## GattServer
GattServer 是 GattServices 的集合。这些服务包含连接到设备的对等体可以读取或写入的特征。这些特征还可能在订阅客户端的值发生更改时发出更新。

### 服务器布局

应用程序代码可以在函数 addService() 的帮助下将 GattService 对象添加到服务器。该函数注册服务中包含的所有 GattCharacteristics，以及这些特性包含的所有特征描述符（请参阅 GattAttribute）。服务注册为作为服务一部分的各种属性分配唯一句柄。用户必须使用此句柄来读取或写入这些组件。

没有定义的原语可以删除单个服务；但是，调用函数 reset() 会删除先前在 GattServer 中注册的所有服务。

### 特征和属性访问

在注册服务时，必须通过分配给它们的句柄访问 GattServer 中存在的特性和特征描述符的值。GattServer 类提供了几种类型的 read() 和 write() 函数，用于检索或改变属性值。

您可以通过调用函数 areUpdatesEnabled() 来查询服务器，以查明客户端是否已订阅给定特征的值更新。

### 事件

您可以使用 GattServer 注册多个事件处理程序，它将调用它来通知您客户端（连接到服务器的远程应用程序）和服务器活动：

+ onDataSent: 向 GattServer 注册一个事件处理程序，它将调用它以在向客户端发送特征值更新时通知您。
+ onDataWriten: 向 GattServer 注册事件处理程序，当客户端编写服务器属性时，它将调用该处理程序以通知您。
+ onDataRead: 向 GattServer 注册一个事件处理程序，当客户端读取服务器的属性时，它将调用该处理程序来通知您。
+ onUpdatesEnabled: 向 GattServer 注册一个事件处理程序，当客户端订阅特征的更新时，它会调用该处理程序来通知您。
+ onUpdatesDisabled: 向 GattServer 注册一个事件处理程序，当客户端取消订阅特征的更新时，它会调用该处理程序来通知您。
+ onConfimationReceived: 向 GattServer 注册事件处理程序，当客户端确认特征值通知时，它将调用该处理程序以通知您。
当启动的服务器的性质不相关时，术语特征值更新表示特征值通知和特征值指示。

