## Wi-Fi
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.png">

CellularBase 类层次结构</div>
CellularBase 提供了一个 C++ API，用于通过蜂窝设备连接到互联网。

Arm Mbed OS 提供了 CellularBase 的参考实现，它具有更多信息。

### Cellular

CellularBase 提供了一个 C++ API，用于通过蜂窝设备连接到互联网。

Arm Mbed OS 提供了 CellularBase 的参考实现。

### 入门

1. 选择支持蜂窝的 Mbed 板，例如 UBLOX-C027 或 MTS-DRAGONFLY。

2. 克隆 mbed-os-example-cellular。按照存储库中的说明进行操作。

    1. 编译代码。
    2. 下载到板子。
您会看到类似于以下摘录的输出：
```
mbed-os-example-cellular
Establishing connection ......
 
Connection Established.
TCP: connected with echo.mbedcloudtesting.com server
TCP: Sent 4 Bytes to echo.mbedcloudtesting.com
Received from echo server 4 Bytes
 
Success. Exiting
```
### 基本工作原则

您可以通过各种不同方式使用和扩展蜂窝接口。例如，

+ 使用 AT 命令控制蜂窝调制解调器内置的现有 IP 栈中的套接字。
 <div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Cell_AT.png"></div>               

+ 使用 PPP（点对点协议）管道在 Mbed OS 支持的 IP 栈和蜂窝调制解调器设备之间传递 IP 数据包。
 <div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Cell_PPP.png"></div>               

[mbed-os-example-cellular](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-cellular/) 使用简单的蜂窝连接。它取决于调制解调器应用程序是使用 PPP 还是 AT 模式。我们可以总结这个特定的设计如下：

+ 它使用外部 IP 栈（如 LWIP）或片上网络栈（例如调制解调器不支持 PPP 时）。
+ 简单的蜂窝连接使用标准的 3GPP AT 27.007 AT 命令来建立蜂窝调制解调器并注册到网络。
+ 注册后，驱动程序使用带有蜂窝调制解调器的 LWIP 打开 PPP 管道并连接到互联网。如果正在使用仅 AT 模式，则调制解调器专用的 AT 命令用于套接字数据控制。

## CellularBase 类参考

