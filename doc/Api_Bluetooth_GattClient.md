## GattClient
GattClient 定义了与远程 GattServer 交互所需的过程。

### 发现程序

GattServer 托管一组固定的服务。这些服务是可以被发现，读取或写入的特征的逻辑组合，并且可以将它们的状态广播到连接的客户端。这些特征还可能包含元信息和命名的特征描述符。特征描述符可以指示用于特征值的单位，以文本形式描述特征目的或允许客户端注册特征值的更新通知。

在与服务器特性进行任何交互之前，GattClient 会发现服务器上存在的服务和特征的布局。

特征描述符的布局也可以作为额外发现步骤发布。

### 属性操作

作为发现过程的结果，客户端可以开始与发现的特征进行交互。根据特征属性（在发现期间获取），客户端可以读取或写入给定特征的值。

Mbed BLE 抽象读取和写入操作，以提供可用于读取或写入特征值的单个 API。如果要传输的属性值不适合单个数据包，则应用程序代码不必处理必要的碎片或重组过程。

### 服务器发起事件

当服务器更新特征值时，它可以将新值转发给任何已注册的客户端。客户可以根据每个特征注册这些更新。服务器使用通知（没有来自客户端的确认）或指示（客户确认收到）发送更新。此机制通过避免轮询来最小化客户端和服务器之间的事务数。

客户端通过设置客户端特性配置描述符（CCCD）值来注册这些更新。这是一个属性，客户端需要发现它的描述符。如果设置了通知或指示属性，则它存在于特征中。

## GattClient 类参考