## GattServer 类参考
[GattServer 类参考](https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; unsigned &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a721162c6683c20fcb0a38fc1b77631e9" rel="nofollow" target="_blank">DataSentCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; unsigned &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a219ee87e2b19b6208e82aefc5497e7d2" rel="nofollow" target="_blank">DataSentCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a63296908418c65b00952672226ddfb1a" rel="nofollow" target="_blank">DataWrittenCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a55b0769c38640c2f4055b6b2217f56ef" rel="nofollow" target="_blank">DataWrittenCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a345efb3a2d8615defee12ab67bd18e3a" rel="nofollow" target="_blank">DataReadCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a3b8838dff545d0250cf2bec4371364c5" rel="nofollow" target="_blank">DataReadCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html" rel="nofollow" target="_blank">GattServer</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a8f81032bce7f110ea1682f4875a08af1" rel="nofollow" target="_blank">GattServerShutdownCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html" rel="nofollow" target="_blank">GattServer</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ac94edfd570c2637aaff813a62031e30b" rel="nofollow" target="_blank">GattServerShutdownCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">EventCallback_t</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ada8f01c3a8f1bb55accd8ef6d369c76c" rel="nofollow" target="_blank">addService</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_service.html" rel="nofollow" target="_blank">GattService</a> &amp;service)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ab6c16fc80735c22dc9ba0274af337271" rel="nofollow" target="_blank">read</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, uint8_t buffer[], uint16_t *lengthP)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ad1b8267d8f7ebdf2981b9095523b7603" rel="nofollow" target="_blank">read</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, uint8_t *buffer, uint16_t *lengthP)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a7bd0af459475d4c8ee1cd42d659af9d0" rel="nofollow" target="_blank">write</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, const uint8_t *value, uint16_t size, bool localOnly=false)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a9673b9624b234b3b6d833aa5de036327" rel="nofollow" target="_blank">write</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, const uint8_t *value, uint16_t size, bool localOnly=false)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a22270a931284e1d49cc3eccdcf80b1fe" rel="nofollow" target="_blank">areUpdatesEnabled</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_characteristic.html" rel="nofollow" target="_blank">GattCharacteristic</a> &amp;characteristic, bool *enabledP)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#abf3af0dd8cd9326e693e1d0be8e7c861" rel="nofollow" target="_blank">areUpdatesEnabled</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_characteristic.html" rel="nofollow" target="_blank">GattCharacteristic</a> &amp;characteristic, bool *enabledP)</td>
		</tr><tr><td style="vertical-align:top;">virtual bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#aedb73714f81af4e549292cb0c082692f" rel="nofollow" target="_blank">isOnDataReadAvailable</a> () const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a888e8891903ce6345223972b8ca8fc7d" rel="nofollow" target="_blank">onDataSent</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a721162c6683c20fcb0a38fc1b77631e9" rel="nofollow" target="_blank">DataSentCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a1cd84517aa7082cb5002a6b9b94c2ea0" rel="nofollow" target="_blank">onDataSent</a> (T *objPtr, void(T::*memberPtr)(unsigned count))</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a219ee87e2b19b6208e82aefc5497e7d2" rel="nofollow" target="_blank">DataSentCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a7bf1c9b1ec154b5a5801857d2c661dc0" rel="nofollow" target="_blank">onDataSent</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a6e8103ed4fdbb62189d56170c20c4369" rel="nofollow" target="_blank">onDataWritten</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a63296908418c65b00952672226ddfb1a" rel="nofollow" target="_blank">DataWrittenCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a13485b68d11235a15e71ce82dbe44aaa" rel="nofollow" target="_blank">onDataWritten</a> (T *objPtr, void(T::*memberPtr)(const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> *context))</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a55b0769c38640c2f4055b6b2217f56ef" rel="nofollow" target="_blank">DataWrittenCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ac57919e0307d974d63cd984cc3b627a1" rel="nofollow" target="_blank">onDataWritten</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a5f60d44646bf8dd283af803b93c5ac82" rel="nofollow" target="_blank">onDataRead</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a345efb3a2d8615defee12ab67bd18e3a" rel="nofollow" target="_blank">DataReadCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a691aeb7b1f8f469f18a65203cd911b74" rel="nofollow" target="_blank">onDataRead</a> (T *objPtr, void(T::*memberPtr)(const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> *context))</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a3b8838dff545d0250cf2bec4371364c5" rel="nofollow" target="_blank">DataReadCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a08a3970da73f0eb367028ad9d4c729f1" rel="nofollow" target="_blank">onDataRead</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a70cc2dca58caaf58814ca779302b24b6" rel="nofollow" target="_blank">onShutdown</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a8f81032bce7f110ea1682f4875a08af1" rel="nofollow" target="_blank">GattServerShutdownCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#afa4c34ae58fc7e9d815e47c90a5ffe6f" rel="nofollow" target="_blank">onShutdown</a> (T *objPtr, void(T::*memberPtr)(const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html" rel="nofollow" target="_blank">GattServer</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ac94edfd570c2637aaff813a62031e30b" rel="nofollow" target="_blank">GattServerShutdownCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#aa06fd7a79f85fed53064d8e7d86b8fd4" rel="nofollow" target="_blank">onShutdown</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a3332d8e545ceca0935931a8749d0f634" rel="nofollow" target="_blank">onUpdatesEnabled</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a8c28a0807459914f12daeafe4e8eb170" rel="nofollow" target="_blank">onUpdatesDisabled</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a6d76eb3509d3e254ad784f321711f478" rel="nofollow" target="_blank">onConfirmationReceived</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a318e00666c33201a3e3adb7943768e15" rel="nofollow" target="_blank">EventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ad73b39805dcca6c2de663e63ee455965" rel="nofollow" target="_blank">reset</a> (void)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a3f123b33b3d3efbfe451fa3010621905" rel="nofollow" target="_blank">GattServer</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a64268127be58f4f2afd76a3f4fa4a150" rel="nofollow" target="_blank">handleDataWrittenEvent</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#ad43f5d774dc7fe8b25c480de2a7b8801" rel="nofollow" target="_blank">handleDataReadEvent</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a9819bae24e178ce15eb9817eb24df226" rel="nofollow" target="_blank">handleEvent</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server_events.html#aa5b9a0237bb2e56eecc8dc70b67154d9" rel="nofollow" target="_blank">GattServerEvents::gattEvent_e</a> type, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a2c90c27712f558a7a87fde10757b3359" rel="nofollow" target="_blank">handleDataSentEvent</a> (unsigned count)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;">uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a315e8d185b089aa2b955dd90eeb4ab93" rel="nofollow" target="_blank">serviceCount</a></td>
		</tr><tr><td style="vertical-align:top;">uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_server.html#a6fc68806867d04062edafb228dbf1ef6" rel="nofollow" target="_blank">characteristicCount</a></td>
		</tr></tbody></table>

