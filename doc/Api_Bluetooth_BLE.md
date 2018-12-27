## BLE
蓝牙低功耗（BLE）是用于构建个人区域网络的低功率无线技术标准。BLE 的典型应用是医疗保健，健身追踪器，信标，智能家居，安全，娱乐，接近传感器，工业和汽车。

Arm Mbed BLE，也称为 BLE_API，是 Mbed 的蓝牙低功耗软件解决方案。许多 Mbed 目标和组件支持 Mbed BLE。开发人员可以使用它来创建新的支持 BLE 的应用程序。

Mbed 的 BLE_API 与平台上的 BLE 控制器接口。它隐藏了 BLE 堆栈在 C++ 抽象背后的复杂性，并且与所有支持 BLE 的 Mbed 平台兼容。Mbed OS BLE_API 自动配置时钟，定时器和其他硬件外设，以最低功耗工作。

### BLE_API，桥接和栈
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/BLEDiagram.png"></div>
您可以使用 Mbed OS，BLE_API 和控制器特定的蓝牙栈以及一些桥接软件构建 BLE 应用程序，以使其适应 BLE_API：

+ BLE_API 如上所述。
+ 桥接软件特定于每个供应商的平台。它为 BLE_API 提供的接口提供实例化，并帮助驱动底层控制器和蓝牙栈。
+ 蓝牙栈实现蓝牙协议并且特定于控制器，因此使用不同控制器的供应商可以提供不同的栈。

### 在 BLE_API 里面
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Inside_API.png"></div>

BLE_API 提供构建块来帮助构建应用程序。这些分为两大类：

1. 在 ble/表达 BLE 结构的接口，例如 GAP，GATT，服务和特性。

2. ble/services 下的类为许多常用的 GATT 配置文件提供参考实现。'services/' 下的代码不是必需的，但它是原型设计的有用起点。我们继续实施标准的 GATT 配置文件。

### BLEDevice 类和头文件

Mbed 的 BLE_API 的入口点是使用标题 ble/BLE.h 可访问的 BLE 类。此类允许您获取 BLE 对象，该对象包含规范兼容的 BLE 设备的基本属性，并且可以与任何 BLE 无线电一起使用：
```
#include "ble/BLE.h"
 
BLE& mydevicename = BLE::Instance();
```
该类的成员函数可以按目的划分：

1. 基本 BLE 操作，例如初始化控制器。

2. 管理 GAP，GATT 或安全性的蓝牙模块的访问者。

### 用法

1. 设置广告和连接模式。
2. 将 UUID 分配给服务及其特性。
3. 创建输入特征。
4. 构造一个服务类并将其添加到 BLE 栈。
5. 特征值更改时推送通知。