[CellularBase 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html)
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a416f5d4ae492773c3e3b5e51acf5e336" rel="nofollow" target="_blank">set_credentials</a> (const char *apn, const char *uname=0, const char *pwd=0)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#ada921fd24c5db4548276afc7546078c6" rel="nofollow" target="_blank">set_sim_pin</a> (const char *sim_pin)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#ac9e05d8e54a8e876bce2bc468cac1735" rel="nofollow" target="_blank">connect</a> (const char *sim_pin, const char *apn=0, const char *uname=0, const char *pwd=0)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a881d87ecfdb0220eb97cb4fbb014f490" rel="nofollow" target="_blank">connect</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a7680e9ef758a7fd92b76ea36f9501e37" rel="nofollow" target="_blank">disconnect</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a4240a7c5f115d810d6205995dcab61d9" rel="nofollow" target="_blank">is_connected</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a1e59e0fdb4da8c27c5ddd203cd3d5e00" rel="nofollow" target="_blank">get_ip_address</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#ac0410fa7845692bfde42638c8c895e4f" rel="nofollow" target="_blank">get_netmask</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#af6c381fa7269e1f8e4d10a8a2bc4e1a3" rel="nofollow" target="_blank">get_gateway</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html" rel="nofollow" target="_blank">CellularBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#acba0d5354e65ae38625832cf2b2a5783" rel="nofollow" target="_blank">cellularBase</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a44e9c420561d0a7e213440b758dd9105" rel="nofollow" target="_blank">get_mac_address</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2a7f9400955ef0ad3e541642e671a85e" rel="nofollow" target="_blank">set_network</a> (const char *ip_address, const char *netmask, const char *gateway)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#ab7b6c4eea1704e7be7fd0b9cebe14cb0" rel="nofollow" target="_blank">set_dhcp</a> (bool dhcp)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a0cf53b62fbf7cf9c4e18f996e1ba3f01" rel="nofollow" target="_blank">gethostbyname</a> (const char *host, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address, nsapi_version_t version=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ggacde826f51019112728ee4ae4e10b8a4fa09ed8714a685448ae2e149c4a142ffe7" rel="nofollow" target="_blank">NSAPI_UNSPEC</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga4dc6e8ec26b364f135278917c3f27c6e" rel="nofollow" target="_blank">nsapi_value_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#abc86c093d4836a70bf1b260af200c106" rel="nofollow" target="_blank">gethostbyname_async</a> (const char *host, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b" rel="nofollow" target="_blank">hostbyname_cb_t</a> callback, nsapi_version_t version=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ggacde826f51019112728ee4ae4e10b8a4fa09ed8714a685448ae2e149c4a142ffe7" rel="nofollow" target="_blank">NSAPI_UNSPEC</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a0e8574fdb15904463225c4e828159093" rel="nofollow" target="_blank">gethostbyname_async_cancel</a> (int id)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1ce0661a40f5adfb69e5f5ef86e4e921" rel="nofollow" target="_blank">add_dns_server</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aff802f87aab01abd0d534ab90fbf85bc" rel="nofollow" target="_blank">attach</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(nsapi_event_t, intptr_t)&gt; status_cb)</td>
		</tr><tr><td style="vertical-align:top;">virtual nsapi_connection_status_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#af8d764d1e0fa8105bd9091915c94b2ab" rel="nofollow" target="_blank">get_connection_status</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1b9125ac147402e7db658b17ab59c0b3" rel="nofollow" target="_blank">set_blocking</a> (bool blocking)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_eth_interface.html" rel="nofollow" target="_blank">EthInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a9b4de0ab54920b8a815169d19b8266c9" rel="nofollow" target="_blank">ethInterface</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html" rel="nofollow" target="_blank">WiFiInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a3113a499d2a23f79f2dcec5b5bd9b916" rel="nofollow" target="_blank">wifiInterface</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html" rel="nofollow" target="_blank">MeshInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2d7f372bc3430d76d02ddd5e890b1582" rel="nofollow" target="_blank">meshInterface</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_e_m_a_c_interface.html" rel="nofollow" target="_blank">EMACInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a7694af9609cad04f1571d68500926764" rel="nofollow" target="_blank">emacInterface</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html" rel="nofollow" target="_blank">CellularBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a7fee63dac5dc6e818a7d3be6307a4dd8" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a91e2da33575adb34650601d50886b34d" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html" rel="nofollow" target="_blank">CellularBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html#a054e5ae2985a082203f4a817a5812e6b" rel="nofollow" target="_blank">get_target_default_instance</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a9dbae3f6d13c567407357229fbc79a10" rel="nofollow" target="_blank">get_target_default_instance</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;继承自的公共类型 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> result, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a3436eae4de46f8bc4d94f47174fcef4a" rel="nofollow" target="_blank">hostbyname_cb_t</a></td>
		</tr><tr><td colspan="2">&nbsp;继承自的公共类型 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html" rel="nofollow" target="_blank">DNS</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> result, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b" rel="nofollow" target="_blank">hostbyname_cb_t</a></td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_stack.html" rel="nofollow" target="_blank">NetworkStack</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a965f268a97414761bff9e7013434b023" rel="nofollow" target="_blank">get_stack</a> ()=0</td>
		</tr></tbody></table>

## 用法
调出网络接口：

1. 实例化 CellularBase 类的实现。
2. 使用您的 SIM 卡的 PIN 码和网络的 APN 呼叫连接（pincode，apn）功能。
3. 连接后，您可以像往常一样使用 Mbed OS 网络套接字。

