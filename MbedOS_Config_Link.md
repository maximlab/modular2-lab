## 连接

此页面描述了 Mbed OS 中连接的构建时可配置参数。有几类可配置的连接参数，因此我们在不同的连接方法之间构建了此页面：

+ LwIP 配置。
+ LwIP 内存优化。
+ LwIP 协议支持。
+ 蜂窝配置。
+ 选择默认网络接口。

**注意**: 您可以在 6LoWPAN 和 Thread Mesh 下找到 Mesh 网络的设置。

以下是 mbed compile --config -v 生成的连接配置参数的完整列表。有关如何使用或覆盖这些设置的详细信息，请参阅配置系统文档。

## LwIP 配置

为 LwIP 构建选项：
```
Configuration parameters
------------------------
 
Name: lwip.addr-timeout
    Description: On dual-stack system how long to additionally wait for other stack's address in seconds
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_ADDR_TIMEOUT
    Value: 5 (set by library:lwip)
Name: lwip.addr-timeout-mode
    Description: Address timeout mode; true: wait both stack's addresses; false: wait for preferred stack's address
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_ADDR_TIMEOUT_MODE
    Value: 1 (set by library:lwip)
Name: lwip.debug-enabled
    Description: Enable debug trace support
    Defined by: library:lwip
    No value set
Name: lwip.use-mbed-trace
    Description: Use mbed trace for debug, rather than printf
    Defined by: library:lwip
    No value set
```
## LwIP 内存优化

以下参数会影响 LwIP 栈的内存使用情况：
```
Configuration parameters
------------------------
 
Name: lwip.default-thread-stacksize
    Description: Stack size for lwip system threads
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_DEFAULT_THREAD_STACKSIZE
    Value: 512 (set by library:lwip)
Name: lwip.ip-ver-pref
    Description: On dual-stack system the preferred stack: 4 for IPv4 and 6 for IPv6
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_IP_VER_PREF
    Value: 4 (set by library:lwip)
Name: lwip.mem-size
    Description: Size of heap (bytes) - used for outgoing packets, and also used by some drivers for reception. Current default (used if null here) is set to 1600 in opt.h, unless overridden by target Ethernet drivers.
    Defined by: library:lwip
    No value set
Name: lwip.pbuf-pool-bufsize
    Description: Size of pbufs in pool. If set to null, lwIP will base the size on the TCP MSS, which is 536 unless overridden by the target
    Defined by: library:lwip
    No value set
Name: lwip.pbuf-pool-size
    Description: Number of pbufs in pool - usually used for received packets, so this determines how much data can be buffered between reception and the application reading. If a driver uses PBUF_RAM for reception, less pool may be needed. Current default (used if null here) is set to 5 in lwipopts.h, unless overridden by target Ethernet drivers.
    Defined by: library:lwip
    No value set
Name: lwip.socket-max
    Description: Maximum number of open TCPServer, TCPSocket and UDPSocket instances allowed, including one used internally for DNS.  Each requires 236 bytes of pre-allocated RAM
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_SOCKET_MAX
    Value: 4 (set by library:lwip)
Name: lwip.tcp-server-max
    Description: Maximum number of open TCPServer instances allowed.  Each requires 72 bytes of pre-allocated RAM
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_TCP_SERVER_MAX
    Value: 4 (set by library:lwip)
Name: lwip.tcp-socket-max
    Description: Maximum number of open TCPSocket instances allowed.  Each requires 196 bytes of pre-allocated RAM
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_TCP_SOCKET_MAX
    Value: 4 (set by library:lwip)
Name: lwip.tcpip-thread-stacksize
    Description: Stack size for lwip TCPIP thread
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_TCPIP_THREAD_STACKSIZE
    Value: 1200 (set by library:lwip)
Name: lwip.udp-socket-max
    Description: Maximum number of open UDPSocket instances allowed, including one used internally for DNS.  Each requires 84 bytes of pre-allocated RAM
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_UDP_SOCKET_MAX
    Value: 4 (set by library:lwip)
Name: lwip.ppp-thread-stacksize
    Description: Thread stack size for PPP
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_PPP_THREAD_STACKSIZE
    Value: 768 (set by library:lwip)
```
## LwIP 协议支持
```
Configuration parameters
------------------------
 
Name: lwip.ethernet-enabled
    Description: Enable support for Ethernet interfaces
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_ETHERNET_ENABLED
    Value: 1 (set by library:lwip)
Name: lwip.ipv4-enabled
    Description: Enable IPv4
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_IPV4_ENABLED
    Value: 1 (set by library:lwip)
Name: lwip.ipv6-enabled
    Description: Enable IPv6
    Defined by: library:lwip
    No value set
Name: lwip.tcp-enabled
    Description: Enable TCP
    Defined by: library:lwip
    Macro name: MBED_CONF_LWIP_TCP_ENABLED
    Value: 1 (set by library:lwip)
Name: lwip.ppp-enabled
    Description: Enable support for PPP interfaces
    Defined by: library:lwip
    No value set
Name: lwip.ppp-ipv4-enabled
    Description: Enable support for ipv4 PPP interface
    Defined by: library:lwip
    Macro name: NSAPI_PPP_IPV4_AVAILABLE
    Value: 1 (set by library:lwip)
Name: lwip.ppp-ipv6-enabled
    Description: Enable support for ipv6 PPP interface
    Defined by: library:lwip
    No value set
```
## 蜂窝配置
```
Configuration parameters
------------------------
 
Name: cellular.random_max_start_delay
    Description: Maximum random delay value used in start-up sequence in milliseconds
    Defined by: library:cellular
    No value set
Name: cellular.use-apn-lookup
    Description: Use APN database lookup
    Defined by: library:cellular
    Macro name: MBED_CONF_CELLULAR_USE_APN_LOOKUP
    Value: 1 (set by library:cellular)
Name: ppp-cell-iface.apn-lookup
    Defined by: library:ppp-cell-iface
    Macro name: MBED_CONF_PPP_CELL_IFACE_APN_LOOKUP
    Value: 1 (set by library:ppp-cell-iface)
Name: ppp-cell-iface.at-parser-buffer-size
    Defined by: library:ppp-cell-iface
    Macro name: MBED_CONF_PPP_CELL_IFACE_AT_PARSER_BUFFER_SIZE
    Value: 256 (set by library:ppp-cell-iface)
Name: ppp-cell-iface.at-parser-timeout
    Defined by: library:ppp-cell-iface
    Macro name: MBED_CONF_PPP_CELL_IFACE_AT_PARSER_TIMEOUT
    Value: 8000 (set by library:ppp-cell-iface)
Name: ppp-cell-iface.baud-rate
    Defined by: library:ppp-cell-iface
    Macro name: MBED_CONF_PPP_CELL_IFACE_BAUD_RATE
    Value: 115200 (set by library:ppp-cell-iface)
Name: lwip.enable-ppp-trace
    Description: Enable trace support for PPP interfaces
    Defined by: library:lwip
    No value set
``` 
## 选择默认网络接口

