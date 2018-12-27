## GAP
通用访问配置文件是处理连接任务的堆栈层。 这包括链接建立和终止，广告和扫描。

具有要发布的数据的设备可以使用 GAP 进行广告。它们可以在广告本身中包含数据，在扫描响应内部，或者在建立连接后让对等设备对其进行查询。

该过程的另一方面是扫描行为，其侦听广告，允许您通过扫描请求查询广告商以获取更多数据，或者连接以便向对等设备查询所需数据。

广告，扫描和连接都有参数，可让您在所需的功耗水平，延迟和这些过程的效率之间找到折衷方案。

### 广告

广告包括定期广播包含有关设备的有价值信息的少量数据。在 BLE 广告信道上监听的对等设备可以扫描这些分组。

扫描仪还可以通过发送扫描请求从设备广告中请求附加信息。如果广播公司接受扫描请求，则它可以使用包含附加信息的扫描响应包进行回复。

### 扫描

扫描包括侦听对等广告包。通过扫描，设备可以识别其环境中可用的设备。

如果设备主动扫描，它会向可扫描广告商发送扫描请求并收集其扫描响应。

### 隐私

隐私是一种允许设备避免被其他（不受信任的）设备跟踪的功能。该设备通过周期性地生成新的随机地址来实现它。随机地址可以是可解析的随机地址，使得可信设备能够将其识别为属于同一设备。这些可信设备在配对期间接收身份解析密钥（IRK）。 SecurityManager 处理此问题并依赖于接受和存储 IRK 的其他设备。

您需要在初始化 SecurityManager 之后调用 enablePrivacy() 来启用隐私，因为隐私需要 SecurityManager 来处理 IRK。使用 setCentralPrivacyConfiguration() 设置启用隐私的设备的行为，该设置指定设备使用随机地址的设备应该是什么，以及 setPeripheralPrivacyConfiguration。启用隐私的设备生成的随机地址可以是两种类型：可解析（由具有 IRK 的设备）和不可解析的。您不能使用无法解析的地址进行连接和可连接的广告；因此，无论隐私配置如何，都可以使用可解析的。

### 调制方案

当主机和控制器支持时，您可以选择不同的调制方案：

+ LE 1M PHY。
+ LE 2M PHY。
+ LE coded PHY。
这些在带宽，功率使用和错误恢复能力之间提供了不同的折衷（参见 BLUETOOTH SPECIFICATION Version 5.0 Vol 1，Part A-1.2）。

您可以使用 setPreferredPhys() 设置首选 PHY（分别用于 RX 和 TX）。您还可以使用 setPhy() 在所选连接上设置当前使用的 PHY。这两个设置都只是建议性的，并且允许控制器根据您的请求，对等方支持的功能和连接的物理条件，自行决定使用最佳PHY。

您可以使用 readPhy() 查询当前使用的 PHY，它通过调用注册的事件处理程序返回结果。您可以使用 setEventHandler() 注册该处理程序。事件通知当前使用的 PHY 以及 PHY 的任何变化，控制器或对等体可以自动触发。

