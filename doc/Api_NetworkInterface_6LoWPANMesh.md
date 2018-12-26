## 6LoWPAN Mesh
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.png">

MeshInterface 类层次结构</div>
Arm Mbed Mesh API 允许应用程序通过 [Nanostack](https://os.mbed.com/docs/v5.9/reference/mesh-tech.html#nanostack) 网络栈使用 IPv6 网状网络拓扑。

Mbed OS 提供两种类型的基于 IPv6 的网状网络：

+ 6LoWPAN_ND，松散地遵循 Zigbee-IP 规范。
+ Thread，遵循 Thread 组的规范。
Nanostack 是提供这两种协议的网络栈。有关栈内部的更多信息，请参阅 6LoWPAN 网状技术部分。应用程序开发人员通过 Mbed Mesh API 使用 Nanostack。

应用程序可以使用 LoWPANNDInterface 或 ThreadInterface 对象连接到网状网络。成功连接后，应用程序可以使用 Mbed C++ 套接字 API 创建套接字以启动与远程对等方的通信。

您可以通过在 mbed_app.json 中提供值来配置网格接口，作为网状配置部分文档。

## 用法
1. 创建网络接口和驱动程序对象。
2. 使用给定的 PHY 驱动程序初始化接口。
3. 连接到网络。

## 支持的网状网络模式
目前，支持 6LoWPAN-ND（邻居发现）和 Thread 自举模式。

## 网络连接状态
初始化后，网络状态为 MESH_DISCONNECTED。连接成功后，状态将更改为 MESH_CONNECTED，当与网络断开连接时，状态将更改回 MESH_DISCONNECTED。

如果出现连接错误，状态将更改为某些连接错误状态。在错误状态下，不需要发出断开连接请求，并且允许应用程序再次尝试连接。

## 入门
有关用法，请参阅示例应用程序 mbed-os-example-mesh-minimal。

Mesh 类参考
[MeshInterface 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html" rel="nofollow" target="_blank">MeshInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html#a7dc1d02e417d01cd15d79e746e5149d5" rel="nofollow" target="_blank">meshInterface</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a44e9c420561d0a7e213440b758dd9105" rel="nofollow" target="_blank">get_mac_address</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a4e7eb81a2ccdaaf49a3a6612c4da5a81" rel="nofollow" target="_blank">get_ip_address</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aa77a7ad27b6ff5818732dfcbb1db788c" rel="nofollow" target="_blank">get_netmask</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1ada53e906ab0a57b4f675a478a29377" rel="nofollow" target="_blank">get_gateway</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2a7f9400955ef0ad3e541642e671a85e" rel="nofollow" target="_blank">set_network</a> (const char *ip_address, const char *netmask, const char *gateway)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#ab7b6c4eea1704e7be7fd0b9cebe14cb0" rel="nofollow" target="_blank">set_dhcp</a> (bool dhcp)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#aa7ef54ecbd066f2083e6031bd1f3cb00" rel="nofollow" target="_blank">connect</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a1a0b6a1cc662ae2483d9cb58e34671a6" rel="nofollow" target="_blank">disconnect</a> ()=0</td>
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
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html" rel="nofollow" target="_blank">CellularBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a8a9e9aebe5c371dd71ac8c086f8294fb" rel="nofollow" target="_blank">cellularBase</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_e_m_a_c_interface.html" rel="nofollow" target="_blank">EMACInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a7694af9609cad04f1571d68500926764" rel="nofollow" target="_blank">emacInterface</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html" rel="nofollow" target="_blank">MeshInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html#a7a2d5734d6bb491b2186a90488ce3d21" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a91e2da33575adb34650601d50886b34d" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html" rel="nofollow" target="_blank">MeshInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html#ae1b09e6c77a8179c22e9e814e06ebc3c" rel="nofollow" target="_blank">get_target_default_instance</a> ()</td>
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

## Mesh 示例
下面的应用程序演示了一个简单的灯光控制应用程序，其中设备可以控制网络中所有设备的 LED 状态。您可以为不安全的 6LoWPAN-ND 或 Thread 网络构建应用程序。

[main.cpp](https://github.com/ARMmbed/mbed-os-example-mesh-minimal/blob/master/main.cpp)   
```
/*
 * Copyright (c) 2016 ARM Limited. All rights reserved.
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
#include "rtos.h"
#include "NanostackInterface.h"
#include "mbed-trace/mbed_trace.h"
#include "mesh_nvm.h"
 
#if MBED_CONF_APP_ENABLE_LED_CONTROL_EXAMPLE
#include "mesh_led_control_example.h"
#endif
 
void trace_printer(const char* str) {
    printf("%s\n", str);
}
 
#define ATMEL   1
#define MCR20   2
#define NCS36510 3
#define KW24D   4
 
#define MESH_LOWPAN     3
#define MESH_THREAD     4
 
#if MBED_CONF_APP_RADIO_TYPE == ATMEL
#include "NanostackRfPhyAtmel.h"
NanostackRfPhyAtmel rf_phy(ATMEL_SPI_MOSI, ATMEL_SPI_MISO, ATMEL_SPI_SCLK, ATMEL_SPI_CS,
                           ATMEL_SPI_RST, ATMEL_SPI_SLP, ATMEL_SPI_IRQ, ATMEL_I2C_SDA, ATMEL_I2C_SCL);
#elif MBED_CONF_APP_RADIO_TYPE == MCR20 || MBED_CONF_APP_RADIO_TYPE == KW24D
#include "NanostackRfPhyMcr20a.h"
NanostackRfPhyMcr20a rf_phy(MCR20A_SPI_MOSI, MCR20A_SPI_MISO, MCR20A_SPI_SCLK, MCR20A_SPI_CS, MCR20A_SPI_RST, MCR20A_SPI_IRQ);
 
#elif MBED_CONF_APP_RADIO_TYPE == NCS36510
#include "NanostackRfPhyNcs36510.h"
NanostackRfPhyNcs36510 rf_phy;
#endif //MBED_CONF_APP_RADIO_TYPE
 
#if MBED_CONF_APP_MESH_TYPE == MESH_LOWPAN
LoWPANNDInterface mesh;
#elif MBED_CONF_APP_MESH_TYPE == MESH_THREAD
ThreadInterface mesh;
#endif //MBED_CONF_APP_MESH_TYPE
 
static Mutex SerialOutMutex;
 
void serial_out_mutex_wait()
{
    SerialOutMutex.lock();
}
 
void serial_out_mutex_release()
{
    SerialOutMutex.unlock();
}
 
int main()
{
    mbed_trace_init();
    mbed_trace_print_function_set(trace_printer);
    mbed_trace_mutex_wait_function_set( serial_out_mutex_wait );
    mbed_trace_mutex_release_function_set( serial_out_mutex_release );
    
    printf("Start mesh-minimal application\n");
    printf("Build: %s %s\nMesh type: %d\n", __DATE__, __TIME__, MBED_CONF_APP_MESH_TYPE);
 
#if MBED_CONF_APP_ENABLE_LED_CONTROL_EXAMPLE
    if (MBED_CONF_APP_BUTTON != NC && MBED_CONF_APP_LED != NC) {
        start_blinking();
    } else {
        printf("pins not configured. Skipping the LED control.\n");
    }
#endif
    printf("\n\nConnecting...\n");
    mesh.initialize(&rf_phy);
    mesh_nvm_initialize();
    int error = mesh.connect();
    if (error) {
        printf("Connection failed! %d\n", error);
        return error;
    }
 
    while (NULL == mesh.get_ip_address())
        Thread::wait(500);
 
    printf("connected. IP = %s\n", mesh.get_ip_address());
 
#if MBED_CONF_APP_ENABLE_LED_CONTROL_EXAMPLE
    // Network found, start socket example
    if (MBED_CONF_APP_BUTTON != NC && MBED_CONF_APP_LED != NC) {
        cancel_blinking();
        start_mesh_led_control_example((NetworkInterface *)&mesh);
    }
#endif
}

```