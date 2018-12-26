## SocketAddress
使用 SocketAddress 类表示唯一网络端点的 IP 地址和端口对。大多数网络函数也被重载以接受 IP 地址的字符串表示，但是您可以使用 SocketAddress 来避免在重复的网络事务期间解析 IP 地址的开销，并且您可以将其作为第一类对象传递。

## SocketAddress 类参考
[SocketAddress 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td colspan="2">template&lt;typename S &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#ac9af263050bc39274a54dc21b7bc891f" rel="nofollow" target="_blank">SocketAddress</a> (S *stack, const char *host, uint16_t port=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a41239a06a42f22d7e4be8b2b89bd5ccd" rel="nofollow" target="_blank">SocketAddress</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga591b50128653d53a7e0c30a89cb0d00b" rel="nofollow" target="_blank">nsapi_addr_t</a> addr=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga591b50128653d53a7e0c30a89cb0d00b" rel="nofollow" target="_blank">nsapi_addr_t</a>(), uint16_t port=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#acb3582d5cbd1af591bcc754d3c20f9ff" rel="nofollow" target="_blank">SocketAddress</a> (const char *addr, uint16_t port=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#af88ff300ce5b6e0c804e6632456100a0" rel="nofollow" target="_blank">SocketAddress</a> (const void *bytes, nsapi_version_t version, uint16_t port=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a5985916f6607b015d707cb2c51d8829a" rel="nofollow" target="_blank">SocketAddress</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;addr)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a1b5dab61019bebb1666c9b855c03cf71" rel="nofollow" target="_blank">~SocketAddress</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#aceb2ec168ef3000525662869d3a8e227" rel="nofollow" target="_blank">set_ip_address</a> (const char *addr)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a357f44a0adb589bfed7c8bec67ac818e" rel="nofollow" target="_blank">set_ip_bytes</a> (const void *bytes, nsapi_version_t version)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a7160008b4bb81c1d9ea44f93dec44dda" rel="nofollow" target="_blank">set_addr</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga591b50128653d53a7e0c30a89cb0d00b" rel="nofollow" target="_blank">nsapi_addr_t</a> addr)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#ae259c016e3b4bf70bb5a88617c1c99ac" rel="nofollow" target="_blank">set_port</a> (uint16_t port)</td>
		</tr><tr><td style="vertical-align:top;">const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#ada004b9376174acb753ca0544fb9d2e3" rel="nofollow" target="_blank">get_ip_address</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa6d594492452701d5b2e180efcecf1d1" target="_blank"></a> const void *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get_ip_bytes</strong> () const</td>
		</tr><tr><td style="vertical-align:top;">nsapi_version_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a58680852c77e64e07696f3e012835bc8" rel="nofollow" target="_blank">get_ip_version</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga591b50128653d53a7e0c30a89cb0d00b" rel="nofollow" target="_blank">nsapi_addr_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a9cad76d11cec75d6dab88b151cb93fe3" rel="nofollow" target="_blank">get_addr</a> () const</td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a64a6be0fefb3c09caeabfba80bdbde9f" rel="nofollow" target="_blank">get_port</a> () const</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a92d07042825feeb5a3f8255214778c22" rel="nofollow" target="_blank">operator bool</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#ada89744478e77bdf3b4aa5a97e33b6cb" rel="nofollow" target="_blank">operator=</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;addr)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2"><a name="friends" target="_blank"></a> 友元</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#a7d09c2f07c12ea1bb7f64a2784d82a12" rel="nofollow" target="_blank">operator==</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;a, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;b)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html#af58e96464ed237d5ba8d47f8b5efaad9" rel="nofollow" target="_blank">operator!=</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;a, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;b)</td>
		</tr></tbody></table>

## SocketAddress 示例
以下是读取当前 UTC 时间的示例。此示例使用 SocketAddress 类获取服务器 IP 地址和端口。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets/file/cf516d904427/main.cpp)  
```
#include "mbed.h"
#include "EthernetInterface.h"
 
// Network interface
EthernetInterface net;
 
// Time protocol implementation : Address: time.nist.gov UDPPort: 37  
 
typedef struct {
    uint32_t secs;         // Transmit Time-stamp seconds.
}ntp_packet;
 
int main() {
    // Bring up the ethernet interface
    printf("UDP Socket example\n");
    if(0 != net.connect()) {
        printf("Error connecting\n");
        return -1;
    }
 
    // Show the network address
    const char *ip = net.get_ip_address();
    printf("IP address is: %s\n", ip ? ip : "No IP");
        
    UDPSocket sock(&net);
    SocketAddress sockAddr;
 
    char out_buffer[] = "time";
    if(0 > sock.sendto("time.nist.gov", 37, out_buffer, sizeof(out_buffer))) {
        printf("Error sending data\n");
        return -1;
    }
    
    ntp_packet in_data;
    int n = sock.recvfrom(&sockAddr, &in_data, sizeof(ntp_packet));
    in_data.secs = ntohl( in_data.secs ) - 2208988800;    // 1900-1970
    printf("Time Received %lu seconds since 1/01/1900 00:00 GMT\n", 
                        (uint32_t)in_data.secs);
    printf("Time = %s", ctime(( const time_t* )&in_data.secs));
    
    printf("Time Server Address: %s Port: %d\n\r", 
                               sockAddr.get_ip_address(), sockAddr.get_port());
    
    // Close the socket and bring down the network interface
    sock.close();
    net.disconnect();
    return 0;
}
```