## GAP 类参考
[Gap 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">AdvertisementCallbackParams_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_central_privacy_configuration__t.html" rel="nofollow" target="_blank">CentralPrivacyConfiguration_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_callback_params__t.html" rel="nofollow" target="_blank">ConnectionCallbackParams_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_disconnection_callback_params__t.html" rel="nofollow" target="_blank">DisconnectionCallbackParams_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_gap_state__t.html" rel="nofollow" target="_blank">GapState_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_peripheral_privacy_configuration__t.html" rel="nofollow" target="_blank">PeripheralPrivacyConfiguration_t</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_whitelist__t.html" rel="nofollow" target="_blank">Whitelist_t</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a750a99481615c883b6bb59477b58bf65" rel="nofollow" target="_blank">DeprecatedAddressType_t</a> { <strong>ADDR_TYPE_PUBLIC</strong> = BLEProtocol::AddressType::PUBLIC, <strong>ADDR_TYPE_RANDOM_STATIC</strong> = BLEProtocol::AddressType::RANDOM_STATIC, <strong>ADDR_TYPE_RANDOM_PRIVATE_RESOLVABLE</strong> = BLEProtocol::AddressType::RANDOM_PRIVATE_RESOLVABLE, <strong>ADDR_TYPE_RANDOM_PRIVATE_NON_RESOLVABLE</strong> = BLEProtocol::AddressType::RANDOM_PRIVATE_NON_RESOLVABLE }</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767" rel="nofollow" target="_blank">TimeoutSource_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767a0c7b797c656b2e3ae4dd466e141a0415" rel="nofollow" target="_blank">TIMEOUT_SRC_ADVERTISING</a> = 0x00, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767a80c6ffa528108d9db85e6a53b4c99657" rel="nofollow" target="_blank">TIMEOUT_SRC_SECURITY_REQUEST</a> = 0x01, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767a801ddfb73dab4066603654e1a05f2d52" rel="nofollow" target="_blank">TIMEOUT_SRC_SCAN</a> = 0x02, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767a08f0a31f60900b19b740ba1e72fdd5c0" rel="nofollow" target="_blank">TIMEOUT_SRC_CONN</a> = 0x03 }</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">DisconnectionReason_t</a> {<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131ab15781f90a5c89a8bcb288d9fcd01461" rel="nofollow" target="_blank">AUTHENTICATION_FAILURE</a> = 0x05, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131aec1305f1a91e985e9b082b4ce8e267bb" rel="nofollow" target="_blank">CONNECTION_TIMEOUT</a> = 0x08, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131a0d6b5e0f18e9e43ea4644e080a3b5598" rel="nofollow" target="_blank">REMOTE_USER_TERMINATED_CONNECTION</a> = 0x13, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131a0187ed274cf3a4733f1ec9af0cdaa958" rel="nofollow" target="_blank">REMOTE_DEV_TERMINATION_DUE_TO_LOW_RESOURCES</a> = 0x14,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131af21477a641a5f89cbbb75c77d7c18b80" rel="nofollow" target="_blank">REMOTE_DEV_TERMINATION_DUE_TO_POWER_OFF</a> = 0x15, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131a9fcdc08e0e60b661000cc33491f91a2f" rel="nofollow" target="_blank">LOCAL_HOST_TERMINATED_CONNECTION</a> = 0x16, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131a2e023cb619ec9a1c0fc2e1c1fe5654a6" rel="nofollow" target="_blank">CONN_INTERVAL_UNACCEPTABLE</a> = 0x3B<br>
			}</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520" rel="nofollow" target="_blank">AdvertisingPolicyMode_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520a90eb2296543dca9d99a76be17a15ee1d" rel="nofollow" target="_blank">ADV_POLICY_IGNORE_WHITELIST</a> = 0, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520abda0acb60d2f2784f124bf889a621cab" rel="nofollow" target="_blank">ADV_POLICY_FILTER_SCAN_REQS</a> = 1, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520aa974f90577a96ef070305b555db99221" rel="nofollow" target="_blank">ADV_POLICY_FILTER_CONN_REQS</a> = 2, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520a923c3b6d8c8c077fbe9825c19964df12" rel="nofollow" target="_blank">ADV_POLICY_FILTER_ALL_REQS</a> = 3 }</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4307718c3a030f808ce9d1f9b6c061e3" rel="nofollow" target="_blank">ScanningPolicyMode_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4307718c3a030f808ce9d1f9b6c061e3af62f977f8de6b58562cf655cf2e36896" rel="nofollow" target="_blank">SCAN_POLICY_IGNORE_WHITELIST</a> = 0, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4307718c3a030f808ce9d1f9b6c061e3a75a846a49021ce787a5ce48022d2b8d2" rel="nofollow" target="_blank">SCAN_POLICY_FILTER_ALL_ADV</a> = 1 }</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb313bfd612fe1e6decd4e37bbe01fee" rel="nofollow" target="_blank">InitiatorPolicyMode_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb313bfd612fe1e6decd4e37bbe01feea335fec4f8aac305b1b0bc729b16de13e" rel="nofollow" target="_blank">INIT_POLICY_IGNORE_WHITELIST</a> = 0, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb313bfd612fe1e6decd4e37bbe01feea66b6117ed56d5968181e92c6a1f7ac64" rel="nofollow" target="_blank">INIT_POLICY_FILTER_ALL_ADV</a> = 1 }</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1a963b223a2851dfb758168b1973dde5" rel="nofollow" target="_blank">Role_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1a963b223a2851dfb758168b1973dde5a1b3756f2c760595b86e8079f844042b7" rel="nofollow" target="_blank">PERIPHERAL</a> = 0x1, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1a963b223a2851dfb758168b1973dde5a3d99164abadadeb6332366e05816587f" rel="nofollow" target="_blank">CENTRAL</a> = 0x2 }</td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a01f3eba4c8381b0ab4873dd41cd67067" rel="nofollow" target="_blank">AddressType_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0f6222dc40d51b14535a557aa15fe510" rel="nofollow" target="_blank">addr_type_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad6a917e769918ab859aad87dff79c6be" rel="nofollow" target="_blank">Address_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a759d94fabc589f3446482e1bfefc9ec0" rel="nofollow" target="_blank">address_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1random__address__type__t.html" rel="nofollow" target="_blank">ble::random_address_type_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad2115d2295c9604f876458919ddd72b8" rel="nofollow" target="_blank">RandomAddressType_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1peer__address__type__t.html" rel="nofollow" target="_blank">ble::peer_address_type_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a70b7146da69eceee8987347e77287c16" rel="nofollow" target="_blank">PeerAddressType_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">AdvertisementCallbackParams_t</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abe73596e93ed70229395f3bc67552312" rel="nofollow" target="_blank">AdvertisementReportCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767" rel="nofollow" target="_blank">TimeoutSource_t</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a254c7b52393a4e0f8fd6952e3c2cc6a3" rel="nofollow" target="_blank">TimeoutEventCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767" rel="nofollow" target="_blank">TimeoutSource_t</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3df3f8577de7cd0059d7f9b2f2691d87" rel="nofollow" target="_blank">TimeoutEventCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_callback_params__t.html" rel="nofollow" target="_blank">ConnectionCallbackParams_t</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a5259ebdc579c7642827dc50730f2e5ac" rel="nofollow" target="_blank">ConnectionEventCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_callback_params__t.html" rel="nofollow" target="_blank">ConnectionCallbackParams_t</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3249dc236938a19f4004e4e9ea536f23" rel="nofollow" target="_blank">ConnectionEventCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_disconnection_callback_params__t.html" rel="nofollow" target="_blank">DisconnectionCallbackParams_t</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa7569b0353d271bc8001058d5c953cbe" rel="nofollow" target="_blank">DisconnectionEventCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_disconnection_callback_params__t.html" rel="nofollow" target="_blank">DisconnectionCallbackParams_t</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ade6b02fc941979d4c360f1b1795e5c0b" rel="nofollow" target="_blank">DisconnectionEventCallbackChain_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; bool &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a100647d2c5f63948ee97914cac2d0496" rel="nofollow" target="_blank">RadioNotificationEventCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html" rel="nofollow" target="_blank">Gap</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a8d61b9138b0c30136a820bc86717efab" rel="nofollow" target="_blank">GapShutdownCallback_t</a></td>
		</tr><tr><td style="vertical-align:top;">typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html" rel="nofollow" target="_blank">Gap</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4191cf7ac4708a1dbc4997e41175157b" rel="nofollow" target="_blank">GapShutdownCallbackChain_t</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a42d4823926c852e03c99c332eb466498" rel="nofollow" target="_blank">setAddress</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> type, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> address)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad4967f4a7e24404c31249808573e791e" rel="nofollow" target="_blank">getAddress</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> *typeP, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> address)</td>
		</tr><tr><td style="vertical-align:top;">virtual uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a37a1e2cc4094bdfc987e395ab6ac8953" rel="nofollow" target="_blank">getMinAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a37fa7b80f72c85c4a378c2570e906934" rel="nofollow" target="_blank">getMinNonConnectableAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad5c2ca75042fa675e5c68eead65df954" rel="nofollow" target="_blank">getMaxAdvertisingInterval</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0cb8a604ef7827ee7c3327eaa3d4702f" rel="nofollow" target="_blank">stopAdvertising</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ac18a9fc8bd315eb716618b5b6805f7f9" rel="nofollow" target="_blank">stopScan</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1fc4d41cd6597e0d68f8590a2eef06ab" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a70b7146da69eceee8987347e77287c16" rel="nofollow" target="_blank">PeerAddressType_t</a> peerAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *connectionParams, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> *scanParams)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab2eaca38cb467e09b61593dfb7f57055" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> peerAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *connectionParams, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> *scanParams)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab81c2422314e84ee6a3fd7e1da81af3b" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a750a99481615c883b6bb59477b58bf65" rel="nofollow" target="_blank">DeprecatedAddressType_t</a> peerAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *connectionParams, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> *scanParams)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af73f193fb7b5462008322590f612ee21" rel="nofollow" target="_blank">disconnect</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">DisconnectionReason_t</a> reason)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a809ce60934bbeeb94c853d27307fe911" rel="nofollow" target="_blank">disconnect</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">DisconnectionReason_t</a> reason)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa86c290ace8eab1b17cd8f7c962abdaa" rel="nofollow" target="_blank">getPreferredConnectionParams</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#adeb93f90421ad0b09a35c6fa8ed7b868" rel="nofollow" target="_blank">setPreferredConnectionParams</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1c3f9263b6dcb55d3f0f48d75454f4ae" rel="nofollow" target="_blank">updateConnectionParams</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a> handle, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *params)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a11d1649ff8babf8f059e5a327d2c797c" rel="nofollow" target="_blank">setDeviceName</a> (const uint8_t *deviceName)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad589c322e98e83d15c4bab523d6103d2" rel="nofollow" target="_blank">getDeviceName</a> (uint8_t *deviceName, unsigned *lengthP)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abd6793d63f178dc7f655e949bc0239b3" rel="nofollow" target="_blank">setAppearance</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> appearance)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a219b9127d5a07da2832c8a95b4691df4" rel="nofollow" target="_blank">getAppearance</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> *appearanceP)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aede2576f28915dc133f1bee68d6dcf19" rel="nofollow" target="_blank">setTxPower</a> (int8_t txPower)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa01af0f6508b8b461196190a4b94ee9d" rel="nofollow" target="_blank">getPermittedTxPowerValues</a> (const int8_t **valueArrayPP, size_t *countP)</td>
		</tr><tr><td style="vertical-align:top;">virtual uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a24a480d7562f3ec74dea0d592191b49a" rel="nofollow" target="_blank">getMaxWhitelistSize</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a303771847c580243a2f34250f2062dc3" rel="nofollow" target="_blank">getWhitelist</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_whitelist__t.html" rel="nofollow" target="_blank">Whitelist_t</a> &amp;whitelist) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abc6b8380886557af7a97576c57abb49d" rel="nofollow" target="_blank">setWhitelist</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_whitelist__t.html" rel="nofollow" target="_blank">Whitelist_t</a> &amp;whitelist)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a8da7e514f01a81eee6f5f0d300e462ae" rel="nofollow" target="_blank">setAdvertisingPolicyMode</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520" rel="nofollow" target="_blank">AdvertisingPolicyMode_t</a> mode)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2089115fb3697d6e5f4535ce492bfe4c" rel="nofollow" target="_blank">setScanningPolicyMode</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4307718c3a030f808ce9d1f9b6c061e3" rel="nofollow" target="_blank">ScanningPolicyMode_t</a> mode)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2dd588b85b902ef9b36090213a4ea1d3" rel="nofollow" target="_blank">setInitiatorPolicyMode</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb313bfd612fe1e6decd4e37bbe01fee" rel="nofollow" target="_blank">InitiatorPolicyMode_t</a> mode)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acb2bae90ea72e88783283f704377f520" rel="nofollow" target="_blank">AdvertisingPolicyMode_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a204b3e104f4ad05f8538be08900f06cd" rel="nofollow" target="_blank">getAdvertisingPolicyMode</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4307718c3a030f808ce9d1f9b6c061e3" rel="nofollow" target="_blank">ScanningPolicyMode_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab1b9a98859d5c95c541464ae0a80adba" rel="nofollow" target="_blank">getScanningPolicyMode</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb313bfd612fe1e6decd4e37bbe01fee" rel="nofollow" target="_blank">InitiatorPolicyMode_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abed0faedb314f3d36511037faa980627" rel="nofollow" target="_blank">getInitiatorPolicyMode</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_gap_state__t.html" rel="nofollow" target="_blank">GapState_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aee9159d956f46780e14f109d92198170" rel="nofollow" target="_blank">getState</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aaaa8b28d7028b3e309bdc633ce0ffa57" rel="nofollow" target="_blank">setAdvertisingType</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html#a7ceecca3718d7d5d44c914e1243a05e2" rel="nofollow" target="_blank">GapAdvertisingParams::AdvertisingType_t</a> advType)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a9f01c5db652ab21a7a79dabc21874935" rel="nofollow" target="_blank">setAdvertisingInterval</a> (uint16_t interval)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ac327b966a8d40c7295e901231286aa67" rel="nofollow" target="_blank">setAdvertisingTimeout</a> (uint16_t timeout)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0e4e0ced270b8942195ba4a6ed9c65f0" rel="nofollow" target="_blank">startAdvertising</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af8d2698830d6b6bb2c84926d1a6ae917" rel="nofollow" target="_blank">clearAdvertisingPayload</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae91d6c0ad54b8c06cb0047f065c773ee" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (uint8_t flags)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a63b105e7db5570d1001cd8f596a96039" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a7bf4f1479a8e3906c230de6ffe136c83" rel="nofollow" target="_blank">GapAdvertisingData::Appearance</a> app)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a550566a04c982aeee26049f6f42c96ee" rel="nofollow" target="_blank">accumulateAdvertisingPayloadTxPower</a> (int8_t power)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2fbd131a6bdc1c36c59df5e90cb850d5" rel="nofollow" target="_blank">accumulateAdvertisingPayload</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a061f7debe69c2e03281a5bef0a364ef2" rel="nofollow" target="_blank">GapAdvertisingData::DataType</a> type, const uint8_t *data, uint8_t len)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a26f9acfa943cd8ec8ad5287f29ff1b81" rel="nofollow" target="_blank">updateAdvertisingPayload</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a061f7debe69c2e03281a5bef0a364ef2" rel="nofollow" target="_blank">GapAdvertisingData::DataType</a> type, const uint8_t *data, uint8_t len)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa9218c8f4d173476d7c45cb2a5f1cba8" rel="nofollow" target="_blank">setAdvertisingPayload</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a> &amp;payload)</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a57835821ab5884608bd5b2803609b6a0" rel="nofollow" target="_blank">getAdvertisingPayload</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab58a4b2ac21a0a887a3e7552129c4187" rel="nofollow" target="_blank">accumulateScanResponse</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html#a061f7debe69c2e03281a5bef0a364ef2" rel="nofollow" target="_blank">GapAdvertisingData::DataType</a> type, const uint8_t *data, uint8_t len)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a6634650885fd948d9546a637681d7b31" rel="nofollow" target="_blank">clearScanResponse</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab095aad7832e6b76e034afa697c282fe" rel="nofollow" target="_blank">setScanParams</a> (uint16_t interval=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html#af174646a891030da3662274d75ec1263" rel="nofollow" target="_blank">GapScanningParams::SCAN_INTERVAL_MAX</a>, uint16_t window=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html#a83586bf09561d0f00b26184f1a5d4e69" rel="nofollow" target="_blank">GapScanningParams::SCAN_WINDOW_MAX</a>, uint16_t timeout=0, bool activeScanning=false)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3e51571ffd2998003f1af5c164280848" rel="nofollow" target="_blank">setScanParams</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> &amp;scanningParams)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa88445cbd9dbf2ce06baab6d87dc389d" rel="nofollow" target="_blank">setScanInterval</a> (uint16_t interval)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae3276ff0b10123eadf19d5dac9451fb7" rel="nofollow" target="_blank">setScanWindow</a> (uint16_t window)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3d5155912b0f0b025b9402fad63bd782" rel="nofollow" target="_blank">setScanTimeout</a> (uint16_t timeout)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a75cf753a14fba8a74fc0f17a144301df" rel="nofollow" target="_blank">setActiveScanning</a> (bool activeScanning)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a14faf54bc8d5d09dcd4dcef7ea9ddb19" rel="nofollow" target="_blank">startScan</a> (void(*callback)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">AdvertisementCallbackParams_t</a> *params))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4afddc945caa0a4699cb5252a8e3232a" rel="nofollow" target="_blank">startScan</a> (T *object, void(T::*callbackMember)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_advertisement_callback_params__t.html" rel="nofollow" target="_blank">AdvertisementCallbackParams_t</a> *params))</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#acaa5daa08295e256a875d72b94ef73e9" rel="nofollow" target="_blank">initRadioNotification</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa5f3dfb12a27ae14916729d2a89206c1" rel="nofollow" target="_blank">enablePrivacy</a> (bool enable)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae42c99ebbbc5ef0cdc5ebb4d5704ab88" rel="nofollow" target="_blank">setPeripheralPrivacyConfiguration</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_peripheral_privacy_configuration__t.html" rel="nofollow" target="_blank">PeripheralPrivacyConfiguration_t</a> *configuration)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a46d6bc927c1169da9c70b514f3eb0090" rel="nofollow" target="_blank">getPeripheralPrivacyConfiguration</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_peripheral_privacy_configuration__t.html" rel="nofollow" target="_blank">PeripheralPrivacyConfiguration_t</a> *configuration)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a9401a5833954eb01567db3cee845b06d" rel="nofollow" target="_blank">setCentralPrivacyConfiguration</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_central_privacy_configuration__t.html" rel="nofollow" target="_blank">CentralPrivacyConfiguration_t</a> *configuration)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af901e5f1c09fe05b02b0680f04f0fe55" rel="nofollow" target="_blank">getCentralPrivacyConfiguration</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_central_privacy_configuration__t.html" rel="nofollow" target="_blank">CentralPrivacyConfiguration_t</a> *configuration)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae8ac376cd33a58a1a932d3a054dc59c0" rel="nofollow" target="_blank">getAdvertisingParams</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0bb09fb9abbc8d833ebb6a10dd54151b" rel="nofollow" target="_blank">getAdvertisingParams</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a529fafe86807e4889f24b51587b10c53" rel="nofollow" target="_blank">setAdvertisingParams</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a> &amp;newParams)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4aee72bf47b050e022324facb8f88ba3" rel="nofollow" target="_blank">onTimeout</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a254c7b52393a4e0f8fd6952e3c2cc6a3" rel="nofollow" target="_blank">TimeoutEventCallback_t</a> callback)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3df3f8577de7cd0059d7f9b2f2691d87" rel="nofollow" target="_blank">TimeoutEventCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1888c364c3c71c748b7add671f0a51ce" rel="nofollow" target="_blank">onTimeout</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ac558afacbb8133aa79478191343088f0" rel="nofollow" target="_blank">onConnection</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a5259ebdc579c7642827dc50730f2e5ac" rel="nofollow" target="_blank">ConnectionEventCallback_t</a> callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aed2c4d4db2d28a40c755def66c401a75" rel="nofollow" target="_blank">onConnection</a> (T *tptr, void(T::*mptr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_callback_params__t.html" rel="nofollow" target="_blank">ConnectionCallbackParams_t</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3249dc236938a19f4004e4e9ea536f23" rel="nofollow" target="_blank">ConnectionEventCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a5f264d546c04f0027b33ffedff886590" rel="nofollow" target="_blank">onConnection</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ac14209def92da4ffef91b814ae142234" rel="nofollow" target="_blank">onDisconnection</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa7569b0353d271bc8001058d5c953cbe" rel="nofollow" target="_blank">DisconnectionEventCallback_t</a> callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0e750398f2dd4de57b2995b2bc04e6c3" rel="nofollow" target="_blank">onDisconnection</a> (T *tptr, void(T::*mptr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_disconnection_callback_params__t.html" rel="nofollow" target="_blank">DisconnectionCallbackParams_t</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ade6b02fc941979d4c360f1b1795e5c0b" rel="nofollow" target="_blank">DisconnectionEventCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#afb1eddb1a2083cbcd42fe88ec6e51713" rel="nofollow" target="_blank">onDisconnection</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a9d614550e8a34eb4840f91628d6d392f" rel="nofollow" target="_blank">onRadioNotification</a> (void(*callback)(bool param))</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3d584354ee0f874d880f1b52006bfd5d" rel="nofollow" target="_blank">onRadioNotification</a> (T *tptr, void(T::*mptr)(bool))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3b91e2dad416c3747e4d057b3aa21ee0" rel="nofollow" target="_blank">onShutdown</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a8d61b9138b0c30136a820bc86717efab" rel="nofollow" target="_blank">GapShutdownCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1b14333c72bf8ed661d5ab92e0917f30" rel="nofollow" target="_blank">onShutdown</a> (T *objPtr, void(T::*memberPtr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html" rel="nofollow" target="_blank">Gap</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4191cf7ac4708a1dbc4997e41175157b" rel="nofollow" target="_blank">GapShutdownCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a14d14cfcfc096835f7888a2252163da5" rel="nofollow" target="_blank">onShutdown</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a412a814978fab0811c3f660504d1951b" rel="nofollow" target="_blank">reset</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a8ae27ae1592f9f771d8994f219f32845" rel="nofollow" target="_blank">processConnectionEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a> handle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1a963b223a2851dfb758168b1973dde5" rel="nofollow" target="_blank">Role_t</a> role, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a70b7146da69eceee8987347e77287c16" rel="nofollow" target="_blank">PeerAddressType_t</a> peerAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> ownAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> ownAddr, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *connectionParams, const uint8_t *peerResolvableAddr=NULL, const uint8_t *localResolvableAddr=NULL)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae24bb31f688698754dbd80f28676a2aa" rel="nofollow" target="_blank">processConnectionEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a> handle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1a963b223a2851dfb758168b1973dde5" rel="nofollow" target="_blank">Role_t</a> role, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> peerAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> ownAddrType, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> ownAddr, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_connection_params__t.html" rel="nofollow" target="_blank">ConnectionParams_t</a> *connectionParams, const uint8_t *peerResolvableAddr=NULL, const uint8_t *localResolvableAddr=NULL)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2f7ef55f526638368b2f55d99fad53f8" rel="nofollow" target="_blank">processDisconnectionEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#af7ab75bbe4d17a5c8497b68f7a2732cf" rel="nofollow" target="_blank">Handle_t</a> handle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a82ea046e0e8b558b7e64c91458852131" rel="nofollow" target="_blank">DisconnectionReason_t</a> reason)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2ca8e26001cb7356f11361afcce37f0e" rel="nofollow" target="_blank">processAdvertisementReport</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, int8_t rssi, bool isScanResponse, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html#a7ceecca3718d7d5d44c914e1243a05e2" rel="nofollow" target="_blank">GapAdvertisingParams::AdvertisingType_t</a> type, uint8_t advertisingDataLen, const uint8_t *advertisingData, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a70b7146da69eceee8987347e77287c16" rel="nofollow" target="_blank">PeerAddressType_t</a> addressType)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0587b01491757ed9ee03a03a76f8b015" rel="nofollow" target="_blank">processAdvertisementReport</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> peerAddr, int8_t rssi, bool isScanResponse, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html#a7ceecca3718d7d5d44c914e1243a05e2" rel="nofollow" target="_blank">GapAdvertisingParams::AdvertisingType_t</a> type, uint8_t advertisingDataLen, const uint8_t *advertisingData, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367d" rel="nofollow" target="_blank">BLEProtocol::AddressType_t</a> addressType=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_b_l_e_protocol_1_1_address_type.html#aa19f8504dac27ab67c7713c29f40367da6f78811fdcccf1055e1014cb6cd5bd7f" rel="nofollow" target="_blank">BLEProtocol::AddressType::RANDOM_STATIC</a>)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1d7aed22716ee0648317b1297a3c1462" rel="nofollow" target="_blank">processTimeoutEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#aa85f2cdd6e17ccf32cc5f6830115a767" rel="nofollow" target="_blank">TimeoutSource_t</a> source)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a686dc170e08fec66986f890b71fe103b" rel="nofollow" target="_blank">MSEC_TO_GAP_DURATION_UNITS</a> (uint32_t durationInMillis)</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a58f5c48043388800dccde6668322f988" rel="nofollow" target="_blank">getRandomAddressType</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespace_b_l_e_protocol.html#a2516adb407539f8197d82261129feebd" rel="nofollow" target="_blank">BLEProtocol::AddressBytes_t</a> address, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ad2115d2295c9604f876458919ddd72b8" rel="nofollow" target="_blank">RandomAddressType_t</a> *addressType)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共属性</td>
		</tr><tr><td style="vertical-align:top;">static const unsigned&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a8b8fe368ce7d1ba71fcf7da8a665ae6a" rel="nofollow" target="_blank">ADDR_LEN</a> = BLEProtocol::ADDR_LEN</td>
		</tr><tr><td style="vertical-align:top;">static const uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ac27778b73c4e200aadb94220611d9914" rel="nofollow" target="_blank">UNIT_1_25_MS</a> = 1250</td>
		</tr><tr><td style="vertical-align:top;">static const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_peripheral_privacy_configuration__t.html" rel="nofollow" target="_blank">PeripheralPrivacyConfiguration_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>default_peripheral_privacy_configuration</strong></td>
		</tr><tr><td style="vertical-align:top;">static const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_central_privacy_configuration__t.html" rel="nofollow" target="_blank">CentralPrivacyConfiguration_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>default_central_privacy_configuration</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a0b61799975a3e893ef49790489c90748" rel="nofollow" target="_blank">startRadioScan</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a> &amp;scanningParams)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abb416b0d6e07ca4912d307352b5470a0" rel="nofollow" target="_blank">Gap</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_params.html" rel="nofollow" target="_blank">GapAdvertisingParams</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2eae22806b3b6d447197c1707ee48c63" rel="nofollow" target="_blank">_advParams</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a81f5469fd1bea0b123155cf82327405a" rel="nofollow" target="_blank">_advPayload</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_scanning_params.html" rel="nofollow" target="_blank">GapScanningParams</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a2de50500bdc80278f3cb0f124c265407" rel="nofollow" target="_blank">_scanningParams</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap_advertising_data.html" rel="nofollow" target="_blank">GapAdvertisingData</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ae7cbc70e102d011fce73b2c9a297aef2" rel="nofollow" target="_blank">_scanResponse</a></td>
		</tr><tr><td style="vertical-align:top;">uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a019192913cdb8e6004f722afbb93b52d" rel="nofollow" target="_blank">connectionCount</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_gap_state__t.html" rel="nofollow" target="_blank">GapState_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a4c5cb1e8ed53b89b319d615149401fd9" rel="nofollow" target="_blank">state</a></td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a85cfcd76253a23f8894558b43e0511c2" rel="nofollow" target="_blank">scanningActive</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3df3f8577de7cd0059d7f9b2f2691d87" rel="nofollow" target="_blank">TimeoutEventCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a40443ad35372f71a4a0b60ff830409be" rel="nofollow" target="_blank">timeoutCallbackChain</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a100647d2c5f63948ee97914cac2d0496" rel="nofollow" target="_blank">RadioNotificationEventCallback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a1c91ca45044112d92c8d63619eb2b42c" rel="nofollow" target="_blank">radioNotificationCallback</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#abe73596e93ed70229395f3bc67552312" rel="nofollow" target="_blank">AdvertisementReportCallback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a698a36b54127d991b6a0b0201b3dfa3f" rel="nofollow" target="_blank">onAdvertisementReport</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a3249dc236938a19f4004e4e9ea536f23" rel="nofollow" target="_blank">ConnectionEventCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#a44193eb944c85391d37e3529450ce587" rel="nofollow" target="_blank">connectionCallChain</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ade6b02fc941979d4c360f1b1795e5c0b" rel="nofollow" target="_blank">DisconnectionEventCallbackChain_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gap.html#ab433f4f12c1cb41002f0102424e6b8ee" rel="nofollow" target="_blank">disconnectionCallChain</a></td>
		</tr></tbody></table>

