## TCPSocket

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.png">

TCPSocket 类层次结构</div>                                                           
TCPSocket 类提供通过 TCP 发送数据流的能力。TCPSockets 维护一个以 connect 成员函数开始的有状态连接。成功连接到服务器后，您可以使用 send 和 recv 成员函数来发送和接收数据（类似于从文件写入或读取）。

构造函数接受 NetworkStack 指针以打开指定 NetworkInterface 上的套接字。如果你没有传入构造函数，那么你必须调用 open 来初始化套接字。

有关 TCP 服务器功能，请参阅 TCPServer 类。

## TCPSocket 类参考
[TCPSocket 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#a7a50427a401d1a6f3209d51818bad901" rel="nofollow" target="_blank">TCPSocket</a> ()</td>
		</tr><tr><td colspan="2">template&lt;typename S &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#ae2e6d1c7dffb42c29313e304bcd205fa" rel="nofollow" target="_blank">TCPSocket</a> (S *stack)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#af357e6923a0f8adbbb8e46fab4523991" rel="nofollow" target="_blank">~TCPSocket</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#aa0caba129c72974e24cf0d3a81789460" rel="nofollow" target="_blank">join_multicast_group</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#a471e8107d72278456280f4e30c9c65bd" rel="nofollow" target="_blank">connect</a> (const char *host, uint16_t port)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#af96c845ca15f6ec5d2a8f4b48f376c60" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#ae51e66cb0d7b918373fe8c2793872b21" rel="nofollow" target="_blank">send</a> (const void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#ac5f7d7ea02ce27bde53f6c7da0b2b75a" rel="nofollow" target="_blank">recv</a> (void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#aab0330fae1d064aadbb15cdd9d9d3303" rel="nofollow" target="_blank">sendto</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address, const void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#a333c51df15e492839066319a890bcbb1" rel="nofollow" target="_blank">recvfrom</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address, void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html" rel="nofollow" target="_blank">TCPSocket</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#ac7d02ef109d2d3a48b6dcaa38869de80" rel="nofollow" target="_blank">accept</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> *<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__platform__error.html#gae04dbb69042f37c4c595fc9beb4ca754" rel="nofollow" target="_blank">error</a>=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html#a60e9fc1a655a660b877a887616054a0b" rel="nofollow" target="_blank">listen</a> (int backlog=1)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#aa05d862f91ae89c523f30c8af75e4bae" rel="nofollow" target="_blank">~InternetSocket</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#ab083ab1197380e8103fbab7984c15ee9" rel="nofollow" target="_blank">open</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_stack.html" rel="nofollow" target="_blank">NetworkStack</a> *stack)</td>
		</tr><tr><td colspan="2"><a id="a9dc20e3df94b86163f06f262d684b6b3" target="_blank"></a> template&lt;typename S &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>open</strong> (S *stack)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#aad12458501c74f50d6757737e47a8f83" rel="nofollow" target="_blank">close</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#a94a4749f37ccaf163cca49cc90f1a84d" rel="nofollow" target="_blank">join_multicast_group</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#a1ba0b15e78863fb8edc1b185ecadfc61" rel="nofollow" target="_blank">leave_multicast_group</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#a296fc493cafabf859e3fdacade5ec592" rel="nofollow" target="_blank">bind</a> (uint16_t port)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#a16c7ed7735fd91b9c20d3741238cd716" rel="nofollow" target="_blank">bind</a> (const char *address, uint16_t port)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#a578d50a9926d81499845efa97ec13650" rel="nofollow" target="_blank">bind</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#afc6f0403ac10e44f4a3bbdacdf309a72" rel="nofollow" target="_blank">set_blocking</a> (bool blocking)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#abb21070bdf7a8cc33e70032c65714927" rel="nofollow" target="_blank">set_timeout</a> (int timeout)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a2f8d2215c2e83353c9080ea5f0ef22a9" target="_blank"></a> virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>setsockopt</strong> (int level, int optname, const void *optval, unsigned optlen)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a096a18fbd774fb069cc8998c01cbfce5" target="_blank"></a> virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getsockopt</strong> (int level, int optname, void *optval, unsigned *optlen)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#ac0aea91a0a949dd810fb09183a3c1d36" rel="nofollow" target="_blank">sigio</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#aab5dd525974d4c60144484a41aeb15b4" rel="nofollow" target="_blank">attach</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html#ae9f70a80141145e0d9a34daae12cec36" rel="nofollow" target="_blank">attach</a> (T *obj, M method)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket.html" rel="nofollow" target="_blank">Socket</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket.html#a594ef9479fc328ef703294d5c98fd024" rel="nofollow" target="_blank">~Socket</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="a14f9425c336286c39d9a2bdf340827d3" target="_blank"></a> virtual nsapi_protocol_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get_proto</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a49fb7a4b6b486043c2400b69eea7a3e9" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>event</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5073d971b8c5c3adcf91c8bf46f5492e" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>modify_multicast_group</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address, nsapi_socket_option_t socketopt)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2"><a name="friends" target="_blank"></a> 友元</td>
		</tr><tr><td style="vertical-align:top;"><a id="ae4cfdb1814d91a8d28dadb49adda68f0" target="_blank"></a> class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>TCPServer</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a83c0e55a5a5092f441c544f7299aa55a" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_network_stack.html" rel="nofollow" target="_blank">NetworkStack</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_stack</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a124b97d046f942c12967a825c8ffafff" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gad0273762e5e5643dda87a74c7de45b69" rel="nofollow" target="_blank">nsapi_socket_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_socket</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a584da21ee339f54ef9d60bf07f69b5e2" target="_blank"></a> uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_timeout</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7931e0b87d5e10113996e27334132895" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_event</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a14330e945bb819dfdbad7ab95a4a7801" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_callback</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7d3d7ce42b0a126e9f9de7f7f6916b28" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html" rel="nofollow" target="_blank">rtos::EventFlags</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_event_flag</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2cf4c006cb717e11af6e61ecfa527f73" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html" rel="nofollow" target="_blank">rtos::Mutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_lock</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a44bf90a1fff04f901523d08779a508cd" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_remote_peer</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="adeced3c6eb1c6eec71392111d2e8a6bb" target="_blank"></a> uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_readers</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a239afffe97dfa06b65e838bd1e84a509" target="_blank"></a> uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_writers</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2d874f0aad887e10dab736469ed40205" target="_blank"></a> volatile unsigned&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_pending</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a455e79e1aafb026eb880165885dc4bf0" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_factory_allocated</strong></td>
		</tr><tr><td colspan="2">&nbsp;从中继承的静态保护属性 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="ad07a7af6ce43dc380378746367d04e52" target="_blank"></a> static const int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>READ_FLAG</strong> = 0x1u</td>
		</tr><tr><td style="vertical-align:top;"><a id="a7125b3e92b5027796c967d19a13c5c55" target="_blank"></a> static const int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>WRITE_FLAG</strong> = 0x2u</td>
		</tr><tr><td style="vertical-align:top;"><a id="a85959748d77ec9b2b058da8e6a6cb59b" target="_blank"></a> static const int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>FINISHED_FLAG</strong> = 0x3u</td>
		</tr></tbody></table>

## TCPSocket 示例
这是使用 ESP8266 模块的 HTTP 事务的 TCP 客户端示例。

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
以下是通过以太网接口进行 HTTP 事务的 TCP 客户端示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/TCPSocket_Example/file/6b383744246e/main.cpp)  
```
#include "mbed.h"
#include "EthernetInterface.h"
 
// Network interface
EthernetInterface net;
 
// Socket demo
int main() {
    // Bring up the ethernet interface
    printf("Ethernet socket example\n");
    net.connect();
 
    // Show the network address
    const char *ip = net.get_ip_address();
    printf("IP address is: %s\n", ip ? ip : "No IP");
 
    // Open a socket on the network interface, and create a TCP connection to mbed.org
    TCPSocket socket;
    socket.open(&net);
    socket.connect("developer.mbed.org", 80);
 
    // Send a simple http request
    char sbuffer[] = "GET / HTTP/1.1\r\nHost: developer.mbed.org\r\n\r\n";
    int scount = socket.send(sbuffer, sizeof sbuffer);
    printf("sent %d [%.*s]\n", scount, strstr(sbuffer, "\r\n")-sbuffer, sbuffer);
 
    // Recieve a simple http response and print out the response line
    char rbuffer[64];
    int rcount = socket.recv(rbuffer, sizeof rbuffer);
    printf("recv %d [%.*s]\n", rcount, strstr(rbuffer, "\r\n")-rbuffer, rbuffer);
 
    // Close the socket to return its memory and bring down the network interface
    socket.close();
 
    // Bring down the ethernet interface
    net.disconnect();
    printf("Done\n");
}
```