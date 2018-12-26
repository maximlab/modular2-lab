## UDPSocket

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.png">

UDPSocket 类层次结构</div>                                                           
UDPSocket 类提供了使用 sendto 和 recvfrom 成员函数通过 UDP 发送数据包的功能。数据包可能丢失或无序到达，因此我们建议您在需要保证交付时使用 TCPSocket。

构造函数接受 NetworkStack 指针以打开指定 NetworkInterface 上的套接字。如果你没有传入构造函数，那么你必须调用 open 来初始化套接字。

## UDPSocket 类参考
[UDPSocket 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#a4f86f3023f5a08f6355802599a10e100" rel="nofollow" target="_blank">UDPSocket</a> ()</td>
		</tr><tr><td colspan="2">template&lt;typename S &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#af09292a7b44b4a508b2b478ae1024847" rel="nofollow" target="_blank">UDPSocket</a> (S *stack)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#adb1a5254938e5acf5d44ff7a347e9f0a" rel="nofollow" target="_blank">~UDPSocket</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#abe14d973c14435becb63e4f42c0cc5f4" rel="nofollow" target="_blank">sendto</a> (const char *host, uint16_t port, const void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#a5794a2e44ed849bba30570c0b517a95f" rel="nofollow" target="_blank">sendto</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address, const void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#aaaf23e726923a22a9e23bd56fdf09346" rel="nofollow" target="_blank">recvfrom</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address, void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#a5eb44f35c21cc31ab4911c22fed416cd" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#a1d56b9258ad06ab5a36716f58ab85509" rel="nofollow" target="_blank">send</a> (const void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga1aef0d1a2599df92bb4499b5c4262d25" rel="nofollow" target="_blank">nsapi_size_or_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#ae99799cc6012506759439170845d2771" rel="nofollow" target="_blank">recv</a> (void *data, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#gaeaef3ae1ffcf0d50c66fa2ca37621281" rel="nofollow" target="_blank">nsapi_size_t</a> size)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket.html" rel="nofollow" target="_blank">Socket</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#ab3f572c3a4a8b60b9235c1c814a9ea06" rel="nofollow" target="_blank">accept</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a> *<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__platform__error.html#gae04dbb69042f37c4c595fc9beb4ca754" rel="nofollow" target="_blank">error</a>=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_u_d_p_socket.html#aa11ae4e2775b4f23059cbb0df6a5f65f" rel="nofollow" target="_blank">listen</a> (int backlog=1)</td>
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
		</tr><tr><td style="vertical-align:top;"><a id="aa500ec94e57685ab96b58a932ea2d6b9" target="_blank"></a> virtual nsapi_protocol_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get_proto</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a49fb7a4b6b486043c2400b69eea7a3e9" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>event</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5073d971b8c5c3adcf91c8bf46f5492e" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>modify_multicast_group</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address, nsapi_socket_option_t socketopt)</td>
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

## UDPSocket 示例
以下是通过向 NIST Internet 时间服务发送请求来读取当前 UTC 时间的 UDP 示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets/file/cf516d904427/main.cpp)  
```
#include "mbed.h"
#include "EthernetInterface.h"
 
// Network interface
EthernetInterface net;
 
// Time protocol implementation : Address: time.nist.gov UDPPort: 37  
 
typedef struct {
    uint32_t secs;         // Transmit Time-stamp seconds.
}ntp_packet;
 
int main() {
    // Bring up the ethernet interface
    printf("UDP Socket example\n");
    if(0 != net.connect()) {
        printf("Error connecting\n");
        return -1;
    }
 
    // Show the network address
    const char *ip = net.get_ip_address();
    printf("IP address is: %s\n", ip ? ip : "No IP");
        
    UDPSocket sock(&net);
    SocketAddress sockAddr;
 
    char out_buffer[] = "time";
    if(0 > sock.sendto("time.nist.gov", 37, out_buffer, sizeof(out_buffer))) {
        printf("Error sending data\n");
        return -1;
    }
    
    ntp_packet in_data;
    int n = sock.recvfrom(&sockAddr, &in_data, sizeof(ntp_packet));
    in_data.secs = ntohl( in_data.secs ) - 2208988800;    // 1900-1970
    printf("Time Received %lu seconds since 1/01/1900 00:00 GMT\n", 
                        (uint32_t)in_data.secs);
    printf("Time = %s", ctime(( const time_t* )&in_data.secs));
    
    printf("Time Server Address: %s Port: %d\n\r", 
                               sockAddr.get_ip_address(), sockAddr.get_port());
    
    // Close the socket and bring down the network interface
    sock.close();
    net.disconnect();
    return 0;
}
```