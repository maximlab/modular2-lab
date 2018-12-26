## TCPServer

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.png">

TCPServer 类层次结构</div>                                                           
TCPServer 类提供接受传入 TCP 连接的能力。listen 成员函数将服务器设置为侦听传入连接，accept 成员函数在传入连接上设置有状态 TCPSocket 实例。

构造函数接受 NetworkStack 指针以打开指定 NetworkInterface 上的套接字。如果未在构造函数中传递 NetworkStack 指针，则必须调用 open 以初始化套接字。

有关 TCP connect，send 和 recv API 的信息，请参阅 TCPSocket 类。

## TCPServer 类参考
[TCPServer 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.html#a3a5e3cfe42c676ed71f2bc58dcc92bda" rel="nofollow" target="_blank">TCPServer</a> ()</td>
		</tr><tr><td colspan="2">template&lt;typename S &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.html#aeafe13def9c1aef541c252df65cf74f6" rel="nofollow" target="_blank">TCPServer</a> (S *stack)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.html#abc497ac52355e53986a6a1bd1acb9581" rel="nofollow" target="_blank">~TCPServer</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__netsocket.html#ga67a8f07758d2ee2a1809293fa52bdf14" rel="nofollow" target="_blank">nsapi_error_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_server.html#a604560d7416501f200aa5ce92a61a5aa" rel="nofollow" target="_blank">accept</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html" rel="nofollow" target="_blank">TCPSocket</a> *connection, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> *address=NULL)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html" rel="nofollow" target="_blank">TCPSocket</a></td>
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
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_t_c_p_socket.html" rel="nofollow" target="_blank">TCPSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a14f9425c336286c39d9a2bdf340827d3" target="_blank"></a> virtual nsapi_protocol_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get_proto</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_internet_socket.html" rel="nofollow" target="_blank">InternetSocket</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a49fb7a4b6b486043c2400b69eea7a3e9" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>event</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5073d971b8c5c3adcf91c8bf46f5492e" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>modify_multicast_group</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_socket_address.html" rel="nofollow" target="_blank">SocketAddress</a> &amp;address, nsapi_socket_option_t socketopt)</td>
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

## TCPServer 示例
这是一个 TCP 服务器示例。它接受单个 telnet 客户端连接并发送缓冲区数据。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-tcp-server/file/ddb5698aa782/main.cpp)   
```
#include "mbed.h"
#include "EthernetInterface.h"
#include "TCPServer.h"
#include "TCPSocket.h"
 
int main()
{
    printf("TCP server example\n");
    
    EthernetInterface eth;
    eth.connect();
    
    printf("The Server IP address is '%s'\n", eth.get_ip_address());
    
    TCPServer srv;
    TCPSocket client_sock;
    SocketAddress client_addr;
    char *buffer = new char[256];
    
    /* Open the server on ethernet stack */
    srv.open(&eth);
    
    /* Bind the HTTP port (TCP 80) to the server */
    srv.bind(eth.get_ip_address(), 23);
    
    /* Can handle x simultaneous connections */
    srv.listen(1);
 
    srv.accept(&client_sock, &client_addr);
    printf("Accepted %s:%d\n", client_addr.get_ip_address(), 
                    client_addr.get_port());
    strcpy(buffer, "Hello \n\r");
    client_sock.send(buffer, strlen(buffer));
    client_sock.recv(buffer, 256);
    
    client_sock.close();
    delete[] buffer;
}
```