[GattClient 类参考](https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2a4d527bde20e9d5abbe7bf8fcdd8b9d" rel="nofollow" target="_blank">WriteOp_t</a> { <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2a4d527bde20e9d5abbe7bf8fcdd8b9da1d0302b7fc87d314764f4bf2f5ff14e9" rel="nofollow" target="_blank">GATT_OP_WRITE_REQ</a> = 0x01, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2a4d527bde20e9d5abbe7bf8fcdd8b9dab4dbd9d3db9315b053eb1d9446a15ab8" rel="nofollow" target="_blank">GATT_OP_WRITE_CMD</a> = 0x02, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2a4d527bde20e9d5abbe7bf8fcdd8b9da853c4016700bb22626d3ceec340fa413" rel="nofollow" target="_blank">GATT_OP_SIGNED_WRITE_CMD</a> = 0x03 }</td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a91c3f1ceca1e83fd6671029e7152a04d" rel="nofollow" target="_blank">ReadCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a9c25f59502569c3798a81eb1f11b4b06" rel="nofollow" target="_blank">ReadCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ad4490a567da33690404a236702310a8f" rel="nofollow" target="_blank">WriteCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a5a554494f8f641aebe07a1ae74eec388" rel="nofollow" target="_blank">WriteCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_h_v_x_callback_params.html" rel="nofollow" target="_blank">GattHVXCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a28d969c787488eae2abe3cb0e081a4c0" rel="nofollow" target="_blank">HVXCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_h_v_x_callback_params.html" rel="nofollow" target="_blank">GattHVXCallbackParams</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2db75531892bfbcdea750d37159447b9" rel="nofollow" target="_blank">HVXCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html" rel="nofollow" target="_blank">GattClient</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a4fb489ff1c9461372b71e05667ef275e" rel="nofollow" target="_blank">GattClientShutdownCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html" rel="nofollow" target="_blank">GattClient</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ae40810e14cd488e2d019aea0fd9259b7" rel="nofollow" target="_blank">GattClientShutdownCallbackChain_t</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ac1eb558c1489d52762fdc6efa500abb0" rel="nofollow" target="_blank">launchServiceDiscovery</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_service_discovery.html#a45354db5286f99fc93005c9045200c58" rel="nofollow" target="_blank">ServiceDiscovery::ServiceCallback_t</a> sc=NULL, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_service_discovery.html#abf8d316f21a10c2a8c04b3dfb3eb7cae" rel="nofollow" target="_blank">ServiceDiscovery::CharacteristicCallback_t</a> cc=NULL, const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html" rel="nofollow" target="_blank">UUID</a> &amp;matchingServiceUUID=<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html#ac9f41b22abc7082a5c4477ac896dd2f3" rel="nofollow" target="_blank">UUID::ShortUUIDBytes_t</a>(<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ggadb49720dc49f7d4e4cf9adbf2948e409abbb64a7440ad9bbd4317ee852737f585" rel="nofollow" target="_blank">BLE_UUID_UNKNOWN</a>), const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html" rel="nofollow" target="_blank">UUID</a> &amp;matchingCharacteristicUUIDIn=<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html#ac9f41b22abc7082a5c4477ac896dd2f3" rel="nofollow" target="_blank">UUID::ShortUUIDBytes_t</a>(<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ggadb49720dc49f7d4e4cf9adbf2948e409abbb64a7440ad9bbd4317ee852737f585" rel="nofollow" target="_blank">BLE_UUID_UNKNOWN</a>))</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#aa17cbe063fa8bb5f5897b6c353c694c6" rel="nofollow" target="_blank">discoverServices</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_service_discovery.html#a45354db5286f99fc93005c9045200c58" rel="nofollow" target="_blank">ServiceDiscovery::ServiceCallback_t</a> callback, const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html" rel="nofollow" target="_blank">UUID</a> &amp;matchingServiceUUID=<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_u_i_d.html#ac9f41b22abc7082a5c4477ac896dd2f3" rel="nofollow" target="_blank">UUID::ShortUUIDBytes_t</a>(<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ggadb49720dc49f7d4e4cf9adbf2948e409abbb64a7440ad9bbd4317ee852737f585" rel="nofollow" target="_blank">BLE_UUID_UNKNOWN</a>))</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ab03c1f320115e198926addf8dbbcdd83" rel="nofollow" target="_blank">discoverServices</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connectionHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_service_discovery.html#a45354db5286f99fc93005c9045200c58" rel="nofollow" target="_blank">ServiceDiscovery::ServiceCallback_t</a> callback, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> startHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> endHandle)</td>
		</tr><tr><td style="vertical-align:top;">virtual bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a06d113f7fb8f1ae350d56821cec1cf5b" rel="nofollow" target="_blank">isServiceDiscoveryActive</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ad573dc2a2e2e04c78a9f247302314e09" rel="nofollow" target="_blank">terminateServiceDiscovery</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a73a626bffa18413bb5d04170269826e7" rel="nofollow" target="_blank">read</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, uint16_t offset) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a3efbba33ffaa6ffe88fc0a03bf8a8918" rel="nofollow" target="_blank">write</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2a4d527bde20e9d5abbe7bf8fcdd8b9d" rel="nofollow" target="_blank">GattClient::WriteOp_t</a> cmd, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Gap::Handle_t</a> connHandle, <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_attribute.html#a8743c39d09f720f497faa86881d57156" rel="nofollow" target="_blank">GattAttribute::Handle_t</a> attributeHandle, size_t length, const uint8_t *value) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ac7d10f4d2709e9b8b91f5e880aac86a6" rel="nofollow" target="_blank">onDataRead</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a91c3f1ceca1e83fd6671029e7152a04d" rel="nofollow" target="_blank">ReadCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a9c25f59502569c3798a81eb1f11b4b06" rel="nofollow" target="_blank">ReadCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a1d309490afa78955fedd3fa6ee131e4a" rel="nofollow" target="_blank">onDataRead</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a20e8dcae61131bdff2609d7333e1a00b" rel="nofollow" target="_blank">onDataWritten</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ad4490a567da33690404a236702310a8f" rel="nofollow" target="_blank">WriteCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a5a554494f8f641aebe07a1ae74eec388" rel="nofollow" target="_blank">WriteCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a4c252a0fdf361541092d277b082241c2" rel="nofollow" target="_blank">onDataWritten</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#aba714cd30ab2cd301010af38cc191e5b" rel="nofollow" target="_blank">onDataWrite</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ad4490a567da33690404a236702310a8f" rel="nofollow" target="_blank">WriteCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#af243d28a9071ac5fa5d71b0c1ef06104" rel="nofollow" target="_blank">onServiceDiscoveryTermination</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_service_discovery.html#ad7f4a0fd51d8c47faa190af9fe0aed18" rel="nofollow" target="_blank">ServiceDiscovery::TerminationCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a9fd4e381458f6c6804908b1672e02b46" rel="nofollow" target="_blank">discoverCharacteristicDescriptors</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_discovered_characteristic.html" rel="nofollow" target="_blank">DiscoveredCharacteristic</a> &amp;characteristic, const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_characteristic_descriptor_discovery.html#a0e2ffe1aa942791df842906c6b226c84" rel="nofollow" target="_blank">CharacteristicDescriptorDiscovery::DiscoveryCallback_t</a> &amp;discoveryCallback, const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_characteristic_descriptor_discovery.html#a14017bda7879f9b70ae7a421050bb1c7" rel="nofollow" target="_blank">CharacteristicDescriptorDiscovery::TerminationCallback_t</a> &amp;terminationCallback)</td>
		</tr><tr><td style="vertical-align:top;">virtual bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ab7f21104e48e97b9c5b38248f1bab5c0" rel="nofollow" target="_blank">isCharacteristicDescriptorDiscoveryActive</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_discovered_characteristic.html" rel="nofollow" target="_blank">DiscoveredCharacteristic</a> &amp;characteristic) const</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#aa2308a6f677011407859a0ad1abe6c59" rel="nofollow" target="_blank">terminateCharacteristicDescriptorDiscovery</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_discovered_characteristic.html" rel="nofollow" target="_blank">DiscoveredCharacteristic</a> &amp;characteristic)</td>
		</tr><tr><td>&nbsp;</td>
			<td>Terminate an ongoing characteristic descriptor discovery procedure. <a href="https://os.mbed.com/docs/v5.9/reference/gattclient.html#aa2308a6f677011407859a0ad1abe6c59" rel="nofollow" target="_blank">More...</a></td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#adb2072b08031e39a6f910e33bdb8360f" rel="nofollow" target="_blank">onHVX</a> (<a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a28d969c787488eae2abe3cb0e081a4c0" rel="nofollow" target="_blank">HVXCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ad3734f2987ca04e13cf47a5559f808ca" rel="nofollow" target="_blank">onShutdown</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a4fb489ff1c9461372b71e05667ef275e" rel="nofollow" target="_blank">GattClientShutdownCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#aa8edf957c59d596b5a998057bff49c89" rel="nofollow" target="_blank">onShutdown</a> (T *objPtr, void(T::*memberPtr)(const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html" rel="nofollow" target="_blank">GattClient</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ae40810e14cd488e2d019aea0fd9259b7" rel="nofollow" target="_blank">GattClientShutdownCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a6910dc4bce6aa2358420b2a329234f98" rel="nofollow" target="_blank">onShutdown</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2db75531892bfbcdea750d37159447b9" rel="nofollow" target="_blank">HVXCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ae2c824f51b4aa2061a72ee4badbb37b7" rel="nofollow" target="_blank">onHVX</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>provide access to the callchain of HVX callbacks. <a href="https://os.mbed.com/docs/v5.9/reference/gattclient.html#ae2c824f51b4aa2061a72ee4badbb37b7" rel="nofollow" target="_blank">More...</a></td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a9cad38418cf8ee470691aadaad821dd6" rel="nofollow" target="_blank">reset</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a4d1e567ae11eeddaa0079d8b50ba76c7" rel="nofollow" target="_blank">processReadResponse</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_read_callback_params.html" rel="nofollow" target="_blank">GattReadCallbackParams</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a1c7769a90eb426691644f436ddab5a93" rel="nofollow" target="_blank">processWriteResponse</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_write_callback_params.html" rel="nofollow" target="_blank">GattWriteCallbackParams</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#afe01180d999f72c1ba77640201ddc91c" rel="nofollow" target="_blank">processHVXEvent</a> (const <a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gatt_h_v_x_callback_params.html" rel="nofollow" target="_blank">GattHVXCallbackParams</a> *params)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a9c25f59502569c3798a81eb1f11b4b06" rel="nofollow" target="_blank">ReadCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a0e79235b819489faf5992ecc36db012f" rel="nofollow" target="_blank">onDataReadCallbackChain</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a5a554494f8f641aebe07a1ae74eec388" rel="nofollow" target="_blank">WriteCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a218906955f64a87ed73156e1ef7a7fba" rel="nofollow" target="_blank">onDataWriteCallbackChain</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a2db75531892bfbcdea750d37159447b9" rel="nofollow" target="_blank">HVXCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#aaf27070eb9a73b94b7324296ca811862" rel="nofollow" target="_blank">onHVXCallbackChain</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#ae40810e14cd488e2d019aea0fd9259b7" rel="nofollow" target="_blank">GattClientShutdownCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_client.html#a5e55a12f4ffcdb7fafa123b7a090d09a" rel="nofollow" target="_blank">shutdownCallChain</a></td>
		</tr></tbody></table>