## GAP 示例
这是一个示例，演示如何使用 GAP API 来通告，扫描，连接和断开连接以及参数如何影响这些操作的效率。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-GAP/file/8539ba0984da/source/main.cpp)      
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2013 ARM Limited
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
 
/** This example demonstrates all the basic setup required
 *  to advertise, scan and connect to other devices.
 *
 *  It contains a single class that performs both scans and advertisements.
 *
 *  The demonstrations happens in sequence, after each "mode" ends
 *  the demo jumps to the next mode to continue. There are several modes
 *  that show scanning and several showing advertising. These are configured
 *  according to the two arrays containing parameters. During scanning
 *  a connection will be made to a connectable device upon its discovery.
 */
 
static const uint8_t DEVICE_NAME[]        = "GAP_device";
 
/* Duration of each mode in milliseconds */
static const size_t MODE_DURATION_MS      = 6000;
 
/* Time between each mode in milliseconds */
static const size_t TIME_BETWEEN_MODES_MS = 2000;
 
/* how long to wait before disconnecting in milliseconds */
static const size_t CONNECTION_DURATION = 3000;
 
typedef struct {
    GapAdvertisingParams::AdvertisingType_t adv_type;
    uint16_t interval;
    uint16_t timeout;
} AdvModeParam_t;
 
