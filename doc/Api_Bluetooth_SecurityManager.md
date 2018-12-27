## SecurityManager
SecurityManager 处理蓝牙低功耗链路的身份验证和加密。配对和任选的粘合过程提供了这一点。SecurityManager 通过保存配对信息并在后续重新连接时重新使用来实现绑定。这节省了时间，因为不必再次执行配对。

配对过程可以产生一组在当前或后续连接期间使用的密钥。SecurityManager 处理这些，它们包括长期加密密钥（LTK），身份解析密钥（IRK）和连接签名解析密钥（CSRK）。SecurityManager 使用 LTK 加密后续连接，而无需再次配对。链路控制器使用 IRK 来识别使用随机可解析地址的对等体。该应用程序使用 CSRK 对签名数据进行签名和身份验证。

配对过程可以提供中间人保护（MITM）。SecurityManager 通过各种方式实现这一点，包括带外通信，具体取决于本地和对等设备的功能。

如果可能，SecurityManager 会永久存储密钥，以加快后续连接的安全请求。

安全请求可以基于属性要求显式地来自用户应用程序或者来自 GATT 服务器。

### 配对

根据您的要求和应用程序提供的功能，有几种方法可以在配对期间提供不同级别的安全性。该过程首先使用新连接的默认选项初始化 SecurityManager。您可以稍后更改每个链接或全局的某些设置。

init() 函数中的重要设置是 MITM 要求和 IO 功能。MITM 保护可以防止一个设备通过同时与两个设备配对来冒充其他设备的攻击。您可以通过独立通道在设备之间共享信息来实现此保护。两种设备的 IO 功能决定了使用的算法。有关详细信息，请参阅 BLUETOOTH SPECIFICATION 版本 5.0 | 第 3 卷，第 H 部分 - 2.3.5.1。您可以在使用 setIoCapability() 初始化后更改 IO 功能。这对所有后续配对生效。

依赖于椭圆曲线加密的安全连接提供最安全的配对。对安全连接的支持取决于支持它的两侧的栈和控制器。如果任何一方不支持它，则使用传统配对。这是较旧的配对标准。如果您需要更高的安全性，可以通过调用 allowLegacyPairing(false)；来禁用旧版配对。

### 配对中使用的带外（OOB）数据

通过 IO 功能共享此信息意味着用户交互，这会限制由于您可以预期传输的数据量限制而导致的保护程度。另一种解决方案是使用带外（OOB）通信来传输该数据。OOB 通信可以发送更多数据并使 MITM 攻击不太可能成功。应用程序必须交换 OOB 数据并将其提供给 SecurityManager。使用 setOOBDataUsage() 表示您要使用它。通过相同的调用，您可以设置用于传输 OOB 数据的通信通道本身是否可以抵御 MITM 保护 - 这将设置使用此数据的配对实现的链路安全级别。

### 签名

应用程序可能需要一定程度的安全性，从而确保数据传输来自可靠来源。您可以通过加密链接来实现此目的，这也提供了额外的机密性。当设备保持连接时加密是一个不错的选择，但如果设备仅定期连接以传输数据，则由于需要加密链路而引入延迟。如果您不需要机密性，GATT 服务器可能允许写入通过未加密的链接进行，但通过每个数据包中存在的签名进行身份验证。此签名依赖于在发送任何签名数据包之前在配对期间向对等方发送签名密钥。

### 持久性的安全信息

SecurityManager 在活动链接上存储其操作所需的所有数据。根据设备上可用的资源，它还存储已断开连接的设备的数据，这些设备已粘合，可在重新连接时重复使用。如果应用程序初始化了文件系统并且 SecurityManager 在 init() 调用期间收到了文件路径，则 SecurityManager 还可以在重置之间提供数据持久性。您必须通过调用 preserveBondingStateOnReset() 来启用它。如果异常终止，持久性可能会失败。如果资源太有限，SecurityManager 也可能会回退到非持久性实现。

### 如何使用

在调用任何其他 SecurityManager 函数之前，使用您选择的设置调用 init()。

SecurityManager 通过事件与您的应用程序通信。这些触发器必须通过调用 setSecurityManagerEventHandler() 函数来调用 EventHandler 中的调用。

最重要的过程是配对。您可以通过调用 requestPairing() 手动触发此操作。配对也可能是因为需要加密的应用程序通过调用 setLinkEncryption() 或通过 requestAuthentication() 需要 MITM 保护的应用程序。

