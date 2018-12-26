## Wi-Fi
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.png">

Wi-FiInterface 类层次结构</div>
WifiInterface 提供了一个简单的 C++ API，用于通过 Wi-Fi 设备连接到互联网。

Wi-Fi 类参考

[WiFiInterface 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html)
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a0e9f9cdd651e3210126de6faa2e92b43" rel="nofollow" target="_blank">set_credentials</a> (const char *ssid, const char *pass, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga7143eaa7f2ebc72fd968a711bd16b53e" rel="nofollow" target="_blank">nsapi_security_t</a> security=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gga0bfcdf6a9abae30715b5e7f43ae4a0c5a54dc678bd03b26b31588ca37aee6c713" rel="nofollow" target="_blank">NSAPI_SECURITY_NONE</a>)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#ada47234a287483d4daa257d78ca97910" rel="nofollow" target="_blank">set_channel</a> (uint8_t channel)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a63a4451befd0b166aa8817c6e1b5012c" rel="nofollow" target="_blank">get_rssi</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a4510ac0eaf9c28c602bed98a0789fb46" rel="nofollow" target="_blank">connect</a> (const char *ssid, const char *pass, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga7143eaa7f2ebc72fd968a711bd16b53e" rel="nofollow" target="_blank">nsapi_security_t</a> security=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gga0bfcdf6a9abae30715b5e7f43ae4a0c5a54dc678bd03b26b31588ca37aee6c713" rel="nofollow" target="_blank">NSAPI_SECURITY_NONE</a>, uint8_t channel=0)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a19e52e1042c1a89fb2ef3dfa2816ac74" rel="nofollow" target="_blank">connect</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#adb714fc58637a838f6218cb1cbe885b0" rel="nofollow" target="_blank">disconnect</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a78c30e52e431573172114cd28a25ecd8" rel="nofollow" target="_blank">scan</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_access_point.html" rel="nofollow" target="_blank">WiFiAccessPoint</a> *res, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> count)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html" rel="nofollow" target="_blank">WiFiInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a21706f8fad01b7f80a7da65a38c583a1" rel="nofollow" target="_blank">wifiInterface</a> ()</td>
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
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_mesh_interface.html" rel="nofollow" target="_blank">MeshInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a2d7f372bc3430d76d02ddd5e890b1582" rel="nofollow" target="_blank">meshInterface</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_cellular_base.html" rel="nofollow" target="_blank">CellularBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a8a9e9aebe5c371dd71ac8c086f8294fb" rel="nofollow" target="_blank">cellularBase</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_e_m_a_c_interface.html" rel="nofollow" target="_blank">EMACInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a7694af9609cad04f1571d68500926764" rel="nofollow" target="_blank">emacInterface</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html" rel="nofollow" target="_blank">WiFiInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a70d442535b92e16303d545f85047ce83" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a91e2da33575adb34650601d50886b34d" rel="nofollow" target="_blank">get_default_instance</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html" rel="nofollow" target="_blank">WiFiInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_wi_fi_interface.html#a6a90db6f44921c73069e3b393b9f7df4" rel="nofollow" target="_blank">get_target_default_instance</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a9dbae3f6d13c567407357229fbc79a10" rel="nofollow" target="_blank">get_target_default_instance</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;继承自的公共类型 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> result, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a3436eae4de46f8bc4d94f47174fcef4a" rel="nofollow" target="_blank">hostbyname_cb_t</a></td>
		</tr><tr><td colspan="2">&nbsp;Public Types inherited from <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html" rel="nofollow" target="_blank">DNS</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> result, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_d_n_s.html#aec4eac28a4be8097efeacb76f1cd9b4b" rel="nofollow" target="_blank">hostbyname_cb_t</a></td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html" rel="nofollow" target="_blank">NetworkInterface</a></td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_stack.html" rel="nofollow" target="_blank">NetworkStack</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_interface.html#a965f268a97414761bff9e7013434b023" rel="nofollow" target="_blank">get_stack</a> ()=0</td>
		</tr></tbody></table>