typedef struct {
    uint16_t interval;
    uint16_t window;
    uint16_t timeout;
    bool active;
} ScanModeParam_t;
 
/** the entries in this array are used to configure our advertising
 *  parameters for each of the modes we use in our demo */
static const AdvModeParam_t advertising_params[] = {
    /*            advertising type                        interval  timeout */
    { GapAdvertisingParams::ADV_CONNECTABLE_UNDIRECTED,      40,/*ms*/ 3/*s*/},
    { GapAdvertisingParams::ADV_SCANNABLE_UNDIRECTED,       100,       4     },
    { GapAdvertisingParams::ADV_NON_CONNECTABLE_UNDIRECTED, 100,       0     }
};
 
/* when we cycle through all our advertising modes we will move to scanning modes */
 
/** the entries in this array are used to configure our scanning
 *  parameters for each of the modes we use in our demo */
static const ScanModeParam_t scanning_params[] = {
/* interval      window    timeout       active */
    {   4,/*ms*/   4,/*ms*/   0,/*s*/    false },
    { 160,       100,         3,         false },
    { 160,        40,         0,         true  },
    { 500,        10,         0,         false }
};
 
/* parameters to use when attempting to connect to maximise speed of connection */
static const GapScanningParams connection_scan_params(
    GapScanningParams::SCAN_INTERVAL_MAX,
    GapScanningParams::SCAN_WINDOW_MAX,
    3,
    false
);
 
