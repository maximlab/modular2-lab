## LoRaWAN 概述
LoRaWAN 是一种专为低功耗电池供电设备而设计的技术。这些设备在未经许可的频谱中运行，从而创建高密度的广域网。

Arm Mbed OS 为 LoRaWAN 提供本地网络栈，可以在任何带有 LoRa 无线电的 Mbed Enabled 设备上运行。

[LoRaWANInterface](https://os.mbed.com/docs/v5.9/reference/lorawan-api.html) 提供了一个 C++ API，用于通过 LoRa 网络连接到互联网。

## 用法
要调出 Mbed LoRaWAN 栈，请考虑以下进展：

+ 一个 EventQueue 对象：
```
// construct an event queue
EventQueue ev_queue(NUM_EVENTS * EVENTS_EVENT_SIZE);
```
+ 一个 LoRaRadio 对象：
```
// construct a LoRadio object
SX1272_LoRaRadio radio(PIN_NAMES ... );
```
+ 实例化 LoRaWANInterface，并传递 LoRaRadio 对象：
```
LoRaWANInterface lorawan(radio) ;
```
+ 初始化 mac 层并传递 EventQueue 对象：
```
lorawan.initialize(&ev_queue);
```
+ 设置事件回调：
```
lorawan_app_callbacks_t callbacks
callbacks.events = mbed::callback(YOUR_EVENT_HANDLER);
lorawan.add_app_callbacks(&callbacks);
```
+ 添加网络凭据（安全密钥）和任何配置：
```
lorawan_connect_t connection;
 
connection.connect_type = LORAWAN_CONNECTION_OTAA;
connection.connection_u.otaa.app_eui = YOUR_APP_EUI_KEY;
connection.connection_u.otaa.dev_eui = YOUR_DEV_EUI_KEY;
connection.connection_u.otaa.app_key = YOUR_APP_KEY;
connection.connection_u.otaa.nb_trials = MBED_CONF_LORA_NB_TRIALS;
 
lorawan.connect(connection);
```
由于大多数 LoRaWAN 设备都是简单的遥测设备，因此栈及其操作需要尽可能简单。这就是 Mbed LoRaWAN 栈是事件驱动的原因。

### 网络事件和回调

以下是您可以从栈发布到应用程序的可能事件列表：

|事件	|描述|
|-|-|
|CONNECTED	|连接完成后|
|DISCONNECTED	|当协议关闭以响应 disconnect() 时|
|TX_DONE	|发送数据包时|
|TX_TIMEOUT	|当栈无法在 TX 窗口中发送数据包时|
|TX_ERROR	|一般的 TX 错误|
|TX_CRYPTO_ERROR	|如果 MIC 失败，或任何其他加密相关的错误|
|TX_SCHEDULING_ERROR	|当栈无法安排数据包时|
|TX_TIMEOUT	|当栈无法在 TX 窗口中发送数据包时|
|RX_DONE	|收到数据包时|
|RX_ERROR	|一般的 RX 错误|

应用程序必须将事件处理程序附加到栈。LoRaWANInterface 提供了一个 API，用于将各种回调附加到栈。一个这样的回调是事件处理程序回调。

### 应用程序回调

Mbed LoRaWAN 栈当前映射了 3 种不同的回调：

|回调类型	|描述|
|-|-|
|事件回调	|强制性，方向：从栈到应用程序|
|链接检查响应回调	|可选，方向：从栈到应用程序|
|电池电量回调	|可选，方向：从应用程序到栈|

### 事件处理程序

将事件处理程序附加到栈的示例：

``` 
void your_event_handler(lorawan_event_t event)
{
    switch (event) {
        case CONNECTED:
        //do something
            break;
        case DISCONNECTED:
            break;
	....
	....
    }
}
lorawan_app_callbacks_t callbacks;
 
callbacks.events = mbed::callback(your_event_handler);
//lorawan is the LoRaWANInterface object
lorawan.add_app_callbacks(&callbacks);
```
### 链接检查响应处理程序

链路检查请求是由 LoRaWAN 规范定义的 MAC 命令。要接收此 MAC 命令的响应，请设置 link_check_resp 回调。
```
void your_link_check_response(uint8_t demod_margin, uint8_t num_gw)
{
	//demod_margin is the demodulation margin
	// num_gw represents the number of gateways involved in the path
}
 
callbacks.link_check_resp = mbed::callback(your_link_check_response);
lorawan.add_app_callbacks(&callbacks);
``` 
### 电池电量处理器

电池电量回调与其他回调不同。此回调的方向是从应用程序到栈。换句话说，它为栈提供信息。应用程序负责让栈知道当前的电池电量。
```
uint8_t your_battery_level()
{
	return battery_level;
}
 
callbacks.battery_level = mbed::callback(your_battery_level);
lorawan.add_app_callbacks(&callbacks);
```
### 错误代码

LoRaWANInterface 上的所有操作都返回一个错误代码 lorawan_status_t，它反映了操作的成功或失败。

以下是错误代码及其说明的列表。

|错误代码	|值	|描述|
|-|:-:|-|-|
|LORAWAN_STATUS_OK	|0	|服务成功完成|
|LORAWAN_STATUS_BUSY	|-1000	|栈忙|
|LORAWAN_STATUS_WOULD_BLOCK	|-1001	|栈目前无法发送或无法读取|
|LORAWAN_STATUS_SERVICE_UNKNOWN	|-1002	|未知的服务请求|
|LORAWAN_STATUS_PARAMETER_INVALID	|-1003	|无效的参数|
|LORAWAN_STATUS_FREQUENCY_INVALID	|-1004	|频率无效|
|LORAWAN_STATUS_DATARATE_INVALID	|-1005	|频率和数据速率无效|
|LORAWAN_STATUS_FREQ_AND_DR_INVALID	|-1006	|当栈无法在 TX 窗口中发送数据包时|
|LORAWAN_STATUS_NO_NETWORK_JOINED	|-1009	|设备尚未成为网络的一部分（仅适用于 OTAA）|
|LORAWAN_STATUS_LENGTH_ERROR	|-1010	|有效载荷长度错误|
|LORAWAN_STATUS_DEVICE_OFF	|-1011	|设备关闭，换句话说，断开状态|
|LORAWAN_STATUS_NOT_INITIALIZED	|-1012	|栈未初始化|
|LORAWAN_STATUS_UNSUPPORTED	|-1013	|不受支持的服务|
|LORAWAN_STATUS_CRYPTO_FAIL	|-1014	|加密失败|
|LORAWAN_STATUS_PORT_INVALID	|-1015	|无效的端口|
|LORAWAN_STATUS_CONNECT_IN_PROGRESS	|-1016	|正在进行连接（应用程序应等待 CONNECT 事件）|
|LORAWAN_STATUS_NO_ACTIVE_SESSIONS	|-1017	|没有正在进行的活动会话|
|LORAWAN_STATUS_IDLE	|-1018	|此刻栈空闲|
|LORAWAN_STATUS_DUTYCYCLE_RESTRICTED	|-1020	|由于工作循环，传输将延迟|
|LORAWAN_STATUS_NO_CHANNEL_FOUND	|-1021	|目前尚未启用任何频道|
|LORAWAN_STATUS_NO_FREE_CHANNEL_FOUND	|-1022	|标记使用的所有频道，此刻找不到免费频道|
|LORAWAN_STATUS_METADATA_NOT_AVAILABLE	|-1023	|元数据陈旧，无法提供，因为它不相关|
您可以在下面找到 'LoRaWANInterface' 和 'LoRaRadio' 类的 API 文档：

+ [LoRaWANInterface API 文档](https://os.mbed.com/docs/v5.9/reference/lorawan.html): 为 LoRaWAN 网络栈提供 API 的类。
+ [LoRaRadio API 文档](https://os.mbed.com/docs/v5.9/reference/loraradio-api.html): 提供纯虚拟 API 以实现 LoRa 无线电驱动程序的类。