## 用法
调出外部 Wi-Fi 设备的网络接口（例如，ESP8266 接口）：

1. 实例化 WiFiInterface 类的实现。
    1. 初始化 AT 命令解析器。
2. 使用 Wi-Fi 网络的 SSID 和密码调用 connect() 函数。
    1. 命令 Wi-Fi 设备连接到网络。
3. 连接后，您可以使用 WiFiInterface 作为打开网络套接字的目标。

调出类似以太网的驱动程序的网络接口（例如，OdinWiFiInterface）：

1. 实例化 WiFiInterface 类的实现。
    1. 初始化目标的 Wi-Fi 驱动程序。
    2. 初始化网络栈（LWIP）。
2. 使用 Wi-Fi 网络的 SSID 和密码调用 connect() 函数。
    1. 将 Wi-Fi 驱动程序连接到 Wi-Fi 网络。
    2. 确保网络堆栈获取 IP 地址和 DNS 服务器地址。
3. 连接后，您可以使用 WiFiInterface 作为打开网络套接字的目标。

## 故障排除信息
网络接口 connect() 和 set_credential() 可能会返回以下错误：

|错误代码	|可能的原因|
|-|-|
|NSAPI_ERROR_UNSUPPORTED	|不支持安全模式。|
|NSAPI_ERROR_PARAMETER	|为给定安全模式提供的参数错误，例如，没有密码。|
|NSAPI_ERROR_NO_SSID	|该设备未找到给定的 Wi-Fi 网络。|
|NSAPI_ERROR_AUTH_FAILURE	|密码错误。|
|NSAPI_ERROR_DEVICE_ERROR	|设备中发生了未知故障。设备可能无法报告更多描述性错误代码。|

## 安全
为了指定安全性设置，connect() 和 set_credential() 都具有可选参数 nsapi_security_t security，它定义了设备使用的安全模式。 WifiInterface 支持以下安全模式：

|nsapi_security_t	|安全模式|
|-|-|
|NSAPI_SECURITY_NONE	|不安全。不需要密码或加密。|
|NSAPI_SECURITY_WEP	|WEP 安全性。过时了。|
|NSAPI_SECURITY_WPA	|WPA 安全模式。WPA 已淘汰；不使用。|
|NSAPI_SECURITY_WPA2	|WPA2 安全性。主要用于安全模式。|
|NSAPI_SECURITY_WPA_WPA2	|允许 WPA 或 WPA2 安全性。|

请注意，设置应与接入点的安全模式匹配。此外，并非所有驱动程序都支持每种模式 对于大多数兼容设置，请使用 NSAPI_SECURITY_WPA_WPA2，并将 Wi-Fi 接入点设置为仅允许 WPA2 模式。