## GattClient 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-GattClient/file/71d7cec222eb/main.cpp)      

 ```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2017 ARM Limited
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
 
#include <memory>
#include <new>
#include <stdio.h>
 
#include "events/EventQueue.h"
#include "platform/NonCopyable.h"
 
#include "ble/BLE.h"
#include "ble/Gap.h"
#include "ble/GattClient.h"
#include "ble/GapAdvertisingParams.h"
#include "ble/GapAdvertisingData.h"
#include "ble/GattClient.h"
#include "ble/DiscoveredService.h"
#include "ble/DiscoveredCharacteristic.h"
#include "ble/CharacteristicDescriptorDiscovery.h"
 
#include "BLEProcess.h"
 
/**
 * Handle discovery of the GATT server.
 *
 * First the GATT server is discovered in its entirety then each readable
 * characteristic is read and the client register to characteristic
 * notifications or indication when available. The client report server
 * indications and notification until the connection end.
 */
class GattClientProcess : private mbed::NonCopyable<GattClientProcess> {
 
    // Internal typedef to this class type.
    // It is used as a shorthand to pass member function as callbacks.
    typedef GattClientProcess Self;
 
    typedef CharacteristicDescriptorDiscovery::DiscoveryCallbackParams_t
        DiscoveryCallbackParams_t;
 
    typedef CharacteristicDescriptorDiscovery::TerminationCallbackParams_t
        TerminationCallbackParams_t;
 
    typedef DiscoveredCharacteristic::Properties_t Properties_t;
 
public:
 
    /**
     * Construct an empty client process.
     *
     * The function start() shall be called to initiate the discovery process.
     */
    GattClientProcess() :
        _client(NULL),
        _connection_handle(),
        _characteristics(NULL),
        _it(NULL),
        _descriptor_handle(0),
        _ble_interface(NULL),
        _event_queue(NULL) {
    }
 
    ~GattClientProcess()
    {
        stop();
    }
 
    void init(BLE &ble_interface, events::EventQueue &event_queue)
    {
        _ble_interface = &ble_interface;
        _event_queue = &event_queue;
        _client = &_ble_interface->gattClient();
 
        _ble_interface->gap().onConnection(as_cb(&Self::on_connection));
        _ble_interface->gap().onDisconnection(as_cb(&Self::on_disconnection));
    }
 
    /**
     * Event handler invoked when a connection is established.
     *
     * This function setup the connection handle to operate on then start the
     * discovery process.
     */
    void on_connection(const Gap::ConnectionCallbackParams_t* connection_event)
    {
        _connection_handle = connection_event->handle;
        _event_queue->call(mbed::callback(this, &Self::start));
    }
 
    /**
     * Start the discovery process.
     *
     * @param[in] client The GattClient instance which will discover the distant
     * GATT server.
     * @param[in] connection_handle Reference of the connection to the GATT
     * server which will be discovered.
     */
    void start()
    {
        // setup the event handlers called during the process
        _client->onDataWritten().add(as_cb(&Self::when_descriptor_written));
        _client->onHVX().add(as_cb(&Self::when_characteristic_changed));
 
        // The discovery process will invoke when_service_discovered when a
        // service is discovered, when_characteristic_discovered when a
        // characteristic is discovered and when_service_discovery_ends once the
        // discovery process has ended.
        _client->onServiceDiscoveryTermination(as_cb(&Self::when_service_discovery_ends));
        ble_error_t error = _client->launchServiceDiscovery(
            _connection_handle,
            as_cb(&Self::when_service_discovered),
            as_cb(&Self::when_characteristic_discovered)
        );
 
        if (error) {
            printf("Error %u returned by _client->launchServiceDiscovery.\r\n", error);
            return;
        }
 
        printf("Client process started: initiate service discovery.\r\n");
    }
 
    /**
     * Stop the discovery process and clean the instance.
     */
    void on_disconnection(const Gap::DisconnectionCallbackParams_t* disconnection_event)
    {
        if (!_client || disconnection_event->handle != _connection_handle) {
            return;
        }
        stop();
    }
 
    /**
     * Stop the discovery process and clean the instance.
     */
    void stop()
    {
        if (!_client) {
            return;
        }
 
        // unregister event handlers
        _client->onDataWritten().detach(as_cb(&Self::when_descriptor_written));
        _client->onHVX().detach(as_cb(&Self::when_characteristic_changed));
        _client->onServiceDiscoveryTermination(NULL);
 
        // remove discovered characteristics
        clear_characteristics();
 
        // clean up the instance
        _connection_handle = 0;
        _characteristics = NULL;
        _it = NULL;
        _descriptor_handle = 0;
 
        printf("Client process stopped.\r\n");
    }
 
private:
////////////////////////////////////////////////////////////////////////////////
// Service and characteristic discovery process.
 
    /**
     * Handle services discovered.
     *
     * The GattClient invokes this function when a service has been discovered.
     *
     * @see GattClient::launchServiceDiscovery
     */
    void when_service_discovered(const DiscoveredService *discovered_service)
    {
        // print information of the service discovered
        printf("Service discovered: value = ");
        print_uuid(discovered_service->getUUID());
        printf(", start = %u, end = %u.\r\n",
            discovered_service->getStartHandle(),
            discovered_service->getEndHandle()
        );
    }
 
    /**
     * Handle characteristics discovered.
     *
     * The GattClient invoke this function when a characteristic has been
     * discovered.
     *
     * @see GattClient::launchServiceDiscovery
     */
    void when_characteristic_discovered(const DiscoveredCharacteristic *discovered_characteristic)
    {
        // print characteristics properties
        printf("\tCharacteristic discovered: uuid = ");
        print_uuid(discovered_characteristic->getUUID());
        printf(", properties = ");
        print_properties(discovered_characteristic->getProperties());
        printf(
            ", decl handle = %u, value handle = %u, last handle = %u.\r\n",
            discovered_characteristic->getDeclHandle(),
            discovered_characteristic->getValueHandle(),
            discovered_characteristic->getLastHandle()
        );
 
        // add the characteristic into the list of discovered characteristics
        bool success = add_characteristic(discovered_characteristic);
        if (!success) {
            printf("Error: memory allocation failure while adding the discovered characteristic.\r\n");
            _client->terminateServiceDiscovery();
            stop();
            return;
        }
    }
 
    /**
     * Handle termination of the service and characteristic discovery process.
     *
     * The GattClient invokes this function when the service and characteristic
     * discovery process ends.
     *
     * @see GattClient::onServiceDiscoveryTermination
     */
    void when_service_discovery_ends(Gap::Handle_t connection_handle)
    {
        if (!_characteristics) {
            printf("No characteristics discovered, end of the process.\r\n");
            return;
        }
 
        printf("All services and characteristics discovered, process them.\r\n");
 
        // reset iterator and start processing characteristics in order
        _it = NULL;
        _event_queue->call(mbed::callback(this, &Self::process_next_characteristic));
    }
 
////////////////////////////////////////////////////////////////////////////////
// Processing of characteristics based on their properties.
 
    /**
     * Process the characteristics discovered.
     *
     * - If the characteristic is readable then read its value and print it. Then
     * - If the characteristic can emit notification or indication then discover
     * the characteristic CCCD and subscribe to the server initiated event.
     * - Otherwise skip the characteristic processing.
     */
    void process_next_characteristic(void)
    {
        if (!_it) {
            _it = _characteristics;
        } else {
            _it = _it->next;
        }
 
        while (_it) {
            Properties_t properties = _it->value.getProperties();
 
            if (properties.read()) {
                read_characteristic(_it->value);
                return;
            } else if(properties.notify() || properties.indicate()) {
                discover_descriptors(_it->value);
                return;
            } else {
                printf(
                    "Skip processing of characteristic %u\r\n",
                    _it->value.getValueHandle()
                );
                _it = _it->next;
            }
        }
 
        printf("All characteristics discovered have been processed.\r\n");
    }
 
    /**
     * Initate the read of the characteristic in input.
     *
     * The completion of the operation will happens in when_characteristic_read()
     */
    void read_characteristic(const DiscoveredCharacteristic &characteristic)
    {
        printf("Initiating read at %u.\r\n", characteristic.getValueHandle());
        ble_error_t error = characteristic.read(
            0, as_cb(&Self::when_characteristic_read)
        );
 
        if (error) {
            printf(
                "Error: cannot initiate read at %u due to %u\r\n",
                characteristic.getValueHandle(), error
            );
            stop();
        }
    }
 
    /**
     * Handle the reception of a read response.
     *
     * If the characteristic can emit notification or indication then start the
     * discovery of the the characteristic descriptors then subscribe to the
     * server initiated event by writing the CCCD discovered. Otherwise start
     * the processing of the next characteristic discovered in the server.
     */
    void when_characteristic_read(const GattReadCallbackParams *read_event)
    {
        printf("\tCharacteristic value at %u equal to: ", read_event->handle);
        for (size_t i = 0; i <  read_event->len; ++i) {
            printf("0x%02X ", read_event->data[i]);
        }
        printf(".\r\n");
 
        Properties_t properties = _it->value.getProperties();
 
        if(properties.notify() || properties.indicate()) {
            discover_descriptors(_it->value);
        } else {
            process_next_characteristic();
        }
    }
 
    /**
     * Initiate the discovery of the descriptors of the characteristic in input.
     *
     * When a descriptor is discovered, the function when_descriptor_discovered
     * is invoked.
     */
    void discover_descriptors(const DiscoveredCharacteristic &characteristic)
    {
        printf("Initiating descriptor discovery of %u.\r\n", characteristic.getValueHandle());
 
        _descriptor_handle = 0;
        ble_error_t error = characteristic.discoverDescriptors(
            as_cb(&Self::when_descriptor_discovered),
            as_cb(&Self::when_descriptor_discovery_ends)
        );
 
        if (error) {
            printf(
                "Error: cannot initiate discovery of %04X due to %u.\r\n",
                characteristic.getValueHandle(), error
            );
            stop();
        }
    }
 
    /**
     * Handle the discovery of the characteristic descriptors.
     *
     * If the descriptor found is a CCCD then stop the discovery. Once the
     * process has ended subscribe to server initiated events by writing the
     * value of the CCCD.
     */
    void when_descriptor_discovered(const DiscoveryCallbackParams_t* event)
    {
        printf("\tDescriptor discovered at %u, UUID: ", event->descriptor.getAttributeHandle());
        print_uuid(event->descriptor.getUUID());
        printf(".\r\n");
 
        if (event->descriptor.getUUID() == BLE_UUID_DESCRIPTOR_CLIENT_CHAR_CONFIG) {
            _descriptor_handle = event->descriptor.getAttributeHandle();
            _client->terminateCharacteristicDescriptorDiscovery(
                event->characteristic
            );
        }
    }
 
    /**
     * If a CCCD has been found subscribe to server initiated events by writing
     * its value.
     */
    void when_descriptor_discovery_ends(const TerminationCallbackParams_t *event) {
        // shall never happen but happen with android devices ...
        // process the next charateristic
        if (!_descriptor_handle) {
            printf("\tWarning: characteristic with notify or indicate attribute without CCCD.\r\n");
            process_next_characteristic();
            return;
        }
 
        Properties_t properties = _it->value.getProperties();
 
        uint16_t cccd_value =
            (properties.notify() << 0) | (properties.indicate() << 1);
 
        ble_error_t error = _client->write(
            GattClient::GATT_OP_WRITE_REQ,
            _connection_handle,
            _descriptor_handle,
            sizeof(cccd_value),
            reinterpret_cast<uint8_t*>(&cccd_value)
        );
 
        if (error) {
            printf(
                "Error: cannot initiate write of CCCD %u due to %u.\r\n",
                _descriptor_handle, error
            );
            stop();
        }
    }
 
    /**
     * Called when the CCCD has been written.
     */
    void when_descriptor_written(const GattWriteCallbackParams* event)
    {
        // should never happen
        if (!_descriptor_handle) {
            printf("\tError: received write response to unsolicited request.\r\n");
            stop();
            return;
        }
 
        printf("\tCCCD at %u written.\r\n", _descriptor_handle);
        _descriptor_handle = 0;
        process_next_characteristic();
    }
 
    /**
     * Print the updated value of the characteristic.
     *
     * This function is called when the server emits a notification or an
     * indication of a characteristic value the client has subscribed to.
     *
     * @see GattClient::onHVX()
     */
    void when_characteristic_changed(const GattHVXCallbackParams* event)
    {
        printf("Change on attribute %u: new value = ", event->handle);
        for (size_t i = 0; i < event->len; ++i) {
            printf("0x%02X ", event->data[i]);
        }
        printf(".\r\n");
    }
 
    struct DiscoveredCharacteristicNode {
        DiscoveredCharacteristicNode(const DiscoveredCharacteristic &c) :
            value(c), next(NULL) { }
 
        DiscoveredCharacteristic value;
        DiscoveredCharacteristicNode *next;
    };
 
    /**
     * Add a discovered characteristic into the list of discovered characteristics.
     */
    bool add_characteristic(const DiscoveredCharacteristic *characteristic)
    {
        DiscoveredCharacteristicNode* new_node =
            new(std::nothrow) DiscoveredCharacteristicNode(*characteristic);
 
        if (new_node == false) {
            printf("Error while allocating a new characteristic.\r\n");
            return false;
        }
 
        if (_characteristics == NULL) {
            _characteristics = new_node;
        } else {
            DiscoveredCharacteristicNode* c = _characteristics;
            while(c->next) {
                c = c->next;
            }
            c->next = new_node;
        }
 
        return true;
    }
 
    /**
     * Clear the list of discovered characteristics.
     */
    void clear_characteristics(void)
    {
        DiscoveredCharacteristicNode *c= _characteristics;
 
        while (c) {
            DiscoveredCharacteristicNode *n = c->next;
            delete c;
            c = n;
        }
    }
 
    /**
     * Helper to construct an event handler from a member function of this
     * instance.
     */
    template<typename ContextType>
    FunctionPointerWithContext<ContextType> as_cb(
        void (Self::*member)(ContextType context)
    ) {
        return makeFunctionPointer(this, member);
    }
 
    /**
     * Print the value of a UUID.
     */
    static void print_uuid(const UUID &uuid)
    {
        const uint8_t *uuid_value = uuid.getBaseUUID();
 
        // UUIDs are in little endian, print them in big endian
        for (size_t i = 0; i < uuid.getLen(); ++i) {
            printf("%02X", uuid_value[(uuid.getLen() - 1) - i]);
        }
    }
 
    /**
     * Print the value of a characteristic properties.
     */
    static void print_properties(const Properties_t &properties)
    {
        const struct {
            bool (Properties_t::*fn)() const;
            const char* str;
        } prop_to_str[] = {
            { &Properties_t::broadcast, "broadcast" },
            { &Properties_t::read, "read" },
            { &Properties_t::writeWoResp, "writeWoResp" },
            { &Properties_t::write, "write" },
            { &Properties_t::notify, "notify" },
            { &Properties_t::indicate, "indicate" },
            { &Properties_t::authSignedWrite, "authSignedWrite" }
        };
 
        printf("[");
        for (size_t i = 0; i < (sizeof(prop_to_str) / sizeof(prop_to_str[0])); ++i) {
            if ((properties.*(prop_to_str[i].fn))()) {
                printf(" %s", prop_to_str[i].str);
            }
        }
        printf(" ]");
    }
 
    GattClient *_client;
    Gap::Handle_t _connection_handle;
    DiscoveredCharacteristicNode *_characteristics;
    DiscoveredCharacteristicNode *_it;
    GattAttribute::Handle_t _descriptor_handle;
    BLE *_ble_interface;
    events::EventQueue *_event_queue;
};
 
 
int main() {
 
    BLE &ble_interface = BLE::Instance();
    events::EventQueue event_queue;
    BLEProcess ble_process(event_queue, ble_interface);
    GattClientProcess gatt_client_process;
 
    // Register GattClientProcess::init in the ble_process; this function will
    // be called once the ble_interface is initialized.
    ble_process.on_init(
        mbed::callback(&gatt_client_process, &GattClientProcess::init)
    );
 
    // bind the event queue to the ble interface, initialize the interface
    // and start advertising
    ble_process.start();
 
    // Process the event queue.
    event_queue.dispatch_forever();
 
    return 0;
}
```