/* get number of items in our arrays */
static const size_t SCAN_PARAM_SET_MAX =
    sizeof(scanning_params) / sizeof(GapScanningParams);
static const size_t ADV_PARAM_SET_MAX  =
    sizeof(advertising_params) / sizeof(GapAdvertisingParams);
 
 
/** Demonstrate advertising, scanning and connecting
 */
class GAPDevice : private mbed::NonCopyable<GAPDevice>
{
public:
    GAPDevice() :
        _ble(BLE::Instance()),
        _led1(LED1, 0),
        _set_index(0),
        _is_in_scanning_mode(false),
        _is_connecting(false),
        _on_duration_end_id(0),
        _scan_count(0) { };
 
    ~GAPDevice()
    {
        if (_ble.hasInitialized()) {
            _ble.shutdown();
        }
    };
 
    /** Start BLE interface initialisation */
    void run()
    {
        ble_error_t error;
 
        if (_ble.hasInitialized()) {
            printf("Ble instance already initialised.\r\n");
            return;
        }
 
        /* this will inform us off all events so we can schedule their handling
         * using our event queue */
        _ble.onEventsToProcess(
            makeFunctionPointer(this, &GAPDevice::schedule_ble_events)
        );
 
        /* handle timeouts, for example when connection attempts fail */
        _ble.gap().onTimeout(
            makeFunctionPointer(this, &GAPDevice::on_timeout)
        );
 
        error = _ble.init(this, &GAPDevice::on_init_complete);
 
        if (error) {
            printf("Error returned by BLE::init.\r\n");
            return;
        }
 
        /* to show we're running we'll blink every 500ms */
        _event_queue.call_every(500, this, &GAPDevice::blink);
 
        /* this will not return until shutdown */
        _event_queue.dispatch_forever();
    };
 
private:
    /** This is called when BLE interface is initialised and starts the first mode */
    void on_init_complete(BLE::InitializationCompleteCallbackContext *event)
    {
        if (event->error) {
            printf("Error during the initialisation\r\n");
            return;
        }
 
        /* print device address */
        Gap::AddressType_t addr_type;
        Gap::Address_t addr;
        _ble.gap().getAddress(&addr_type, addr);
        printf("Device address: %02x:%02x:%02x:%02x:%02x:%02x\r\n",
               addr[5], addr[4], addr[3], addr[2], addr[1], addr[0]);
 
        /* all calls are serialised on the user thread through the event queue */
        _event_queue.call(this, &GAPDevice::demo_mode_start);
    };
 
