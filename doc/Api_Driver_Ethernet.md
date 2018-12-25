## Ethernet
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.png"><br>
EthInterface 类层次结构</div>

EthInterface 提供了一个 C++ API，用于通过以太网连接到互联网。默认情况下，此类不需要任何配置。它能够为目标选择默认的以太网驱动程序并选择正确的网络栈。

## 用法

要静态初始化驱动程序，请创建一个对象而不传递任何参数：
```
EthernetInterface eth;
```
然后，如果默认配置足够，请调出界面：
```
nsapi_error_t status = eth.connect();
```
现在，该接口已准备好用于[网络套接字](https://os.mbed.com/docs/v5.9/reference/network-socket.html)。
```
// Open a TCP socket
TCPSocket socket;
socket.open(&eth);
 
// Open a UDP socket
UDPSocket socket;
socket.open(&eth);
```
## 配置

对于 EthernetInterface，有两种可能的配置：

* 使用 DHCP 进行网络寻址。这是默认值。
* 使用静态配置的 IP 地址。
有关如何通过调用 set_network() 函数来设置 IP 地址，请参阅下面的 API。

## 故障排除信息

网络接口连接失败原因：

* NSAPI_ERROR_NO_CONNECTION 表示以太网链路出现故障。检查以太网连接是否正常。
* NSAPI_ERROR_DHCP_FAILURE 表示获取 IP 地址失败。检查 IP 地址配置服务是否正常。
## EthInterface 类参考

[EthInterface 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html)

|公共成员函数||
|-|:-|
|virtual [EthInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html) * 	|[ethInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html#a9dd5beb5a55ab85b97f65fd91e879e0e) ()|
|公共成员函数继承自 |[NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html)|
|virtual const char * 	|[get_mac_address](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a44e9c420561d0a7e213440b758dd9105) ()|
virtual const char * 	|[get_ip_address](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a4e7eb81a2ccdaaf49a3a6612c4da5a81) ()|
|virtual const char * 	|[get_netmask](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aa77a7ad27b6ff5818732dfcbb1db788c) ()|
|virtual const char * 	|[get_gateway](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1ada53e906ab0a57b4f675a478a29377) ()|
|virtual nsapi_error_t 	|[set_network](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2a7f9400955ef0ad3e541642e671a85e) (const char *ip_address, const char *netmask, const char *gateway)|
|virtual nsapi_error_t 	|[set_dhcp](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#ab7b6c4eea1704e7be7fd0b9cebe14cb0) (bool dhcp)|
|virtual nsapi_error_t 	|[connect](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aa7ef54ecbd066f2083e6031bd1f3cb00) ()=0|
|virtual nsapi_error_t 	|[disconnect](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1a0b6a1cc662ae2483d9cb58e34671a6) ()=0|
|virtual nsapi_error_t 	|[gethostbyname](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a0cf53b62fbf7cf9c4e18f996e1ba3f01) (const char *host, SocketAddress *address, nsapi_version_t version=NSAPI_UNSPEC)|
|virtual nsapi_value_or_error_t 	|[gethostbyname_async](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#abc86c093d4836a70bf1b260af200c106) (const char *host, hostbyname_cb_t callback, nsapi_version_t version=NSAPI_UNSPEC)|
|virtual nsapi_error_t 	|[gethostbyname_async_cancel](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a0e8574fdb15904463225c4e828159093) (int id)|
|virtual nsapi_error_t 	|[add_dns_server](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1ce0661a40f5adfb69e5f5ef86e4e921) (const SocketAddress &address)|
|virtual void 	|[attach](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aff802f87aab01abd0d534ab90fbf85bc) (mbed::Callback< void(nsapi_event_t, intptr_t)> status_cb)|
|virtual nsapi_connection_status_t 	|[get_connection_status](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#af8d764d1e0fa8105bd9091915c94b2ab) () const|
|virtual nsapi_error_t 	|[set_blocking](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1b9125ac147402e7db658b17ab59c0b3) (bool blocking)|
|virtual WiFiInterface * 	|[wifiInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a3113a499d2a23f79f2dcec5b5bd9b916) ()|
|virtual MeshInterface * 	|[meshInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2d7f372bc3430d76d02ddd5e890b1582) ()|
|virtual CellularBase * 	|[cellularBase](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a8a9e9aebe5c371dd71ac8c086f8294fb) ()|
|virtual EMACInterface * 	|[emacInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a7694af9609cad04f1571d68500926764) ()|
|静态公共成员函数||
|static [EthInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html) * 	|[get_default_instance](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html#afe8a7c966c246eb8ffef845053e4862d) ()|
|静态公共成员函数继承自 |[NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html)|
|static [NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html) * 	|[get_default_instance](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a91e2da33575adb34650601d50886b34d) ()|
|静态保护的成员函数||
|static [EthInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html) * 	|[get_target_default_instance](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html#a0c17d80d2db255f7007e23874605514b) ()|
|静态保护的成员函数继承自 |[NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html)|
|static [NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html) * 	|[get_target_default_instance](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a9dbae3f6d13c567407357229fbc79a10) ()|
|其他继承成员||
|继承自的公共类型 |[NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html)|
|typedef [mbed::Callback](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html)< void([nsapi_error_t result](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14), [SocketAddress](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html) *address)> 	|[hostbyname_cb_t](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a3436eae4de46f8bc4d94f47174fcef4a)|
|继承自的公共类型 |[DNS](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html)|
typedef [mbed::Callback](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html)< void([nsapi_error_t result](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14), [SocketAddress](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html) *address)> 	|[hostbyname_cb_t](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b)|
|受保护的成员函数继承自 |[NetworkInterface](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html)|
|virtual [NetworkStack](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_stack.html) * 	|[get_stack](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a965f268a97414761bff9e7013434b023) ()=0|
## EthInterface 示例

以下是 HTTP 客户端程序的示例。该程序将以太网作为底层网络接口，并使用它来通过 TCPSocket 执行 HTTP 事务：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/TCPSocket_Example/file/6b383744246e/main.cpp)                                                                                                                                               <div align=right>[导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed_example/code/TCPSocket_Example)</div>
```
#include "mbed.h"
#include "EthernetInterface.h"
 
// Network interface
EthernetInterface net;
 
// Socket demo
int main() {
    // Bring up the ethernet interface
    printf("Ethernet socket example\n");
    net.connect();
 
    // Show the network address
    const char *ip = net.get_ip_address();
    printf("IP address is: %s\n", ip ? ip : "No IP");
 
    // Open a socket on the network interface, and create a TCP connection to mbed.org
    TCPSocket socket;
    socket.open(&net);
    socket.connect("developer.mbed.org", 80);
 
    // Send a simple http request
    char sbuffer[] = "GET / HTTP/1.1\r\nHost: developer.mbed.org\r\n\r\n";
    int scount = socket.send(sbuffer, sizeof sbuffer);
    printf("sent %d [%.*s]\n", scount, strstr(sbuffer, "\r\n")-sbuffer, sbuffer);
 
    // Recieve a simple http response and print out the response line
    char rbuffer[64];
    int rcount = socket.recv(rbuffer, sizeof rbuffer);
    printf("recv %d [%.*s]\n", rcount, strstr(rbuffer, "\r\n")-rbuffer, rbuffer);
 
    // Close the socket to return its memory and bring down the network interface
    socket.close();
 
    // Bring down the ethernet interface
    net.disconnect();
    printf("Done\n");
}
``` 
相关内容

[网络套接字](https://os.mbed.com/docs/v5.9/reference/network-socket.html) API 参考概述。

[以太网架构](https://os.mbed.com/docs/v5.9/reference/ethernet-technology.html)。