## BLE 类参考
[BLE 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_1_1_initialization_complete_callback_context.html" rel="nofollow" target="_blank">InitializationCompleteCallbackContext</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_1_1_on_events_to_process_callback_context.html" rel="nofollow" target="_blank">OnEventsToProcessCallbackContext</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">typedef unsigned&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_1_1_on_events_to_process_callback_context.html" rel="nofollow" target="_blank">OnEventsToProcessCallbackContext</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a4b14879c5237c587b37717278834c987" rel="nofollow" target="_blank">OnEventsToProcessCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a42283fcd0e9ba5958ee26b7403909d6b" rel="nofollow" target="_blank">InitializationCompleteCallback_t</a>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_1_1_initialization_complete_callback_context.html" rel="nofollow" target="_blank">InitializationCompleteCallbackContext</a> *context)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a34ed3d22ed0ebe4a66bec2593181754f" rel="nofollow" target="_blank">getInstanceID</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae591142eae56fd2ae1d677d22fdaeaaa" rel="nofollow" target="_blank">onEventsToProcess</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a4b14879c5237c587b37717278834c987" rel="nofollow" target="_blank">OnEventsToProcessCallback_t</a> &amp;on_event_cb)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aa8f76495e44ab778c0af9391e312c795" rel="nofollow" target="_blank">processEvents</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a5a9358c00d6ac18f9c5486db0c7b5f65" rel="nofollow" target="_blank">init</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a42283fcd0e9ba5958ee26b7403909d6b" rel="nofollow" target="_blank">InitializationCompleteCallback_t</a> completion_cb=NULL)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#abbe23b1df8dd57db1cf7d592fdf60102" rel="nofollow" target="_blank">init</a> (T *object, void(T::*completion_cb)(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_1_1_initialization_complete_callback_context.html" rel="nofollow" target="_blank">InitializationCompleteCallbackContext</a> *context))</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae36656b6796cf82e006ff0cea611bda6" rel="nofollow" target="_blank">hasInitialized</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ac0e72aaff398cf87dde77b3b09bb42a8" rel="nofollow" target="_blank">shutdown</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae83495ca8d315703f7469be82af648ba" rel="nofollow" target="_blank">getVersion</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html" rel="nofollow" target="_blank">Gap</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aae3937fec14edc454317597cf21ebce3" rel="nofollow" target="_blank">gap</a> ()</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html" rel="nofollow" target="_blank">Gap</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae251b3141d48569021d8a77c37bf3dc1" rel="nofollow" target="_blank">gap</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html" rel="nofollow" target="_blank">GattServer</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#acd0ee9b0b683296cbcfd2c8b369b3ca4" rel="nofollow" target="_blank">gattServer</a> ()</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html" rel="nofollow" target="_blank">GattServer</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a60c4dc93f2fdcf11ef8e3b6177da76b5" rel="nofollow" target="_blank">gattServer</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html" rel="nofollow" target="_blank">GattClient</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a0095fd6deccda47a5f5031de5cae915f" rel="nofollow" target="_blank">gattClient</a> ()</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html" rel="nofollow" target="_blank">GattClient</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#afd85b8453ee2020b3532cb8491909863" rel="nofollow" target="_blank">gattClient</a> () const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html" rel="nofollow" target="_blank">SecurityManager</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#af64b07545f7144367951e0d01797515b" rel="nofollow" target="_blank">securityManager</a> ()</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html" rel="nofollow" target="_blank">SecurityManager</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ad94f5f59b90bd6b58cb96e38116e8c03" rel="nofollow" target="_blank">securityManager</a> () const</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a550c43e4a56226357167c3d264c88346" rel="nofollow" target="_blank">BLE</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a> instanceID=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2e32eea101f05a709d0b17c33ce39c8b" rel="nofollow" target="_blank">DEFAULT_INSTANCE</a>)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#adc0ea789747f338fd12a0945d4d97e11" rel="nofollow" target="_blank">waitForEvent</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a877d56e896f73b5a4ed00928c22b9c26" rel="nofollow" target="_blank">setAddress</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> type, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> address)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a3bcea4c1e556f36faeab3b4b39fc662d" rel="nofollow" target="_blank">getAddress</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> *typeP, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> address)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#af0aae9cfe146e1f7b8ed3f4432e0ef79" rel="nofollow" target="_blank">setAdvertisingType</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html#aa838a6e9b6ef22f0edd9a18079510331" rel="nofollow" target="_blank">GapAdvertisingParams::AdvertisingType</a> advType)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a42a76117705689b64b449d355ec5854e" rel="nofollow" target="_blank">setAdvertisingInterval</a> (uint16_t interval)</td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a0b822352b51751ef15285f0680944a7c" rel="nofollow" target="_blank">getMinAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ac7814711bafb43c7c7eb5ddd461b321d" rel="nofollow" target="_blank">getMinNonConnectableAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a38632bc8c077218e30b12bace95c7ac0" rel="nofollow" target="_blank">getMaxAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a4514bc50c13d2770b44f15a235abe880" rel="nofollow" target="_blank">setAdvertisingTimeout</a> (uint16_t timeout)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a6c5eb3d4cdbc63860d2a8590b9c825e6" rel="nofollow" target="_blank">setAdvertisingParams</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a> &amp;advParams)</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2f72b5cb0f8f29beb58ee85218dc7a0e" rel="nofollow" target="_blank">getAdvertisingParams</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a615617a3b2f8983c9ceb4beca9f1036d" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (uint8_t flags)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ab720e9a9fdb9da3f0eb0aa827a2a11e7" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> app)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aadc260a71eadae4d8743c85aa2899bec" rel="nofollow" target="_blank">accumulateAdvertisingPayloadTxPower</a> (int8_t power)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a5cf4219d040276dddc7c8e9169e049e1" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a061f7debe69c2e03281a5bef0a364ef2" rel="nofollow" target="_blank">GapAdvertisingData::DataType</a> type, const uint8_t *data, uint8_t len)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a6708627efaaab6e0ecfe719bbecb5b6f" rel="nofollow" target="_blank">setAdvertisingData</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a> &amp;advData)</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a1f041ca2183f13c09d1d0c82f115a265" rel="nofollow" target="_blank">getAdvertisingData</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a3afd655ab0b586f79e9ad7da8373eafb" rel="nofollow" target="_blank">clearAdvertisingPayload</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ac65405627878ce2e5186308d066f3640" rel="nofollow" target="_blank">setAdvertisingPayload</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#af055c03bc0846ab85a32f5daaffc215f" rel="nofollow" target="_blank">accumulateScanResponse</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a061f7debe69c2e03281a5bef0a364ef2" rel="nofollow" target="_blank">GapAdvertisingData::DataType</a> type, const uint8_t *data, uint8_t len)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae993eafc07931348d9bc9549461b3233" rel="nofollow" target="_blank">clearScanResponse</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a9d6ee3a38ac4d66399321c4c033c0e89" rel="nofollow" target="_blank">startAdvertising</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a507dc45c0a273cf43bf73c74f09d388a" rel="nofollow" target="_blank">stopAdvertising</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a66881eee6f78f427a15bcaf3f3231bc4" rel="nofollow" target="_blank">setScanParams</a> (uint16_t interval=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html#af174646a891030da3662274d75ec1263" rel="nofollow" target="_blank">GapScanningParams::SCAN_INTERVAL_MAX</a>, uint16_t window=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html#a83586bf09561d0f00b26184f1a5d4e69" rel="nofollow" target="_blank">GapScanningParams::SCAN_WINDOW_MAX</a>, uint16_t timeout=0, bool activeScanning=false)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ad8a33db1fc9d2240b72b0f890ce78418" rel="nofollow" target="_blank">setScanInterval</a> (uint16_t interval)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a1e18bb1896a1515321806ff16b5f443f" rel="nofollow" target="_blank">setScanWindow</a> (uint16_t window)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae235f9685c6931b4d98305ccb5c8be4e" rel="nofollow" target="_blank">setScanTimeout</a> (uint16_t timeout)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ab30de7e32f7b366c412fe48aea671f4c" rel="nofollow" target="_blank">setActiveScan</a> (bool activeScanning)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a3e60513a8541b30258f05eda4f8961d8" rel="nofollow" target="_blank">startScan</a> (void(*callback)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">Gap::AdvertisementCallbackParams_t</a> *params))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ac70826ae36b348517611003103a46a4b" rel="nofollow" target="_blank">startScan</a> (T *object, void(T::*memberCallback)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">Gap::AdvertisementCallbackParams_t</a> *params))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a0f7f4d64a734ce57156136649bba9f68" rel="nofollow" target="_blank">stopScan</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a755e1d73742deb3a7f034f77e4bf6267" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> peerAddrType=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367da6f78811fdcccf1055e1014cb6cd5bd7f" rel="nofollow" target="_blank">BLEProtocol::AddressType::RANDOM_STATIC</a>, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">Gap::ConnectionParams_t</a> *connectionParams=NULL, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> *scanParams=NULL)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#adadd619814a93b253f7965f9abbd551a" rel="nofollow" target="_blank">disconnect</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">Gap::DisconnectionReason_t</a> reason)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a21241a5fd1202c0b57cc9492397e6715" rel="nofollow" target="_blank">disconnect</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">Gap::DisconnectionReason_t</a> reason)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_gap_state__t.html" rel="nofollow" target="_blank">Gap::GapState_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aeafd00fe946224fb51e764cc285cff9f" rel="nofollow" target="_blank">getGapState</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a3f09fa88ee2ac2282e75d81663e99652" rel="nofollow" target="_blank">getPreferredConnectionParams</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">Gap::ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a8bb3efe756fb78f56e29bdf5ea4c271d" rel="nofollow" target="_blank">setPreferredConnectionParams</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">Gap::ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a43a5259c44db36eb6d9181aad3730ce7" rel="nofollow" target="_blank">updateConnectionParams</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> handle, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">Gap::ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2f0b53d47df8a3fc445d24f72edc47e5" rel="nofollow" target="_blank">setDeviceName</a> (const uint8_t *deviceName)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a3a3376aa7760b867e2756f1d4a413701" rel="nofollow" target="_blank">getDeviceName</a> (uint8_t *deviceName, unsigned *lengthP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a0a05bf7736b58abfdc0d7ec0461a80ac" rel="nofollow" target="_blank">setAppearance</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> appearance)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ac1e38d23beee8828bf7188e97761bcda" rel="nofollow" target="_blank">getAppearance</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> *appearanceP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a9bdcb88083b323d38a06d38179b1fd2b" rel="nofollow" target="_blank">setTxPower</a> (int8_t txPower)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a299ec8f1d88045bbac6d554a6c4bb1f0" rel="nofollow" target="_blank">getPermittedTxPowerValues</a> (const int8_t **valueArrayPP, size_t *countP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae7f0ede283278e029e7c5d219a539443" rel="nofollow" target="_blank">addService</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_service.html" rel="nofollow" target="_blank">GattService</a> &amp;service)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2411cef0db445efdc962021ab31d9470" rel="nofollow" target="_blank">readCharacteristicValue</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, uint8_t *buffer, uint16_t *lengthP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a8d592ac8d859fa4874d8cbde37ba2627" rel="nofollow" target="_blank">readCharacteristicValue</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, uint8_t *buffer, uint16_t *lengthP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae922ac076b0e6ecc27535f8e04ff6437" rel="nofollow" target="_blank">updateCharacteristicValue</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, const uint8_t *value, uint16_t size, bool localOnly=false)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a4981d4cd3f36795be8cce45636f781bc" rel="nofollow" target="_blank">updateCharacteristicValue</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, const uint8_t *value, uint16_t size, bool localOnly=false)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a9a1a0fe3254ea8761819a04cda387e2d" rel="nofollow" target="_blank">initializeSecurity</a> (bool enableBonding=true, bool requireMITM=true, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityManager::SecurityIOCapabilities_t</a> iocaps=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2aa9938c31732f4393e6713fcdbb8ae004" rel="nofollow" target="_blank">SecurityManager::IO_CAPS_NONE</a>, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">SecurityManager::Passkey_t</a> passkey=NULL)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aa2aa4f4e7994c3c481ef2b909b821835" rel="nofollow" target="_blank">getLinkSecurity</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181" rel="nofollow" target="_blank">SecurityManager::LinkSecurityStatus_t</a> *securityStatusP)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ab4e7309eb910ec963073307fdcae5775" rel="nofollow" target="_blank">purgeAllBondingState</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aa023052c37b50c72d88e7fc8e02689ec" rel="nofollow" target="_blank">onTimeout</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a254c7b52393a4e0f8fd6952e3c2cc6a3" rel="nofollow" target="_blank">Gap::TimeoutEventCallback_t</a> timeoutCallback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a610ec115ab0465b35a16fd16bc3d557b" rel="nofollow" target="_blank">onConnection</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a5259ebdc579c7642827dc50730f2e5ac" rel="nofollow" target="_blank">Gap::ConnectionEventCallback_t</a> connectionCallback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ae4bdcd75e657ce344b929b6fec2e50c5" rel="nofollow" target="_blank">onDisconnection</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa7569b0353d271bc8001058d5c953cbe" rel="nofollow" target="_blank">Gap::DisconnectionEventCallback_t</a> disconnectionCallback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ad13b2986c42d847d9f63a7b84f6afa80" rel="nofollow" target="_blank">onDisconnection</a> (T *tptr, void(T::*mptr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_disconnection_callback_params__t.html" rel="nofollow" target="_blank">Gap::DisconnectionCallbackParams_t</a> *))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a740024be6e1e7fb43e12a8ab9461d5e3" rel="nofollow" target="_blank">onRadioNotification</a> (void(*callback)(bool))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#ab91b734dfb5c0b6855812d0e616afc35" rel="nofollow" target="_blank">onDataSent</a> (void(*callback)(unsigned count))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a31b9f7c51a402db1484e1940c9d31632" rel="nofollow" target="_blank">onDataSent</a> (T *objPtr, void(T::*memberPtr)(unsigned count))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a84eb1fefbf57fcabf206a02ece660ee2" rel="nofollow" target="_blank">onDataWritten</a> (void(*callback)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> *eventDataP))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a4194a07e63e6dba496bba5581265c853" rel="nofollow" target="_blank">onDataWritten</a> (T *objPtr, void(T::*memberPtr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> *context))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2b22c1b2394a892065699ddebe1cc71c" rel="nofollow" target="_blank">onDataRead</a> (void(*callback)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> *eventDataP))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a0b18a0feb3d2751df5d9e998f53ef391" rel="nofollow" target="_blank">onDataRead</a> (T *objPtr, void(T::*memberPtr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> *context))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a93a980eed1d5bca04a69e2e5e5a9b008" rel="nofollow" target="_blank">onUpdatesEnabled</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">GattServer::EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aae3d8df40510ab4109310df2f85efd2c" rel="nofollow" target="_blank">onUpdatesDisabled</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">GattServer::EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#abd75598f959adbf453b7040f434a1e8d" rel="nofollow" target="_blank">onConfirmationReceived</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">GattServer::EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aba6192b2ae712daeefa84111c3499b2c" rel="nofollow" target="_blank">onSecuritySetupInitiated</a> (SecurityManager::SecuritySetupInitiatedCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a464902c8b29b0487cfc00e0593faeeb5" rel="nofollow" target="_blank">onSecuritySetupCompleted</a> (SecurityManager::SecuritySetupCompletedCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aae10c63e4b202cdf6cdca1920be26dcf" rel="nofollow" target="_blank">onLinkSecured</a> (SecurityManager::LinkSecuredCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#abd17d58883333fa19326b0151579e35c" rel="nofollow" target="_blank">onSecurityContextStored</a> (SecurityManager::HandleSpecificEvent_t callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a9802bf7e8237bddbff3c1944fec25d5f" rel="nofollow" target="_blank">onPasskeyDisplay</a> (SecurityManager::PasskeyDisplayCallback_t callback)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#aaa79d87959c84e6b85ce8bac58a8322e" rel="nofollow" target="_blank">Instance</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a> id=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2e32eea101f05a709d0b17c33ce39c8b" rel="nofollow" target="_blank">DEFAULT_INSTANCE</a>)</td>
		</tr><tr><td style="vertical-align:top;">static const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a6ddb72506267a09906eb7d0c8637ca0f" rel="nofollow" target="_blank">errorToString</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__platform__error.html#gae04dbb69042f37c4c595fc9beb4ca754" rel="nofollow" target="_blank">error</a>)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2"><a name="pub-static-attribs" target="_blank"></a> Static Public Attributes</td>
		</tr><tr><td style="vertical-align:top;">static const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2e32eea101f05a709d0b17c33ce39c8b" rel="nofollow" target="_blank">DEFAULT_INSTANCE</a> = 0</td>
		</tr><tr><td style="vertical-align:top;">static const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#a2484cf6aa39b0ac663bf0ecb13de996e" rel="nofollow" target="_blank">InstanceID_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html#af1f046db9b72a14bc8f4dff5881c047e" rel="nofollow" target="_blank">NUM_INSTANCES</a> = 1</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2"><a name="friends" target="_blank"></a> Friends</td>
		</tr><tr><td style="vertical-align:top;"><a id="a792920a99fc759d853d340543ae6c45c" target="_blank"></a> class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>BLEInstanceBase</strong></td>
		</tr></tbody></table>

