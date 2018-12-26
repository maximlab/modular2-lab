## 网络套接字概述
IP 网络的应用程序编程接口是 Socket API。如本书的 IP 网络部分所述，Socket API 与 OSI 第 4 层（传输层）相关。在 Mbed OS 中，Socket API 支持 TCP 和 UDP 协议。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/ip-networking.png">

套接字</div>
                                                                                         

在 Mbed OS 中，此套接字 API 基于 C++，但严格遵循 POSIX 标准（IEEE Std 1003.1）和相关 RFC 标准的功能。标准将套接字分为两类，即数据报和流套接字。Mbed OS 使用协议名称 UDPSocket 作为数据报，使用 TCPSocket 作为流。

## 一般用法
以下步骤描述了典型的应用程序流程：

1. 初始化网络接口。
2. 创建一个套接字。
3. 连接（不适用于 UDP）。
4. 发送数据。
5. 接收数据。
6. 关闭套接字。
以下代码通过向服务器发送 HTTP 查询来演示这些步骤：
```
// Initialize network interface
EthernetInterface eth;
eth.connect();
 
// Create a socket
TCPSocket sock;
sock.open(&eth);
 
// Connect
sock.connect("arm.com", 80);
 
// Send data
sock.send("GET / HTTP/1.0\r\n\r\n", 18);
 
// Receive data
char buf[100];
sock.recv(buf, 100);
 
// Close the socket
sock.close();
```
## 网络套接字类
网络套接字 API 提供了在网络设备上使用套接字的通用接口。它是一个基于类的接口，对于使用其他套接字 API 的用户来说很熟悉。

+ UDPSocket: 此类提供使用 sendto 和 recvfrom 成员函数通过 UDP 发送数据包的功能。
+ TCPSocket: 此类提供通过 TCP 发送数据流的功能。
+ TCPServer: 此类提供接受传入 TCP 连接的功能。
+ SocketAddress: 您可以使用此类来表示唯一网络端点的 IP 地址和端口对。
+ Network status: 用于监控网络状态更改的 API。
## 网络错误
网络套接字 API 的约定是用于返回负错误代码以指示失败的函数。成功时，函数可以返回零或非负整数以指示事务的大小。失败时，函数必须返回一个负整数，这是 nsapi_error_t 枚举中的错误代码之一：
```
/** Enum of standardized error codes
 *
 *  Valid error codes have negative values and may
 *  be returned by any network operation.
 *
 *  @enum nsapi_error
 */
enum nsapi_error {
    NSAPI_ERROR_OK                  =  0,        /*!< no error */
    NSAPI_ERROR_WOULD_BLOCK         = -3001,     /*!< no data is not available but call is non-blocking */
    NSAPI_ERROR_UNSUPPORTED         = -3002,     /*!< unsupported functionality */
    NSAPI_ERROR_PARAMETER           = -3003,     /*!< invalid configuration */
    NSAPI_ERROR_NO_CONNECTION       = -3004,     /*!< not connected to a network */
    NSAPI_ERROR_NO_SOCKET           = -3005,     /*!< socket not available for use */
    NSAPI_ERROR_NO_ADDRESS          = -3006,     /*!< IP address is not known */
    NSAPI_ERROR_NO_MEMORY           = -3007,     /*!< memory resource not available */
    NSAPI_ERROR_NO_SSID             = -3008,     /*!< ssid not found */
    NSAPI_ERROR_DNS_FAILURE         = -3009,     /*!< DNS failed to complete successfully */
    NSAPI_ERROR_DHCP_FAILURE        = -3010,     /*!< DHCP failed to complete successfully */
    NSAPI_ERROR_AUTH_FAILURE        = -3011,     /*!< connection to access point failed */
    NSAPI_ERROR_DEVICE_ERROR        = -3012,     /*!< failure interfacing with the network processor */
    NSAPI_ERROR_IN_PROGRESS         = -3013,     /*!< operation (eg connect) in progress */
    NSAPI_ERROR_ALREADY             = -3014,     /*!< operation (eg connect) already in progress */
    NSAPI_ERROR_IS_CONNECTED        = -3015,     /*!< socket is already connected */
    NSAPI_ERROR_CONNECTION_LOST     = -3016,     /*!< connection lost */
    NSAPI_ERROR_CONNECTION_TIMEOUT  = -3017,     /*!< connection timed out */
};
```
## 非阻塞操作
网络套接字 API 还支持非阻塞操作。set_blocking() 成员函数更改套接字的状态。当套接字处于非阻塞模式时，当事务无法立即完成时，套接字操作将返回 NSAPI_ERROR_WOULD_BLOCK。

为了有效地使用非阻塞操作，套接字类提供了一个 sigio() 成员函数来在套接字状态更改上注册回调。当套接字可以成功接收，发送或接受或发生错误时，系统会触发回调。它可能会毫无理由地虚假地调用回调。

您可以在中断上下文中调用回调，但在线程上之前不要进行任何读取或写入调用。

以下示例显示如何为套接字设置异步处理程序：
```
nsapi_size_or_error_t send_query(TCPSocket *socket) {
    return socket->send(QUERY, QUERY_LEN);
}
 
nsapi_size_or_error_t receive_data(TCPSocket *socket) {
    // Simplified example, does not properly handle streaming and appending to buffer
    return socket->recv(my_buffer, remaining_len);
}
 
void handle_socket_sigio(EventFlags *evt, TCPSocket *socket)
{
    static enum {
        CONNECTING,
        SEND,
        RECEIVE,
        CLOSE,
    } next_state = CONNECTING;
 
    switch (next_state) {
        case CONNECTING:
            switch(socket->connect("api.ipify.org", 80)) {
                case NSAPI_ERROR_IN_PROGRESS:
                    // Connecting to server
                    break;
                case NSAPI_ERROR_ALREADY:
                    // Now connected to server
                    next_state = SEND;
                    break;
                default:
                    // Error in connection phase
                    next_state = CLOSE;
            }
        case SEND:
            if (send_query(socket) > 0)
                next_state = RECEIVE;
            else
                next_state = CLOSE; // Error
            break;
        case RECEIVE:
            if (receive_data(socket) == NSAPI_ERROR_WOULD_BLOCK)
                break;
            next_state = CLOSE;
            break;
        case CLOSE:
            socket->close();
            evt->set(1); // Signal the main thread
            break;
    }
}
 
int main() {
    EthernetInterface net;
    net.connect();
 
    TCPSocket socket;
    socket.open(&net);
 
    EventFlags completed;
    EventQueue *queue = mbed_event_queue();
 
    Event<void()> handler = queue->event(handle_socket_sigio, &completed, &socket);
 
    socket.set_blocking(false);
    socket.sigio(handler);
    handler();                   // Kick the state machine to start connecting
 
    completed.wait_any(1);
}
```