    /** queue up start of the current demo mode */
    void demo_mode_start()
    {
        if (_is_in_scanning_mode) {
            /* when scanning we want to connect to a peer device so we need to
             * attach callbacks that are used by Gap to notify us of events */
            _ble.gap().onConnection(this, &GAPDevice::on_connect);
            _ble.gap().onDisconnection(this, &GAPDevice::on_disconnect);
 
            _event_queue.call(this, &GAPDevice::scan);
        } else {
            _event_queue.call(this, &GAPDevice::advertise);
        }
 
        /* for performance measurement keep track of duration of the demo mode */
        _demo_duration.start();
        /* keep track of our state */
        _is_connecting = false;
 
        /* queue up next demo mode */
        _on_duration_end_id = _event_queue.call_in(
            MODE_DURATION_MS, this, &GAPDevice::on_duration_end
        );
 
        printf("\r\n");
    }
 
    /** Set up and start advertising */
    void advertise()
    {
        ble_error_t error;
        GapAdvertisingData advertising_data;
 
        /* add advertising flags */
        advertising_data.addFlags(GapAdvertisingData::LE_GENERAL_DISCOVERABLE
                                  | GapAdvertisingData::BREDR_NOT_SUPPORTED);
 
        /* add device name */
        advertising_data.addData(
            GapAdvertisingData::COMPLETE_LOCAL_NAME,
            DEVICE_NAME,
            sizeof(DEVICE_NAME)
        );
 
        error = _ble.gap().setAdvertisingPayload(advertising_data);
 
        if (error) {
            printf("Error during Gap::setAdvertisingPayload\r\n");
            return;
        }
 
        /* set the advertising parameters according to currently selected set,
         * see @AdvertisingType_t for explanation of modes */
        GapAdvertisingParams::AdvertisingType_t adv_type =
            advertising_params[_set_index].adv_type;
 
        /* how many milliseconds between advertisements, lower interval
         * increases the chances of being seen at the cost of more power */
        uint16_t interval = advertising_params[_set_index].interval;
 
        /* advertising will continue for this many seconds or until connected */
        uint16_t timeout = advertising_params[_set_index].timeout;
 
        _ble.gap().setAdvertisingType(adv_type);
        _ble.gap().setAdvertisingInterval(interval);
        _ble.gap().setAdvertisingTimeout(timeout);
 
        error = _ble.gap().startAdvertising();
 
        if (error) {
            printf("Error during Gap::startAdvertising.\r\n");
            return;
        }
 
        printf("Advertising started (type: 0x%x, interval: %dms, timeout: %ds)\r\n",
               adv_type, interval, timeout);
    };
 