您可以使用 setLinkSecurity() 隐式调用所有这些，以设置链接所需的安全性。SecurityManager 会触发实现设置安全级别所需的过程。您只能升级安全级别。要求 SecurityManager 的安全级别低于现有安全级别，但不会失败，但会导致通过当前级别的 linkEncryptionResult() 通知应用程序的事件（保持不变）。

选择的配对算法取决于 IO 功能和 OOB 使用设置。它们会生成适当的事件，EventHandler 必须处理这些事件。如果您的事件处理程序不支持所有调用，则不得设置 IO 功能或以触发它们的方式设置 OOB 使用，否则配对失败（通常通过超时）。

最简单的示例是没有 IO 功能的设备配对，也没有可用的 OOB 数据。这不提供任何 MITM 保护。配对（隐式触发或显式调用）导致在对等方调用 pairingRequest() 上生成事件。事件处理程序必须做出决定（在应用程序本身或基于用户交互）是否接受配对并调用 acceptPairing() 或 cancelPairing()。在 EventHandler 中调用 pairingResult() 的事件在两个对等体上传递结果。

## SecurityManager 类参考
[SecurityManager 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">class &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager_1_1_event_handler.html" rel="nofollow" target="_blank">EventHandler</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9f" rel="nofollow" target="_blank">Keypress_t</a> {<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9fab85f5cda528371b1c4e03ec53b0621e1" rel="nofollow" target="_blank">KEYPRESS_STARTED</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9fa3f205241c935ae7bdb5f4e0d4390ca68" rel="nofollow" target="_blank">KEYPRESS_ENTERED</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9fa5d2941019f7cb927d41e89b9d53bfe13" rel="nofollow" target="_blank">KEYPRESS_ERASED</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9fa19626cf47b25b583c2235fd48df36f9e" rel="nofollow" target="_blank">KEYPRESS_CLEARED</a>,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9fa6f4dd12565f4c7c1ce526b00105f27a1" rel="nofollow" target="_blank">KEYPRESS_COMPLETED</a><br>
			}</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8" rel="nofollow" target="_blank">SecurityMode_t</a> {<br>
			&nbsp;&nbsp;<strong>SECURITY_MODE_NO_ACCESS</strong>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8a50cf29349df7177506c564dccebc7f27" rel="nofollow" target="_blank">SECURITY_MODE_ENCRYPTION_OPEN_LINK</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8ae608194ac07bd6a983d2c09acdfa3bff" rel="nofollow" target="_blank">SECURITY_MODE_ENCRYPTION_NO_MITM</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8a9dba7dfe148c314452670c730231afe2" rel="nofollow" target="_blank">SECURITY_MODE_ENCRYPTION_WITH_MITM</a>,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8a0092ecfee9572c7b8c170386c5f4394d" rel="nofollow" target="_blank">SECURITY_MODE_SIGNED_NO_MITM</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8a48a2ba2aba4113886c7d28a6b401b046" rel="nofollow" target="_blank">SECURITY_MODE_SIGNED_WITH_MITM</a><br>
			}</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181" rel="nofollow" target="_blank">LinkSecurityStatus_t</a> { <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181a6447ca407e3af69512deaf45ed277c8e" rel="nofollow" target="_blank">NOT_ENCRYPTED</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181ac708b8607a1408d34a4d0ebc3112aa88" rel="nofollow" target="_blank">ENCRYPTION_IN_PROGRESS</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181ad711d928441940950dad3e2577f94be2" rel="nofollow" target="_blank">ENCRYPTED</a> }</td>
		</tr><tr><td>&nbsp;</td>
			<td>Defines possible security status or states. <a href="https://os.mbed.com/docs/v5.9/reference/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181" rel="nofollow" target="_blank">More...</a></td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityIOCapabilities_t</a> {<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2a5bf3fb101dcc5065c4ad359d67dd8cc1" rel="nofollow" target="_blank">IO_CAPS_DISPLAY_ONLY</a> = 0x00, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2a0f70426a370095ce360d6810121c9a30" rel="nofollow" target="_blank">IO_CAPS_DISPLAY_YESNO</a> = 0x01, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2a72e0db3e0e0ac1930d406ad7c7a7b518" rel="nofollow" target="_blank">IO_CAPS_KEYBOARD_ONLY</a> = 0x02, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2aa9938c31732f4393e6713fcdbb8ae004" rel="nofollow" target="_blank">IO_CAPS_NONE</a> = 0x03,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2a53b1db92e4eb3ed051880f97d62bcd3b" rel="nofollow" target="_blank">IO_CAPS_KEYBOARD_DISPLAY</a> = 0x04<br>
			}</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ec" rel="nofollow" target="_blank">SecurityCompletionStatus_t</a> {<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca097b4e9223f07b4bdffb2e57d746f39c" rel="nofollow" target="_blank">SEC_STATUS_SUCCESS</a> = 0x00, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca94ab9de3314f14833add789374de8e72" rel="nofollow" target="_blank">SEC_STATUS_TIMEOUT</a> = 0x01, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca4793dc1bb66a5a094d42841c6861e9b1" rel="nofollow" target="_blank">SEC_STATUS_PDU_INVALID</a> = 0x02, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca047eb3c84b81ae585fbf7fa94d06c211" rel="nofollow" target="_blank">SEC_STATUS_PASSKEY_ENTRY_FAILED</a> = 0x81,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca0d76ffb3edcfe9e1dcedc9e41f4242bd" rel="nofollow" target="_blank">SEC_STATUS_OOB_NOT_AVAILABLE</a> = 0x82, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecaf35f88107570ab302ae75aa110a84a19" rel="nofollow" target="_blank">SEC_STATUS_AUTH_REQ</a> = 0x83, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca72ef43dc45d58894b0128745fe610aa6" rel="nofollow" target="_blank">SEC_STATUS_CONFIRM_VALUE</a> = 0x84, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecae43b5d52e90b2d32b7663ad5ccab7837" rel="nofollow" target="_blank">SEC_STATUS_PAIRING_NOT_SUPP</a> = 0x85,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecafdc49570ece9e889a1413e7265b9f66f" rel="nofollow" target="_blank">SEC_STATUS_ENC_KEY_SIZE</a> = 0x86, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecaa4808a41df3fb0ca38d9279272a1e3a8" rel="nofollow" target="_blank">SEC_STATUS_SMP_CMD_UNSUPPORTED</a> = 0x87, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecacecd6e16ad90041d07547352d3273d13" rel="nofollow" target="_blank">SEC_STATUS_UNSPECIFIED</a> = 0x88, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecaa28b454f178a56c72b1a2d26bcddfe8d" rel="nofollow" target="_blank">SEC_STATUS_REPEATED_ATTEMPTS</a> = 0x89,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0eca634f31c8d2139832ebbd6211401c7e87" rel="nofollow" target="_blank">SEC_STATUS_INVALID_PARAMS</a> = 0x8A, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecafced937204250d74cde4e789f318cf54" rel="nofollow" target="_blank">SEC_STATUS_DHKEY_CHECK_FAILED</a> = 0x8B, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ecabcd4d8b46df29494a50ec8ee5c1648a4" rel="nofollow" target="_blank">SEC_STATUS_COMPARISON_FAILED</a> = 0x8C<br>
			}</td>
		</tr><tr><td style="vertical-align:top;">typedef uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a>[<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0eaf9e3736c31304159909c8bf758eae" rel="nofollow" target="_blank">PASSKEY_LEN</a>]</td>
		</tr><tr><td style="vertical-align:top;"><a id="ad12d9b2ebe7cc52b3498aa3aed4c634f" target="_blank"></a> typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">FunctionPointerWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html" rel="nofollow" target="_blank">SecurityManager</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>SecurityManagerShutdownCallback_t</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="ad50ffbedf0b4856db667a0985c7f05fb" target="_blank"></a> typedef <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">CallChainOfFunctionPointersWithContext</a>&lt; const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html" rel="nofollow" target="_blank">SecurityManager</a> * &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>SecurityManagerShutdownCallbackChain_t</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a142086e7a474a35dd14400bf4e9e3a4e" target="_blank"></a> typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>HandleSpecificEvent_t</strong>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;"><a id="addf068aec07a6fffd9256eded6812059" target="_blank"></a> typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>SecuritySetupInitiatedCallback_t</strong>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a>, bool allowBonding, bool requireMITM, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityIOCapabilities_t</a> iocaps)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa2ebd7be0ed4b3ddd0fefdd03e0f4c3a" target="_blank"></a> typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>SecuritySetupCompletedCallback_t</strong>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ec" rel="nofollow" target="_blank">SecurityCompletionStatus_t</a> status)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aac0080eb17fc1d64cb7cab0644865376" target="_blank"></a> typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>LinkSecuredCallback_t</strong>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8" rel="nofollow" target="_blank">SecurityMode_t</a> securityMode)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aebc7fdf654783163d66e568db2dcef1f" target="_blank"></a> typedef void(*&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>PasskeyDisplayCallback_t</strong>) (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a> passkey)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a72704e650c73dcc2a56c5e57d6c95aeb" rel="nofollow" target="_blank">init</a> (bool enableBonding=true, bool requireMITM=true, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityIOCapabilities_t</a> iocaps=<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2aa9938c31732f4393e6713fcdbb8ae004" rel="nofollow" target="_blank">IO_CAPS_NONE</a>, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a> passkey=NULL, bool signing=true, const char *dbFilepath=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aa595b5f33d6ff1729ae0b5444b6ed776" rel="nofollow" target="_blank">setDatabaseFilepath</a> (const char *dbFilepath=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a63f2de22a0113b928bf3ce9e2464ed51" rel="nofollow" target="_blank">reset</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a38a7b527a382d008310758d6df7c1cbd" rel="nofollow" target="_blank">preserveBondingStateOnReset</a> (bool enable)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aa7a5056701030ae59a6e7be6f62c5061" rel="nofollow" target="_blank">purgeAllBondingState</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a6df27f54f4c938e5dbf99ae96d17da78" rel="nofollow" target="_blank">generateWhitelistFromBondTable</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_whitelist__t.html" rel="nofollow" target="_blank">Gap::Whitelist_t</a> *whitelist) const</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a8e4bd2b013dcc8036023edf641e66f4d" rel="nofollow" target="_blank">requestPairing</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aecc448ca46cc725ebba38b2437f82042" rel="nofollow" target="_blank">acceptPairingRequest</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a4a7213ce3ecb9956cf482a6ac3cd81d4" rel="nofollow" target="_blank">cancelPairingRequest</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a8eacb37b66dd76954e5253d2f67f4bc2" rel="nofollow" target="_blank">setPairingRequestAuthorisation</a> (bool required=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a452fdff0d0f51eabb4809ce124f5fa00" rel="nofollow" target="_blank">allowLegacyPairing</a> (bool allow=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a5689b12b419783d129b5c6db584d811a" rel="nofollow" target="_blank">getSecureConnectionsSupport</a> (bool *enabled)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ae89dda25b800475cb270a391f60dbdc0" rel="nofollow" target="_blank">setIoCapability</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityIOCapabilities_t</a> iocaps)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ae211fbc261d3a013bdb7826bfeaec098" rel="nofollow" target="_blank">setDisplayPasskey</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a> passkey)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ace965717a446fcc19c1cfabf938f9bce" rel="nofollow" target="_blank">setLinkSecurity</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8" rel="nofollow" target="_blank">SecurityMode_t</a> securityMode)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a2b0fb0e108d14d9dc37bcdf938d24f65" rel="nofollow" target="_blank">setKeypressNotification</a> (bool enabled=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a834816bbf85aad384240751f97cfeab8" rel="nofollow" target="_blank">enableSigning</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, bool enabled=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#adfface1d4bc7dc771c2f73771a23276d" rel="nofollow" target="_blank">setHintFutureRoleReversal</a> (bool enable=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a89f65430bb57a1555c4cf86a2aee1168" rel="nofollow" target="_blank">getLinkEncryption</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1link__encryption__t.html" rel="nofollow" target="_blank">ble::link_encryption_t</a> *encryption)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ae94b5568945bd5febbf3d39d51e77498" rel="nofollow" target="_blank">setLinkEncryption</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1link__encryption__t.html" rel="nofollow" target="_blank">ble::link_encryption_t</a> encryption)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a8b803de1e05f0b827d670aa2bdfa71f6" rel="nofollow" target="_blank">setEncryptionKeyRequirements</a> (uint8_t minimumByteSize, uint8_t maximumByteSize)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ad009b3be0bbd553883f13175f92bd6c7" rel="nofollow" target="_blank">requestAuthentication</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abc9608d5ebbbd3a9737f9f23cd4575fb" rel="nofollow" target="_blank">generateOOB</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1address__t.html" rel="nofollow" target="_blank">ble::address_t</a> *address)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#adb76b9fe526326bf9b615aa49e1b9a3c" rel="nofollow" target="_blank">setOOBDataUsage</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, bool useOOB, bool OOBProvidesMITM=true)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ae7d129630dea3857f8d74e244a98d76e" rel="nofollow" target="_blank">confirmationEntered</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, bool confirmation)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a67675d55494c57819f1442989bab46cc" rel="nofollow" target="_blank">passkeyEntered</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a> passkey)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a14a252f96dd3813c7544ee71f1da0d03" rel="nofollow" target="_blank">sendKeypressNotification</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#abbd320ee6ac8ebd37db64dd12ad15d9f" rel="nofollow" target="_blank">Keypress_t</a> keypress)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a689d4c7135ec96fb7a1b6cb56eeb3da4" rel="nofollow" target="_blank">legacyPairingOobReceived</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1address__t.html" rel="nofollow" target="_blank">ble::address_t</a> *address, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#a43692f37cdeddbefc3cb9d0ce89be6cb" rel="nofollow" target="_blank">ble::oob_tk_t</a> *tk)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ac71d022c3f985e08ddbfc71e05389234" rel="nofollow" target="_blank">oobReceived</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structble_1_1address__t.html" rel="nofollow" target="_blank">ble::address_t</a> *address, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#a2eea11a282b3366b0cc542f7bc8cb371" rel="nofollow" target="_blank">ble::oob_lesc_value_t</a> *random, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#ab31b398667a6f93a13759c6fcde34a31" rel="nofollow" target="_blank">ble::oob_confirm_t</a> *confirm)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a56507be7f6289a883f9f64206bd729fc" rel="nofollow" target="_blank">getSigningKey</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, bool authenticated)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#affd9fabba70885a99de889009594c31c" rel="nofollow" target="_blank">onShutdown</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_function_pointer_with_context.html" rel="nofollow" target="_blank">SecurityManagerShutdownCallback_t</a> &amp;callback)</td>
		</tr><tr><td colspan="2"><a id="a925f684f292334f89b7c1af18bbfdf96" target="_blank"></a> template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>onShutdown</strong> (T *objPtr, void(T::*memberPtr)(const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html" rel="nofollow" target="_blank">SecurityManager</a> *))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_call_chain_of_function_pointers_with_context.html" rel="nofollow" target="_blank">SecurityManagerShutdownCallbackChain_t</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ac37f073251f187695baabed5544256dc" rel="nofollow" target="_blank">onShutdown</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#afa3d4312acc86034930fa18bd00ae8b8" rel="nofollow" target="_blank">setSecurityManagerEventHandler</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager_1_1_event_handler.html" rel="nofollow" target="_blank">EventHandler</a> *handler)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aa3adc103a8eb34bceecbae55b41426f2" rel="nofollow" target="_blank">getAddressesFromBondTable</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_gap_1_1_whitelist__t.html" rel="nofollow" target="_blank">Gap::Whitelist_t</a> &amp;addresses) const</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__common.html#ga6fb48b8f40e280c30d2ae3bd0c3712c4" rel="nofollow" target="_blank">ble_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aaf1e86da861649303d635e45f454d85b" rel="nofollow" target="_blank">getLinkSecurity</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0c8a48e91a4ff4e381513786808b9181" rel="nofollow" target="_blank">LinkSecurityStatus_t</a> *securityStatus)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aa559f180e6d1ec9eb40dd02c4f0856ac" rel="nofollow" target="_blank">onSecuritySetupInitiated</a> (SecuritySetupInitiatedCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#ab7af99eb60bd29e3d97d8234663feb10" rel="nofollow" target="_blank">onSecuritySetupCompleted</a> (SecuritySetupCompletedCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#af466daf0228aa1f0c15c1ae059d89302" rel="nofollow" target="_blank">onLinkSecured</a> (LinkSecuredCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a3559cca2e2b4ecec7338045fa68c230b" rel="nofollow" target="_blank">onSecurityContextStored</a> (HandleSpecificEvent_t callback)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a249c414e46fc08149951f2d136ddb6ff" rel="nofollow" target="_blank">onPasskeyDisplay</a> (PasskeyDisplayCallback_t callback)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aadcaf3d09f4980bb1dbc3436f6b42849" rel="nofollow" target="_blank">processSecuritySetupInitiatedEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, bool allowBonding, bool requireMITM, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a57b655669b9196457b0ccf263e2033c2" rel="nofollow" target="_blank">SecurityIOCapabilities_t</a> iocaps)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a5b3e2888570bc1eb87227f551b933f6b" rel="nofollow" target="_blank">processSecuritySetupCompletedEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a055f2cf56ca86881944e8c6d0a85c0ec" rel="nofollow" target="_blank">SecurityCompletionStatus_t</a> status)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a71449fbc4087dce12d9f10b521ccc601" rel="nofollow" target="_blank">processLinkSecuredEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a60f7b1ca0294bc7e18380cad8a5288b8" rel="nofollow" target="_blank">SecurityMode_t</a> securityMode)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a7325c41d311cc9e2dd973acbbd539e37" rel="nofollow" target="_blank">processSecurityContextStoredEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a65872b3277f571174da1ff3534580b7c" rel="nofollow" target="_blank">processPasskeyDisplayEvent</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespaceble.html#adecd79e33c3c569a6d393f99b031e89f" rel="nofollow" target="_blank">ble::connection_handle_t</a> connectionHandle, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#aee1598968e7065de3708c09c584afe07" rel="nofollow" target="_blank">Passkey_t</a> passkey)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共属性</td>
		</tr><tr><td style="vertical-align:top;">static const unsigned&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager.html#a0eaf9e3736c31304159909c8bf758eae" rel="nofollow" target="_blank">PASSKEY_LEN</a> = 6</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a7ffac882df46b36c040bae28d33632a0" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_security_manager_1_1_event_handler.html" rel="nofollow" target="_blank">EventHandler</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>eventHandler</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="ae3aa3a4f90d889e706c47869f0627879" target="_blank"></a> LegacyEventHandler&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>defaultEventHandler</strong></td>
		</tr></tbody></table>

## SecurityManager 示例
SecurityManager 示例演示了中央连接和外围连接，执行基本配对和设置链接安全性。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-SM/file/fcb1e0b995a9/source/main.cpp)       
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
#include "SecurityManager.h"
 
/** This example demonstrates all the basic setup required
 *  for pairing and setting up link security both as a central and peripheral
 *
 *  The example is implemented as two classes, one for the peripheral and one
 *  for central inheriting from a common base. They are run in sequence and
 *  require a peer device to connect to. During the peripheral device demonstration
 *  a peer device is required to connect. In the central device demonstration
 *  this peer device will be scanned for and connected to - therefore it should
 *  be advertising with the same address as when it connected.
 *
 *  During the test output is written on the serial connection to monitor its
 *  progress.
 */
 
static const uint8_t DEVICE_NAME[] = "SM_device";
 
/* for demonstration purposes we will store the peer device address
 * of the device that connects to us in the first demonstration
 * so we can use its address to reconnect to it later */
static BLEProtocol::AddressBytes_t peer_address;
 
/** Base class for both peripheral and central. The same class that provides
 *  the logic for the application also implements the SecurityManagerEventHandler
 *  which is the interface used by the Security Manager to communicate events
 *  back to the applications. You can provide overrides for a selection of events
 *  your application is interested in.
 */
class SMDevice : private mbed::NonCopyable<SMDevice>,
                 public SecurityManager::EventHandler
{
public:
    SMDevice(BLE &ble, events::EventQueue &event_queue, BLEProtocol::AddressBytes_t &peer_address) :
        _led1(LED1, 0),
        _ble(ble),
        _event_queue(event_queue),
        _peer_address(peer_address),
        _handle(0),
        _is_connecting(false) { };
 
    virtual ~SMDevice()
    {
        if (_ble.hasInitialized()) {
            _ble.shutdown();
        }
    };
 
    /** Start BLE interface initialisation */
    void run()
    {
        ble_error_t error;
 
        /* to show we're running we'll blink every 500ms */
        _event_queue.call_every(500, this, &SMDevice::blink);
 
        if (_ble.hasInitialized()) {
            printf("Ble instance already initialised.\r\n");
            return;
        }
 
        /* this will inform us off all events so we can schedule their handling
         * using our event queue */
        _ble.onEventsToProcess(
            makeFunctionPointer(this, &SMDevice::schedule_ble_events)
        );
 
        /* handle timeouts, for example when connection attempts fail */
        _ble.gap().onTimeout(
            makeFunctionPointer(this, &SMDevice::on_timeout)
        );
 
        error = _ble.init(this, &SMDevice::on_init_complete);
 
        if (error) {
            printf("Error returned by BLE::init.\r\n");
            return;
        }
 
        /* this will not return until shutdown */
        _event_queue.dispatch_forever();
    };
 
    /* event handler functions */
 
    /** Respond to a pairing request. This will be called by the stack
     * when a pairing request arrives and expects the application to
     * call acceptPairingRequest or cancelPairingRequest */
    virtual void pairingRequest(
        ble::connection_handle_t connectionHandle
    ) {
        printf("Pairing requested. Authorising.\r\n");
        _ble.securityManager().acceptPairingRequest(connectionHandle);
    }
 
    /** Inform the application of a successful pairing. Terminate the demonstration. */
    virtual void pairingResult(
        ble::connection_handle_t connectionHandle,
        SecurityManager::SecurityCompletionStatus_t result
    ) {
        if (result == SecurityManager::SEC_STATUS_SUCCESS) {
            printf("Pairing successful\r\n");
        } else {
            printf("Pairing failed\r\n");
        }
 
        /* disconnect in 500 ms */
        _event_queue.call_in(
            500, &_ble.gap(),
            &Gap::disconnect, _handle, Gap::REMOTE_USER_TERMINATED_CONNECTION
        );
    }
 
    /** Inform the application of change in encryption status. This will be
     * communicated through the serial port */
    virtual void linkEncryptionResult(
        ble::connection_handle_t connectionHandle,
        ble::link_encryption_t result
    ) {
        if (result == ble::link_encryption_t::ENCRYPTED) {
            printf("Link ENCRYPTED\r\n");
        } else if (result == ble::link_encryption_t::ENCRYPTED_WITH_MITM) {
            printf("Link ENCRYPTED_WITH_MITM\r\n");
        } else if (result == ble::link_encryption_t::NOT_ENCRYPTED) {
            printf("Link NOT_ENCRYPTED\r\n");
        }
    }
 
private:
    /** Override to start chosen activity when initialisation completes */
    virtual void start() = 0;
 
    /** This is called when BLE interface is initialised and starts the demonstration */
    void on_init_complete(BLE::InitializationCompleteCallbackContext *event)
    {
        ble_error_t error;
 
        if (event->error) {
            printf("Error during the initialisation\r\n");
            return;
        }
 
        /* If the security manager is required this needs to be called before any
         * calls to the Security manager happen. */
        error = _ble.securityManager().init();
 
        if (error) {
            printf("Error during init %d\r\n", error);
            return;
        }
 
        /* Tell the security manager to use methods in this class to inform us
         * of any events. Class needs to implement SecurityManagerEventHandler. */
        _ble.securityManager().setSecurityManagerEventHandler(this);
 
        /* print device address */
        Gap::AddressType_t addr_type;
        Gap::Address_t addr;
        _ble.gap().getAddress(&addr_type, addr);
        printf("Device address: %02x:%02x:%02x:%02x:%02x:%02x\r\n",
               addr[5], addr[4], addr[3], addr[2], addr[1], addr[0]);
 
        /* when scanning we want to connect to a peer device so we need to
         * attach callbacks that are used by Gap to notify us of events */
        _ble.gap().onConnection(this, &SMDevice::on_connect);
        _ble.gap().onDisconnection(this, &SMDevice::on_disconnect);
 
        /* start test in 500 ms */
        _event_queue.call_in(500, this, &SMDevice::start);
    };
 
    /** This is called by Gap to notify the application we connected */
    virtual void on_connect(const Gap::ConnectionCallbackParams_t *connection_event) = 0;
 
    /** This is called by Gap to notify the application we disconnected,
     *  in our case it ends the demonstration. */
    void on_disconnect(const Gap::DisconnectionCallbackParams_t *event)
    {
        printf("Disconnected - demonstration ended \r\n");
        _event_queue.break_dispatch();
    };
 
    /** End demonstration unexpectedly. Called if timeout is reached during advertising,
     * scanning or connection initiation */
    void on_timeout(const Gap::TimeoutSource_t source)
    {
        printf("Unexpected timeout - aborting \r\n");
        _event_queue.break_dispatch();
    };
 
    /** Schedule processing of events from the BLE in the event queue. */
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
    DigitalOut _led1;
 
protected:
    BLE &_ble;
    events::EventQueue &_event_queue;
    BLEProtocol::AddressBytes_t &_peer_address;
    ble::connection_handle_t _handle;
    bool _is_connecting;
};
 
/** A peripheral device will advertise, accept the connection and request
 * a change in link security. */
class SMDevicePeripheral : public SMDevice {
public:
    SMDevicePeripheral(BLE &ble, events::EventQueue &event_queue, BLEProtocol::AddressBytes_t &peer_address)
        : SMDevice(ble, event_queue, peer_address) { }
 
    virtual void start()
    {
        /* Set up and start advertising */
 
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
 
        /* advertise to everyone */
        _ble.gap().setAdvertisingType(GapAdvertisingParams::ADV_CONNECTABLE_UNDIRECTED);
        /* how many milliseconds between advertisements, lower interval
         * increases the chances of being seen at the cost of more power */
        _ble.gap().setAdvertisingInterval(20);
        _ble.gap().setAdvertisingTimeout(0);
 
        error = _ble.gap().startAdvertising();
 
        if (error) {
            printf("Error during Gap::startAdvertising.\r\n");
            return;
        }
 
        /** This tells the stack to generate a pairingRequest event
         * which will require this application to respond before pairing
         * can proceed. Setting it to false will automatically accept
         * pairing. */
        _ble.securityManager().setPairingRequestAuthorisation(true);
    };
 
    /** This is called by Gap to notify the application we connected,
     *  in our case it immediately requests a change in link security */
    virtual void on_connect(const Gap::ConnectionCallbackParams_t *connection_event)
    {
        ble_error_t error;
 
        /* remember the device that connects to us now so we can connect to it
         * during the next demonstration */
        memcpy(_peer_address, connection_event->peerAddr, sizeof(_peer_address));
 
        /* store the handle for future Security Manager requests */
        _handle = connection_event->handle;
 
        /* Request a change in link security. This will be done
         * indirectly by asking the master of the connection to
         * change it. Depending on circumstances different actions
         * may be taken by the master which will trigger events
         * which the applications should deal with. */
        error = _ble.securityManager().setLinkSecurity(
            _handle,
            SecurityManager::SECURITY_MODE_ENCRYPTION_NO_MITM
        );
 
        if (error) {
            printf("Error during SM::setLinkSecurity %d\r\n", error);
            return;
        }
    };
};
 
/** A central device will scan, connect to a peer and request pairing. */
class SMDeviceCentral : public SMDevice {
public:
    SMDeviceCentral(BLE &ble, events::EventQueue &event_queue, BLEProtocol::AddressBytes_t &peer_address)
        : SMDevice(ble, event_queue, peer_address) { }
 
    virtual void start()
    {
        /* start scanning and attach a callback that will handle advertisements
         * and scan requests responses */
        ble_error_t error = _ble.gap().startScan(this, &SMDeviceCentral::on_scan);
 
        if (error) {
            printf("Error during Gap::startScan %d\r\n", error);
            return;
        }
    }
 
    /** Look at scan payload to find a peer device and connect to it */
    void on_scan(const Gap::AdvertisementCallbackParams_t *params)
    {
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
 
            /* connect to the same device that connected to us */
            if (memcmp(params->peerAddr, _peer_address, sizeof(_peer_address)) == 0) {
 
                ble_error_t error = _ble.gap().connect(
                    params->peerAddr, params->addressType,
                    NULL, NULL
                );
 
                if (error) {
                    printf("Error during Gap::connect %d\r\n", error);
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
     *  in our case it immediately request pairing */
    virtual void on_connect(const Gap::ConnectionCallbackParams_t *connection_event)
    {
        ble_error_t error;
 
        /* store the handle for future Security Manager requests */
        _handle = connection_event->handle;
 
        /* in this example the local device is the master so we request pairing */
        error = _ble.securityManager().requestPairing(_handle);
 
        if (error) {
            printf("Error during SM::requestPairing %d\r\n", error);
            return;
        }
 
        /* upon pairing success the application will disconnect */
    };
};
 
int main()
{
    BLE& ble = BLE::Instance();
    events::EventQueue queue;
 
    {
        printf("\r\n PERIPHERAL \r\n\r\n");
        SMDevicePeripheral peripheral(ble, queue, peer_address);
        peripheral.run();
    }
 
    {
        printf("\r\n CENTRAL \r\n\r\n");
        SMDeviceCentral central(ble, queue, peer_address);
        central.run();
    }
 
    return 0;
}
```