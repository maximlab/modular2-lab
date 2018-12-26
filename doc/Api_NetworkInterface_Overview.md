## 网络接口概述
套接字在打开时需要一个 NetworkInterface 实例，以指示应在哪个 NetworkInterface 上创建套接字。NetworkInterface 提供了一个实现底层套接字操作的网络栈。

网络接口也是应用程序指定网络配置的控制 API。

现有网络接口：
+ Ethernet: 用于通过以太网连接连接到互联网的 API。
+ Wi-Fi: 使用 Wi-Fi 设备连接到互联网的 API。
+ Cellular: 用于使用蜂窝设备连接到互联网的 API。
+ Mesh networking interface: Mbed OS 提供两种基于 IPv6 的网状网络 - 6LoWPAN_ND 和 Thread。

可选功能：
+ Network status: 用于监控网络状态更改的 API。