    /** Set up and start scanning */
    void scan()
    {
        ble_error_t error;
 
        /* scanning happens repeatedly, interval is the number of milliseconds
         * between each cycle of scanning */
        uint16_t interval = scanning_params[_set_index].interval;
 
        /* number of milliseconds we scan for each time we enter
         * the scanning cycle after the interval set above */
        uint16_t window = scanning_params[_set_index].window;
 
        /* how long to repeat the cycles of scanning in seconds */
        uint16_t timeout = scanning_params[_set_index].timeout;
 
        /* active scanning will send a scan request to any scanable devices that
         * we see advertising */
        bool active = scanning_params[_set_index].active;
 
        /* set the scanning parameters according to currently selected set */
        error = _ble.gap().setScanParams(interval, window, timeout, active);
 
        if (error) {
            printf("Error during Gap::setScanParams\r\n");
            return;
        }
 
        /* start scanning and attach a callback that will handle advertisements
         * and scan requests responses */
        error = _ble.gap().startScan(this, &GAPDevice::on_scan);
 
        if (error) {
            printf("Error during Gap::startScan\r\n");
            return;
        }
 
        printf("Scanning started (interval: %dms, window: %dms, timeout: %ds).\r\n",
               interval, window, timeout);
    };
 
    /** After a set duration this cycles to the next demo mode
     *  unless a connection happened first */
    void on_duration_end()
    {
        print_performance();
 
        /* alloted time has elapsed, move to next demo mode */
        _event_queue.call(this, &GAPDevice::demo_mode_end);
    };
 
    /** Look at scan payload to find a peer device and connect to it */
    void on_scan(const Gap::AdvertisementCallbackParams_t *params)
    {
        /* keep track of scan events for performance reporting */
        _scan_count++;
 
        /* don't bother with analysing scan result if we're already connecting */
        if (_is_connecting) {
            return;
        }
 
        /* parse the advertising payload, looking for a discoverable device */
        for (uint8_t i = 0; i < params->advertisingDataLen; ++i) {
            /* The advertising payload is a collection of key/value records where
             * byte 0: length of the record excluding this byte
             * byte 1: The key, it is the type of the data
             * byte [2..N] The value. N is equal to byte0 - 1 */
            const uint8_t record_length = params->advertisingData[i];
            if (record_length == 0) {
                continue;
            }
            const uint8_t type = params->advertisingData[i + 1];
            const uint8_t *value = params->advertisingData + i + 2;
 
            /* connect to a discoverable device */
            if ((type == GapAdvertisingData::FLAGS)
                && (*value & GapAdvertisingData::LE_GENERAL_DISCOVERABLE)) {
 
                /* abort timeout as the mode will end on disconnection */
                _event_queue.cancel(_on_duration_end_id);
 
                printf("We found a connectable device\r\n");
 
                ble_error_t error = _ble.gap().connect(
                    params->peerAddr, Gap::ADDR_TYPE_RANDOM_STATIC,
                    NULL, &connection_scan_params
                );
 
                if (error) {
                    printf("Error during Gap::connect\r\n");
                    /* since no connection will be attempted end the mode */
                    _event_queue.call(this, &GAPDevice::demo_mode_end);
                    return;
                }
 
                /* we may have already scan events waiting
                 * to be processed so we need to remember
                 * that we are already connecting and ignore them */
                _is_connecting = true;
 
                return;
            }
 
            i += record_length;
        }
    };
 