## Cellular 示例：连接建立
此示例使用 Mbed OS CellularInterface 建立与蜂窝网络的连接。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-cellular/file/0f644d6045cf/main.cpp) 
```
/*
 * Copyright (c) 2017 ARM Limited. All rights reserved.
 * SPDX-License-Identifier: Apache-2.0
 * Licensed under the Apache License, Version 2.0 (the License); you may
 * not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an AS IS BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
 
#include "mbed.h"
#include "common_functions.h"
#include "UDPSocket.h"
#include "OnboardCellularInterface.h"
 
#define UDP 0
#define TCP 1
 
// SIM pin code goes here
#ifndef MBED_CONF_APP_SIM_PIN_CODE
# define MBED_CONF_APP_SIM_PIN_CODE    "1234"
#endif
 
#ifndef MBED_CONF_APP_APN
# define MBED_CONF_APP_APN         "internet"
#endif
#ifndef MBED_CONF_APP_USERNAME
# define MBED_CONF_APP_USERNAME    NULL
#endif
#ifndef MBED_CONF_APP_PASSWORD
# define MBED_CONF_APP_PASSWORD    NULL
#endif
 
// Number of retries /
#define RETRY_COUNT 3
 
 
 
// CellularInterface object
OnboardCellularInterface iface;
 
// Echo server hostname
const char *host_name = "echo.mbedcloudtesting.com";
 
// Echo server port (same for TCP and UDP)
const int port = 7;
 
Mutex PrintMutex;
Thread dot_thread(osPriorityNormal, 512);
 
#define PRINT_TEXT_LENGTH 128
char print_text[PRINT_TEXT_LENGTH];
void print_function(const char *input_string)
{
    PrintMutex.lock();
    printf("%s", input_string);
    fflush(NULL);
    PrintMutex.unlock();
}
 
void dot_event()
{
 
    while (true) {
        wait(4);
        if (!iface.is_connected()) {
            print_function(".");
        } else {
            break;
        }
    }
 
}
 
 
/**
 * Connects to the Cellular Network
 */
nsapi_error_t do_connect()
{
    nsapi_error_t retcode;
    uint8_t retry_counter = 0;
 
    while (!iface.is_connected()) {
 
        retcode = iface.connect();
        if (retcode == NSAPI_ERROR_AUTH_FAILURE) {
            print_function("\n\nAuthentication Failure. Exiting application\n");
            return retcode;
        } else if (retcode != NSAPI_ERROR_OK) {
            snprintf(print_text, PRINT_TEXT_LENGTH, "\n\nCouldn't connect: %d, will retry\n", retcode);
            print_function(print_text);
            retry_counter++;
            continue;
        } else if (retcode != NSAPI_ERROR_OK && retry_counter > RETRY_COUNT) {
            snprintf(print_text, PRINT_TEXT_LENGTH, "\n\nFatal connection failure: %d\n", retcode);
            print_function(print_text);
            return retcode;
        }
 
        break;
    }
 
    print_function("\n\nConnection Established.\n");
 
    return NSAPI_ERROR_OK;
}
 
/**
 * Opens a UDP or a TCP socket with the given echo server and performs an echo
 * transaction retrieving current.
 */
nsapi_error_t test_send_recv()
{
    nsapi_size_or_error_t retcode;
#if MBED_CONF_APP_SOCK_TYPE == TCP
    TCPSocket sock;
#else
    UDPSocket sock;
#endif
 
    retcode = sock.open(&iface);
    if (retcode != NSAPI_ERROR_OK) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "UDPSocket.open() fails, code: %d\n", retcode);
        print_function(print_text);
        return -1;
    }
 
    SocketAddress sock_addr;
    retcode = iface.gethostbyname(host_name, &sock_addr);
    if (retcode != NSAPI_ERROR_OK) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "Couldn't resolve remote host: %s, code: %d\n", host_name,
               retcode);
        print_function(print_text);
        return -1;
    }
 
    sock_addr.set_port(port);
 
    sock.set_timeout(15000);
    int n = 0;
    const char *echo_string = "TEST";
    char recv_buf[4];
#if MBED_CONF_APP_SOCK_TYPE == TCP
    retcode = sock.connect(sock_addr);
    if (retcode < 0) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "TCPSocket.connect() fails, code: %d\n", retcode);
        print_function(print_text);
        return -1;
    } else {
        snprintf(print_text, PRINT_TEXT_LENGTH, "TCP: connected with %s server\n", host_name);
        print_function(print_text);
    }
    retcode = sock.send((void*) echo_string, sizeof(echo_string));
    if (retcode < 0) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "TCPSocket.send() fails, code: %d\n", retcode);
        print_function(print_text);
        return -1;
    } else {
        snprintf(print_text, PRINT_TEXT_LENGTH, "TCP: Sent %d Bytes to %s\n", retcode, host_name);
        print_function(print_text);
    }
 
    n = sock.recv((void*) recv_buf, sizeof(recv_buf));
#else
 
    retcode = sock.sendto(sock_addr, (void*) echo_string, sizeof(echo_string));
    if (retcode < 0) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "UDPSocket.sendto() fails, code: %d\n", retcode);
        print_function(print_text);
        return -1;
    } else {
        snprintf(print_text, PRINT_TEXT_LENGTH, "UDP: Sent %d Bytes to %s\n", retcode, host_name);
        print_function(print_text);
    }
 
    n = sock.recvfrom(&sock_addr, (void*) recv_buf, sizeof(recv_buf));
#endif
 
    sock.close();
 
    if (n > 0) {
        snprintf(print_text, PRINT_TEXT_LENGTH, "Received from echo server %d Bytes\n", n);
        print_function(print_text);
        return 0;
    }
 
    return -1;
}
 
int main()
{
 
    iface.modem_debug_on(MBED_CONF_APP_MODEM_TRACE);
    /* Set Pin code for SIM card */
    iface.set_sim_pin(MBED_CONF_APP_SIM_PIN_CODE);
 
    /* Set network credentials here, e.g., APN*/
    iface.set_credentials(MBED_CONF_APP_APN, MBED_CONF_APP_USERNAME, MBED_CONF_APP_PASSWORD);
 
    print_function("\n\nmbed-os-example-cellular\n");
    print_function("Establishing connection ");
    dot_thread.start(dot_event);
 
    /* Attempt to connect to a cellular network */
    if (do_connect() == NSAPI_ERROR_OK) {
        nsapi_error_t retcode = test_send_recv();
        if (retcode == NSAPI_ERROR_OK) {
            print_function("\n\nSuccess. Exiting \n\n");
            return 0;
        }
    }
 
    print_function("\n\nFailure. Exiting \n\n");
    return -1;
}
// EOF
```