## GattServer 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-GattServer/file/8fbed496a023/main.cpp)      
```
/* mbed Microcontroller Library
 * Copyright (c) 2017 ARM Limited
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
 
#include <stdio.h>
 
#include "platform/Callback.h"
#include "events/EventQueue.h"
#include "platform/NonCopyable.h"
 
#include "ble/BLE.h"
#include "ble/Gap.h"
#include "ble/GattClient.h"
#include "ble/GapAdvertisingParams.h"
#include "ble/GapAdvertisingData.h"
#include "ble/GattServer.h"
#include "BLEProcess.h"
 
using mbed::callback;
 
/**
 * A Clock service that demonstrate the GattServer features.
 *
 * The clock service host three characteristics that model the current hour,
 * minute and second of the clock. The value of the second characteristic is
 * incremented automatically by the system.
 *
 * A client can subscribe to updates of the clock characteristics and get
 * notified when one of the value is changed. Clients can also change value of
 * the second, minute and hour characteristric.
 */
class ClockService {
    typedef ClockService Self;
 
public:
    ClockService() :
        _hour_char("485f4145-52b9-4644-af1f-7a6b9322490f", 0),
        _minute_char("0a924ca7-87cd-4699-a3bd-abdcd9cf126a", 0),
        _second_char("8dd6a1b7-bc75-4741-8a26-264af75807de", 0),
        _clock_service(
            /* uuid */ "51311102-030e-485f-b122-f8f381aa84ed",
            /* characteristics */ _clock_characteristics,
            /* numCharacteristics */ sizeof(_clock_characteristics) /
                                     sizeof(_clock_characteristics[0])
        ),
        _server(NULL),
        _event_queue(NULL)
    {
        // update internal pointers (value, descriptors and characteristics array)
        _clock_characteristics[0] = &_hour_char;
        _clock_characteristics[1] = &_minute_char;
        _clock_characteristics[2] = &_second_char;
 
        // setup authorization handlers
        _hour_char.setWriteAuthorizationCallback(this, &Self::authorize_client_write);
        _minute_char.setWriteAuthorizationCallback(this, &Self::authorize_client_write);
        _second_char.setWriteAuthorizationCallback(this, &Self::authorize_client_write);
    }
 
 
 
    void start(BLE &ble_interface, events::EventQueue &event_queue)
    {
         if (_event_queue) {
            return;
        }
 
        _server = &ble_interface.gattServer();
        _event_queue = &event_queue;
 
        // register the service
        printf("Adding demo service\r\n");
        ble_error_t err = _server->addService(_clock_service);
 
        if (err) {
            printf("Error %u during demo service registration.\r\n", err);
            return;
        }
 
        // read write handler
        _server->onDataSent(as_cb(&Self::when_data_sent));
        _server->onDataWritten(as_cb(&Self::when_data_written));
        _server->onDataRead(as_cb(&Self::when_data_read));
 
        // updates subscribtion handlers
        _server->onUpdatesEnabled(as_cb(&Self::when_update_enabled));
        _server->onUpdatesDisabled(as_cb(&Self::when_update_disabled));
        _server->onConfirmationReceived(as_cb(&Self::when_confirmation_received));
 
        // print the handles
        printf("clock service registered\r\n");
        printf("service handle: %u\r\n", _clock_service.getHandle());
        printf("\thour characteristic value handle %u\r\n", _hour_char.getValueHandle());
        printf("\tminute characteristic value handle %u\r\n", _minute_char.getValueHandle());
        printf("\tsecond characteristic value handle %u\r\n", _second_char.getValueHandle());
 
        _event_queue->call_every(1000 /* ms */, callback(this, &Self::increment_second));
    }
 
private:
 
    /**
     * Handler called when a notification or an indication has been sent.
     */
    void when_data_sent(unsigned count)
    {
        printf("sent %u updates\r\n", count);
    }
 
    /**
     * Handler called after an attribute has been written.
     */
    void when_data_written(const GattWriteCallbackParams *e)
    {
        printf("data written:\r\n");
        printf("\tconnection handle: %u\r\n", e->connHandle);
        printf("\tattribute handle: %u", e->handle);
        if (e->handle == _hour_char.getValueHandle()) {
            printf(" (hour characteristic)\r\n");
        } else if (e->handle == _minute_char.getValueHandle()) {
            printf(" (minute characteristic)\r\n");
        } else if (e->handle == _second_char.getValueHandle()) {
            printf(" (second characteristic)\r\n");
        } else {
            printf("\r\n");
        }
        printf("\twrite operation: %u\r\n", e->writeOp);
        printf("\toffset: %u\r\n", e->offset);
        printf("\tlength: %u\r\n", e->len);
        printf("\t data: ");
 
        for (size_t i = 0; i < e->len; ++i) {
            printf("%02X", e->data[i]);
        }
 
        printf("\r\n");
    }
 
    /**
     * Handler called after an attribute has been read.
     */
    void when_data_read(const GattReadCallbackParams *e)
    {
        printf("data read:\r\n");
        printf("\tconnection handle: %u\r\n", e->connHandle);
        printf("\tattribute handle: %u", e->handle);
        if (e->handle == _hour_char.getValueHandle()) {
            printf(" (hour characteristic)\r\n");
        } else if (e->handle == _minute_char.getValueHandle()) {
            printf(" (minute characteristic)\r\n");
        } else if (e->handle == _second_char.getValueHandle()) {
            printf(" (second characteristic)\r\n");
        } else {
            printf("\r\n");
        }
    }
 
    /**
     * Handler called after a client has subscribed to notification or indication.
     *
     * @param handle Handle of the characteristic value affected by the change.
     */
    void when_update_enabled(GattAttribute::Handle_t handle)
    {
        printf("update enabled on handle %d\r\n", handle);
    }
 
    /**
     * Handler called after a client has cancelled his subscription from
     * notification or indication.
     *
     * @param handle Handle of the characteristic value affected by the change.
     */
    void when_update_disabled(GattAttribute::Handle_t handle)
    {
        printf("update disabled on handle %d\r\n", handle);
    }
 
    /**
     * Handler called when an indication confirmation has been received.
     *
     * @param handle Handle of the characteristic value that has emitted the
     * indication.
     */
    void when_confirmation_received(GattAttribute::Handle_t handle)
    {
        printf("confirmation received on handle %d\r\n", handle);
    }
 
    /**
     * Handler called when a write request is received.
     *
     * This handler verify that the value submitted by the client is valid before
     * authorizing the operation.
     */
    void authorize_client_write(GattWriteAuthCallbackParams *e)
    {
        printf("characteristic %u write authorization\r\n", e->handle);
 
        if (e->offset != 0) {
            printf("Error invalid offset\r\n");
            e->authorizationReply = AUTH_CALLBACK_REPLY_ATTERR_INVALID_OFFSET;
            return;
        }
 
        if (e->len != 1) {
            printf("Error invalid len\r\n");
            e->authorizationReply = AUTH_CALLBACK_REPLY_ATTERR_INVALID_ATT_VAL_LENGTH;
            return;
        }
 
        if ((e->data[0] >= 60) ||
            ((e->data[0] >= 24) && (e->handle == _hour_char.getValueHandle()))) {
            printf("Error invalid data\r\n");
            e->authorizationReply = AUTH_CALLBACK_REPLY_ATTERR_WRITE_NOT_PERMITTED;
            return;
        }
 
        e->authorizationReply = AUTH_CALLBACK_REPLY_SUCCESS;
    }
 
    /**
     * Increment the second counter.
     */
    void increment_second(void)
    {
        uint8_t second = 0;
        ble_error_t err = _second_char.get(*_server, second);
        if (err) {
            printf("read of the second value returned error %u\r\n", err);
            return;
        }
 
        second = (second + 1) % 60;
 
        err = _second_char.set(*_server, second);
        if (err) {
            printf("write of the second value returned error %u\r\n", err);
            return;
        }
 
        if (second == 0) {
            increment_minute();
        }
    }
 
    /**
     * Increment the minute counter.
     */
    void increment_minute(void)
    {
        uint8_t minute = 0;
        ble_error_t err = _minute_char.get(*_server, minute);
        if (err) {
            printf("read of the minute value returned error %u\r\n", err);
            return;
        }
 
        minute = (minute + 1) % 60;
 
        err = _minute_char.set(*_server, minute);
        if (err) {
            printf("write of the minute value returned error %u\r\n", err);
            return;
        }
 
        if (minute == 0) {
            increment_hour();
        }
    }
 
    /**
     * Increment the hour counter.
     */
    void increment_hour(void)
    {
        uint8_t hour = 0;
        ble_error_t err = _hour_char.get(*_server, hour);
        if (err) {
            printf("read of the hour value returned error %u\r\n", err);
            return;
        }
 
        hour = (hour + 1) % 24;
 
        err = _hour_char.set(*_server, hour);
        if (err) {
            printf("write of the hour value returned error %u\r\n", err);
            return;
        }
    }
 
private:
    /**
     * Helper that construct an event handler from a member function of this
     * instance.
     */
    template<typename Arg>
    FunctionPointerWithContext<Arg> as_cb(void (Self::*member)(Arg))
    {
        return makeFunctionPointer(this, member);
    }
 
    /**
     * Read, Write, Notify, Indicate  Characteristic declaration helper.
     *
     * @tparam T type of data held by the characteristic.
     */
    template<typename T>
    class ReadWriteNotifyIndicateCharacteristic : public GattCharacteristic {
    public:
        /**
         * Construct a characteristic that can be read or written and emit
         * notification or indication.
         *
         * @param[in] uuid The UUID of the characteristic.
         * @param[in] initial_value Initial value contained by the characteristic.
         */
        ReadWriteNotifyIndicateCharacteristic(const UUID & uuid, const T& initial_value) :
            GattCharacteristic(
                /* UUID */ uuid,
                /* Initial value */ &_value,
                /* Value size */ sizeof(_value),
                /* Value capacity */ sizeof(_value),
                /* Properties */ GattCharacteristic::BLE_GATT_CHAR_PROPERTIES_READ |
                                GattCharacteristic::BLE_GATT_CHAR_PROPERTIES_WRITE |
                                GattCharacteristic::BLE_GATT_CHAR_PROPERTIES_NOTIFY |
                                GattCharacteristic::BLE_GATT_CHAR_PROPERTIES_INDICATE,
                /* Descriptors */ NULL,
                /* Num descriptors */ 0,
                /* variable len */ false
            ),
            _value(initial_value) {
        }
 
        /**
         * Get the value of this characteristic.
         *
         * @param[in] server GattServer instance that contain the characteristic
         * value.
         * @param[in] dst Variable that will receive the characteristic value.
         *
         * @return BLE_ERROR_NONE in case of success or an appropriate error code.
         */
        ble_error_t get(GattServer &server, T& dst) const
        {
            uint16_t value_length = sizeof(dst);
            return server.read(getValueHandle(), &dst, &value_length);
        }
 
        /**
         * Assign a new value to this characteristic.
         *
         * @param[in] server GattServer instance that will receive the new value.
         * @param[in] value The new value to set.
         * @param[in] local_only Flag that determine if the change should be kept
         * locally or forwarded to subscribed clients.
         */
        ble_error_t set(
            GattServer &server, const uint8_t &value, bool local_only = false
        ) const {
            return server.write(getValueHandle(), &value, sizeof(value), local_only);
        }
 
    private:
        uint8_t _value;
    };
 
    ReadWriteNotifyIndicateCharacteristic<uint8_t> _hour_char;
    ReadWriteNotifyIndicateCharacteristic<uint8_t> _minute_char;
    ReadWriteNotifyIndicateCharacteristic<uint8_t> _second_char;
 
    // list of the characteristics of the clock service
    GattCharacteristic* _clock_characteristics[3];
 
    // demo service
    GattService _clock_service;
 
    GattServer* _server;
    events::EventQueue *_event_queue;
};
 
int main() {
    BLE &ble_interface = BLE::Instance();
    events::EventQueue event_queue;
    ClockService demo_service;
    BLEProcess ble_process(event_queue, ble_interface);
 
    ble_process.on_init(callback(&demo_service, &ClockService::start));
 
    // bind the event queue to the ble interface, initialize the interface
    // and start advertising
    ble_process.start();
 
    // Process the event queue.
    event_queue.dispatch_forever();
 
    return 0;
}
```