    /** This is called by Gap to notify the application we connected,
     *  in our case it immediately disconnects */
    void on_connect(const Gap::ConnectionCallbackParams_t *connection_event)
    {
        print_performance();
 
        printf("Connected in %dms\r\n", _demo_duration.read_ms());
 
        /* cancel the connect timeout since we connected */
        _event_queue.cancel(_on_duration_end_id);
 
        _event_queue.call_in(
            CONNECTION_DURATION, &_ble.gap(), &Gap::disconnect, Gap::REMOTE_USER_TERMINATED_CONNECTION
        );
    };
 
    /** This is called by Gap to notify the application we disconnected,
     *  in our case it calls demo_mode_end() to progress the demo */
    void on_disconnect(const Gap::DisconnectionCallbackParams_t *event)
    {
        printf("Disconnected\r\n");
 
        /* we have successfully disconnected ending the demo, move to next mode */
        _event_queue.call(this, &GAPDevice::demo_mode_end);
    };
 
    /** called if timeout is reached during advertising, scanning
     *  or connection initiation */
    void on_timeout(const Gap::TimeoutSource_t source)
    {
        _demo_duration.stop();
 
        switch (source) {
            case Gap::TIMEOUT_SRC_ADVERTISING:
                printf("Stopped advertising early due to timeout parameter\r\n");
                break;
            case Gap::TIMEOUT_SRC_SCAN:
                printf("Stopped scanning early due to timeout parameter\r\n");
                break;
            case Gap::TIMEOUT_SRC_CONN:
                printf("Failed to connect after scanning %d advertisements\r\n", _scan_count);
                _event_queue.call(this, &GAPDevice::print_performance);
                _event_queue.call(this, &GAPDevice::demo_mode_end);
                break;
            default:
                printf("Unexpected timeout\r\n");
                break;
        }
    };
 
    /** clean up after last run, cycle to the next mode and launch it */
    void demo_mode_end()
    {
        /* reset the demo ready for the next mode */
        _scan_count = 0;
        _demo_duration.stop();
        _demo_duration.reset();
 
        /* cycle through all demo modes */
        _set_index++;
 
        /* switch between advertising and scanning when we go
         * through all the params in the array */
        if (_set_index >= (_is_in_scanning_mode? SCAN_PARAM_SET_MAX : ADV_PARAM_SET_MAX)) {
            _set_index = 0;
            _is_in_scanning_mode = !_is_in_scanning_mode;
        }
 
        _ble.shutdown();
        _event_queue.break_dispatch();
    };
 
    /** print some information about our radio activity */
    void print_performance()
    {
        /* measure time from mode start, may have been stopped by timeout */
        uint16_t duration = _demo_duration.read_ms();
 
        if (_is_in_scanning_mode) {
            /* convert ms into timeslots for accurate calculation as internally
             * all durations are in timeslots (0.625ms) */
            uint16_t interval_ts = GapScanningParams::MSEC_TO_SCAN_DURATION_UNITS(
                scanning_params[_set_index].interval
            );
            uint16_t window_ts = GapScanningParams::MSEC_TO_SCAN_DURATION_UNITS(
                scanning_params[_set_index].window
            );
            uint16_t duration_ts = GapScanningParams::MSEC_TO_SCAN_DURATION_UNITS(
                duration
            );
            /* this is how long we scanned for in timeslots */
            uint16_t rx_ts = (duration_ts / interval_ts) * window_ts;
            /* convert to milliseconds */
            uint16_t rx_ms = (rx_ts * GapScanningParams::UNIT_0_625_MS) / 1000;
 
            printf("We have scanned for %dms with an interval of %d"
                    " timeslot and a window of %d timeslots\r\n",
                    duration, interval_ts, window_ts);
 
            printf("We have been listening on the radio for at least %dms\r\n", rx_ms);
 
        } else /* advertising */ {
 
            /* convert ms into timeslots for accurate calculation as internally
             * all durations are in timeslots (0.625ms) */
            uint16_t interval_ts = GapAdvertisingParams::MSEC_TO_ADVERTISEMENT_DURATION_UNITS(
                advertising_params[_set_index].interval
            );
            uint16_t duration_ts = GapAdvertisingParams::MSEC_TO_ADVERTISEMENT_DURATION_UNITS(
                duration
            );
            /* this is how many times we advertised */
            uint16_t events = duration_ts / interval_ts;
 
            printf("We have advertised for %dms"
                   " with an interval of %d timeslots\r\n",
                   duration, interval_ts);
 
            /* non-scannable and non-connectable advertising
             * skips rx events saving on power consumption */
            if (advertising_params[_set_index].adv_type
                == GapAdvertisingParams::ADV_NON_CONNECTABLE_UNDIRECTED) {
                printf("We created at least %d tx events\r\n", events);
            } else {
                printf("We created at least %d tx and rx events\r\n", events);
            }
        }
    };
 
    /** Schedule processing of events from the BLE middleware in the event queue. */
    void schedule_ble_events(BLE::OnEventsToProcessCallbackContext *context)
    {
        _event_queue.call(mbed::callback(&context->ble, &BLE::processEvents));
    };
 
    /** Blink LED to show we're running */
    void blink(void)
    {
        _led1 = !_led1;
    };
 
private:
    BLE                &_ble;
    events::EventQueue  _event_queue;
    DigitalOut          _led1;
 
    /* Keep track of our progress through demo modes */
    size_t              _set_index;
    bool                _is_in_scanning_mode;
    bool                _is_connecting;
 
    /* Remember the call id of the function on _event_queue
     * so we can cancel it if we need to end the mode early */
    int                 _on_duration_end_id;
 
    /* Measure performance of our advertising/scanning */
    Timer               _demo_duration;
    size_t              _scan_count;
};
 
int main()
{
    GAPDevice gap_device;
 
    while (1) {
        gap_device.run();
        wait_ms(TIME_BETWEEN_MODES_MS);
        printf("\r\nStarting next GAP demo mode\r\n");
    };
 
    return 0;
}
```