## 示例：BLE 信标
这是一个演示如何创建 BLE 信标的示例。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-Beacon/file/abc2d39dfdde/source/main.cpp)   
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2015 ARM Limited
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
 
#include <events/mbed_events.h>
#include <mbed.h>
#include "ble/BLE.h"
#include "ble/services/iBeacon.h"
 
static iBeacon* ibeaconPtr;
 
static EventQueue eventQueue(/* event count */ 4 * EVENTS_EVENT_SIZE);
 
/**
 * This function is called when the ble initialization process has failled
 */
void onBleInitError(BLE &ble, ble_error_t error)
{
    /* Initialization error handling should go here */
}
 
/**
 * Callback triggered when the ble initialization process has finished
 */
void bleInitComplete(BLE::InitializationCompleteCallbackContext *params)
{
    BLE&        ble   = params->ble;
    ble_error_t error = params->error;
 
    if (error != BLE_ERROR_NONE) {
        /* In case of error, forward the error handling to onBleInitError */
        onBleInitError(ble, error);
        return;
    }
 
    /* Ensure that it is the default instance of BLE */
    if(ble.getInstanceID() != BLE::DEFAULT_INSTANCE) {
        return;
    }
 
    /**
     * The Beacon payload has the following composition:
     * 128-Bit / 16byte UUID = E2 0A 39 F4 73 F5 4B C4 A1 2F 17 D1 AD 07 A9 61
     * Major/Minor  = 0x1122 / 0x3344
     * Tx Power     = 0xC8 = 200, 2's compliment is 256-200 = (-56dB)
     *
     * Note: please remember to calibrate your beacons TX Power for more accurate results.
     */
    static const uint8_t uuid[] = {0xE2, 0x0A, 0x39, 0xF4, 0x73, 0xF5, 0x4B, 0xC4,
                                   0xA1, 0x2F, 0x17, 0xD1, 0xAD, 0x07, 0xA9, 0x61};
    uint16_t majorNumber = 1122;
    uint16_t minorNumber = 3344;
    uint16_t txPower     = 0xC8;
    ibeaconPtr = new iBeacon(ble, uuid, majorNumber, minorNumber, txPower);
 
    ble.gap().setAdvertisingInterval(1000); /* 1000ms. */
    ble.gap().startAdvertising();
}
 