应用程序可以使用默认网络接口，而无需直接指定其类型。这需要 mbed_app.json 的设置才能工作。

示例应用程序代码可以简单如下：
```
    NetworkInterface *net = NetworkInterface::get_default_instance();
    if (!net) {
        // There is no default...
    }
    net->connet();
```
仅提供以太网连接的板不需要任何配置。默认设置就足够了。提供其他连接选项的板需要选择默认接口类型并为其提供设置。

使用以下 target.network-default-interface-type 参数之一选择默认接口类型：

|target.network-default-interface-type	|必需的配置|
|-|-|
|ETHERNET	|nothing|
|WIFI	|nsapi.default-wifi-security, nsapi.default-wifi-ssid and nsapi.default-wifi-password|
|CELLULAR	|nsapi.default-cellular-apn, nsapi.default-cellular-username and nsapi.default-cellular-password|
|MESH	|nsapi.default-mesh-type|
```
Configuration parameters
------------------------
Name: target.network-default-interface-type
    Description: Default network interface type. Typical options: null, ETHERNET, WIFI, CELLULAR, MESH
    Defined by: target:Target
    Macro name: MBED_CONF_TARGET_NETWORK_DEFAULT_INTERFACE_TYPE
    Value: ETHERNET
Name: nsapi.default-wifi-security
    Defined by: library:nsapi
    Macro name: MBED_CONF_NSAPI_DEFAULT_WIFI_SECURITY
    Value: NONE (set by library:nsapi)
Name: nsapi.default-wifi-ssid
    Defined by: library:nsapi
    No value set
Name: nsapi.default-wifi-password
    Defined by: library:nsapi
    No value set
Name: nsapi.default-cellular-apn
    Defined by: library:nsapi
    No value set
Name: nsapi.default-cellular-password
    Defined by: library:nsapi
    No value set
Name: nsapi.default-cellular-username
    Defined by: library:nsapi
    No value set
Name: nsapi.default-mesh-type
    Defined by: library:nsapi
    Macro name: MBED_CONF_NSAPI_DEFAULT_MESH_TYPE
    Value: THREAD (set by library:nsapi)
Name: nsapi.default-stack
    Defined by: library:nsapi
    Macro name: MBED_CONF_NSAPI_DEFAULT_STACK
    Value: LWIP (set by library:nsapi)
```