## i-Fi 示例
以下是 HTTP 客户端程序的示例。该程序将 ESP8266 作为底层网络接口，并使用它通过 TCPSocket 执行 HTTP 事务。有多个 Wi-Fi 组件实现了 WiFiInterface 类。以下示例使用 [ESP8266Interface](https://github.com/armmbed/esp8266-driver) 和 [OdinWiFiInterface](https://github.com/u-blox/ublox-odin-w2-drivers-docs-mbed-5)。

ESP8266 接口通过串行接口使用 AT 命令连接到外部 Wi-Fi 设备。OdinWiFiInterface 为 Mbed OS 网络栈提供类似以太网的驱动程序。网络栈使用驱动程序连接到 Wi-Fi：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/TCPSocketWiFi_Example/file/6a4e57edc2b2/main.cpp)        
```
/* WiFi Example
 * Copyright (c) 2016 ARM Limited
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
 
#include "mbed.h"
#include "TCPSocket.h"
 
#if TARGET_UBLOX_EVK_ODIN_W2
#include "OdinWiFiInterface.h"
OdinWiFiInterface wifi;
#else
#if !TARGET_FF_ARDUINO
#error [NOT_SUPPORTED] Only Arduino form factor devices are supported at this time
#endif
#include "ESP8266Interface.h"
ESP8266Interface wifi(D1, D0);
#endif
 
const char *sec2str(nsapi_security_t sec)
{
    switch (sec) {
        case NSAPI_SECURITY_NONE:
            return "None";
        case NSAPI_SECURITY_WEP:
            return "WEP";
        case NSAPI_SECURITY_WPA:
            return "WPA";
        case NSAPI_SECURITY_WPA2:
            return "WPA2";
        case NSAPI_SECURITY_WPA_WPA2:
            return "WPA/WPA2";
        case NSAPI_SECURITY_UNKNOWN:
        default:
            return "Unknown";
    }
}
 
void scan_demo(WiFiInterface *wifi)
{
    WiFiAccessPoint *ap;
 
    printf("Scan:\r\n");
 
    int count = wifi->scan(NULL,0);
 
    /* Limit number of network arbitrary to 15 */
    count = count < 15 ? count : 15;
 
    ap = new WiFiAccessPoint[count];
    count = wifi->scan(ap, count);
    for (int i = 0; i < count; i++)
    {
        printf("Network: %s secured: %s BSSID: %hhX:%hhX:%hhX:%hhx:%hhx:%hhx RSSI: %hhd Ch: %hhd\r\n", ap[i].get_ssid(),
               sec2str(ap[i].get_security()), ap[i].get_bssid()[0], ap[i].get_bssid()[1], ap[i].get_bssid()[2],
               ap[i].get_bssid()[3], ap[i].get_bssid()[4], ap[i].get_bssid()[5], ap[i].get_rssi(), ap[i].get_channel());
    }
    printf("%d networks available.\r\n", count);
 
    delete[] ap;
}
 
void http_demo(NetworkInterface *net)
{
    TCPSocket socket;
 
    printf("Sending HTTP request to www.arm.com...\r\n");
 
    // Open a socket on the network interface, and create a TCP connection to www.arm.com
    socket.open(net);
    socket.connect("www.arm.com", 80);
 
    // Send a simple http request
    char sbuffer[] = "GET / HTTP/1.1\r\nHost: www.arm.com\r\n\r\n";
    int scount = socket.send(sbuffer, sizeof sbuffer);
    printf("sent %d [%.*s]\r\n", scount, strstr(sbuffer, "\r\n")-sbuffer, sbuffer);
 
    // Recieve a simple http response and print out the response line
    char rbuffer[64];
    int rcount = socket.recv(rbuffer, sizeof rbuffer);
    printf("recv %d [%.*s]\r\n", rcount, strstr(rbuffer, "\r\n")-rbuffer, rbuffer);
 
    // Close the socket to return its memory and bring down the network interface
    socket.close();
}
 
int main()
{
    printf("WiFi example\r\n\r\n");
 
    scan_demo(&wifi);
 
    printf("\r\nConnecting...\r\n");
    int ret = wifi.connect(MBED_CONF_APP_WIFI_SSID, MBED_CONF_APP_WIFI_PASSWORD, NSAPI_SECURITY_WPA_WPA2);
    if (ret != 0) {
        printf("\r\nConnection error\r\n");
        return -1;
    }
 
    printf("Success\r\n\r\n");
    printf("MAC: %s\r\n", wifi.get_mac_address());
    printf("IP: %s\r\n", wifi.get_ip_address());
    printf("Netmask: %s\r\n", wifi.get_netmask());
    printf("Gateway: %s\r\n", wifi.get_gateway());
    printf("RSSI: %d\r\n\r\n", wifi.get_rssi());
 
    http_demo(&wifi);
 
    wifi.disconnect();
 
    printf("\r\nDone\r\n");
}
```