void scheduleBleEventsProcessing(BLE::OnEventsToProcessCallbackContext* context) {
    BLE &ble = BLE::Instance();
    eventQueue.call(Callback<void()>(&ble, &BLE::processEvents));
}
 
int main()
{
    BLE &ble = BLE::Instance();
    ble.onEventsToProcess(scheduleBleEventsProcessing);
    ble.init(bleInitComplete);
 
    eventQueue.dispatch_forever();
 
    return 0;
}
```
## 示例：BLE 心率监测器
这是一个示例，演示如何构建可由 BLE 客户端（如手机）连接和监控的心率传感器。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-HeartRate/file/b36aa157781d/source/main.cpp)
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2015 ARM Limited
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
 
#include <events/mbed_events.h>
#include <mbed.h>
#include "ble/BLE.h"
#include "ble/Gap.h"
#include "ble/services/HeartRateService.h"
 
DigitalOut led1(LED1, 1);
 
const static char     DEVICE_NAME[] = "HRM";
static const uint16_t uuid16_list[] = {GattService::UUID_HEART_RATE_SERVICE};
 
static uint8_t hrmCounter = 100; // init HRM to 100bps
static HeartRateService *hrServicePtr;
 
static EventQueue eventQueue(/* event count */ 16 * EVENTS_EVENT_SIZE);
 
void disconnectionCallback(const Gap::DisconnectionCallbackParams_t *params)
{
    BLE::Instance().gap().startAdvertising(); // restart advertising
}
 
void updateSensorValue() {
    // Do blocking calls or whatever is necessary for sensor polling.
    // In our case, we simply update the HRM measurement.
    hrmCounter++;
 
    //  100 <= HRM bps <=175
    if (hrmCounter == 175) {
        hrmCounter = 100;
    }
 
    hrServicePtr->updateHeartRate(hrmCounter);
}
 
void periodicCallback(void)
{
    led1 = !led1; /* Do blinky on LED1 while we're waiting for BLE events */
 
    if (BLE::Instance().getGapState().connected) {
        eventQueue.call(updateSensorValue);
    }
}
 
void onBleInitError(BLE &ble, ble_error_t error)
{
    (void)ble;
    (void)error;
   /* Initialization error handling should go here */
}
 
void bleInitComplete(BLE::InitializationCompleteCallbackContext *params)
{
    BLE&        ble   = params->ble;
    ble_error_t error = params->error;
 
    if (error != BLE_ERROR_NONE) {
        onBleInitError(ble, error);
        return;
    }
 
    if (ble.getInstanceID() != BLE::DEFAULT_INSTANCE) {
        return;
    }
 
    ble.gap().onDisconnection(disconnectionCallback);
 
    /* Setup primary service. */
    hrServicePtr = new HeartRateService(ble, hrmCounter, HeartRateService::LOCATION_FINGER);
 
    /* Setup advertising. */
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::BREDR_NOT_SUPPORTED | GapAdvertisingData::LE_GENERAL_DISCOVERABLE);
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LIST_16BIT_SERVICE_IDS, (uint8_t *)uuid16_list, sizeof(uuid16_list));
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::GENERIC_HEART_RATE_SENSOR);
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LOCAL_NAME, (uint8_t *)DEVICE_NAME, sizeof(DEVICE_NAME));
    ble.gap().setAdvertisingType(GapAdvertisingParams::ADV_CONNECTABLE_UNDIRECTED);
    ble.gap().setAdvertisingInterval(1000); /* 1000ms */
    ble.gap().startAdvertising();
}
 
void scheduleBleEventsProcessing(BLE::OnEventsToProcessCallbackContext* context) {
    BLE &ble = BLE::Instance();
    eventQueue.call(Callback<void()>(&ble, &BLE::processEvents));
}
 
int main()
{
    eventQueue.call_every(500, periodicCallback);
 
    BLE &ble = BLE::Instance();
    ble.onEventsToProcess(scheduleBleEventsProcessing);
    ble.init(bleInitComplete);
 
    eventQueue.dispatch_forever();
 
    return 0;
}
```