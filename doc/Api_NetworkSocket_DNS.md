## DNS解析器

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.png">

DNS 类层次结构</div>                                                           
DNS 解析器提供了用于执行 DNS 主机名解析的界面。您可以使用 DNS 主机名解析将资源名称转换为 IP 地址。连接接口后，可以进行 DNS 主机名解析。您可以使用返回的 IP 地址建立套接字连接。

### 用法

DNS 解析器支持阻止和异步 DNS 主机名解析。

要进行 DNS 主机名解析：

1. 实例化并连接网络接口。
2. 调用 gethostbyname() 函数来解析地址。

要进行异步 DNS 主机名解析：

1. 为异步主机名解析创建回调函数。
2. 实例化并连接网络接口。
3. 使用回调函数调用 gethostbyname_async() 来解析地址。

要取消异步主机名解析：

1. 存储 gethostbyname_async() 调用返回的唯一 ID。
2. 使用唯一 ID 调用 gethostbyname_async_cancel() 以取消异步地址解析。

### 异步操作

DNS 解析器具有主机名和 IP 地址的缓存。如果从缓存中找到主机名，则 gethostbyname_async() 函数会立即返回成功。在函数返回之前调用回调。

如果地址不在缓存中，gethostbyname_async() 将返回操作的唯一 ID。在从网络上的 DNS 服务器到达响应或发生超时后调用回调。如果需要，您可以使用唯一 ID 取消 DNS 主机名解析。

如果 gethostbyname_async() 返回失败，则不会调用回调。

在设计回调函数时，请考虑以下注意事项：

从线程上下文调用回调。如果回调执行时间超过 10 毫秒，则可能会阻止底层线程处理。由于堆栈大小限制，不要调用网络操作; 回调不应执行昂贵的操作，例如套接字 recv / send 调用或阻塞操作。

## DNS resolver 类参考
[DNS 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> result, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b" rel="nofollow" target="_blank">hostbyname_cb_t</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aca164b9a2db4edd93939403afaaddd7a" rel="nofollow" target="_blank">gethostbyname</a> (const char *host, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address, nsapi_version_t version=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ggacde826f51019112728ee4ae4e10b8a4fa09ed8714a685448ae2e149c4a142ffe7" rel="nofollow" target="_blank">NSAPI_UNSPEC</a>)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga4dc6e8ec26b364f135278917c3f27c6e" rel="nofollow" target="_blank">nsapi_value_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#ab578ede181eece6a3e83b46b237653d2" rel="nofollow" target="_blank">gethostbyname_async</a> (const char *host, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b" rel="nofollow" target="_blank">hostbyname_cb_t</a> callback, nsapi_version_t version=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ggacde826f51019112728ee4ae4e10b8a4fa09ed8714a685448ae2e149c4a142ffe7" rel="nofollow" target="_blank">NSAPI_UNSPEC</a>)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#a8be37f89c88d87ab31868959ae3d4d65" rel="nofollow" target="_blank">gethostbyname_async_cancel</a> (int id)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#ab7f2512a6e368aa8866b798a614d92e0" rel="nofollow" target="_blank">add_dns_server</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)=0</td>
		</tr></tbody></table>

## DNS 解析器示例
此 DNS 解析程序示例使异步 DNS 主机名解析。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/DNS_GetHostbyNameAsync_Example/file/d0f7d306a900/main.cpp)                                                                                                  
```
#include "mbed.h"
#include "nsapi_types.h"
#include "EthernetInterface.h"
#include "SocketAddress.h"
#include "Semaphore.h"
 
rtos::Semaphore callback_semaphore;
SocketAddress address;
nsapi_error_t result;
 
// Callback for asynchronous host name resolution
void hostbyname_callback(nsapi_error_t res, SocketAddress *addr)
{
    // Store result and release semaphore
    result = res;
    address = *addr;
    callback_semaphore.release();
}
 
int main()
{
    // Initialise network interface
    EthernetInterface eth;
    eth.connect();
 
    // Initiate asynchronous DNS host name resolution
    eth.gethostbyname_async("www.mbed.com", hostbyname_callback);
 
    // Wait for callback semaphore
    callback_semaphore.wait();
 
    // Print result
    printf("Result %s, Address %s\r\n", result == NSAPI_ERROR_OK ? "OK" : "FAIL",
        result == NSAPI_ERROR_OK ? address.get_ip_address() : "NONE");
 
    // Disconnect network interface
    eth.disconnect();
}
``` 
## 故障排除信息
网络接口 gethostbyname() 和 gethostbyname_async() 失败原因：

+ NSAPI_ERROR_DNS_FAILURE 表示 DNS 未能成功完成。检查主机名和网络连接。
+ NSAPI_ERROR_NO_MEMORY 表示堆上没有足够的内存来进行地址解析。