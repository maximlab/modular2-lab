## Serial
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.png">

Serial 类层次结构</div>

Serial 接口提供 UART 功能。串行链路有两个单向通道，一个用于发送，一个用于接收。链接是异步的，因此必须将串行链路的两端配置为使用相同的设置。

其中一个串行连接使用 Arm Mbed USB 端口，可让您轻松与主机 PC 通信。

## Serial 类参考
[mbed::Serial 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.html#a9a125d98683a95be3c36b0cdacd30dc7" rel="nofollow" target="_blank">Serial</a> (PinName tx, PinName rx, const char *name=NULL, int <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ac777186012bec315ebdf8320d5c4d917" rel="nofollow" target="_blank">baud</a>=MBED_CONF_PLATFORM_DEFAULT_SERIAL_BAUD_RATE)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.html#a3a2389412e9ebd089a6facca3140a9ef" rel="nofollow" target="_blank">Serial</a> (PinName tx, PinName rx, int <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ac777186012bec315ebdf8320d5c4d917" rel="nofollow" target="_blank">baud</a>)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa81c8fc54e8534e70fbfd0707e3f166b" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>readable</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5863bd9b34da8251f4a57efede49b672" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>writable</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a0585647fe570bde9bcbc6c2516ca5ba9" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>writeable</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">mbed::SerialBase</a></td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ac777186012bec315ebdf8320d5c4d917" rel="nofollow" target="_blank">baud</a> (int baudrate)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a768f1e9fd9e14c787f693745fa2538a4" rel="nofollow" target="_blank">format</a> (int bits=8, Parity parity=SerialBase::None, int stop_bits=1)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a3f9c53a49de1101826404a3571249847" rel="nofollow" target="_blank">readable</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a1e3bf16c00b7d3d0a28e704d816dc9a7" rel="nofollow" target="_blank">writeable</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a8907fdeae10761f81c1a6a3e50d0be51" rel="nofollow" target="_blank">attach</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func, IrqType type=RxIrq)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a8112b091b97f49ca14181807463c51e6" rel="nofollow" target="_blank">attach</a> (T *obj, void(T::*method)(), IrqType type=RxIrq)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#adfd1e5b2e7983bd2e7d6768909aceb93" rel="nofollow" target="_blank">attach</a> (T *obj, void(*method)(T *), IrqType type=RxIrq)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#aada18908c9152ef4d698f88e306799aa" rel="nofollow" target="_blank">send_break</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a7dd4b2c92705e106f6c67cdb9fd5bd0f" rel="nofollow" target="_blank">set_flow_control</a> (Flow type, PinName flow1=NC, PinName flow2=NC)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#abee1597dcb5e2dfcdfb42ed9fe871e37" rel="nofollow" target="_blank">write</a> (const uint8_t *buffer, int length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=SERIAL_EVENT_TX_COMPLETE)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ab5d7cec0c5b759ba1e3635e25f39c20c" rel="nofollow" target="_blank">write</a> (const uint16_t *buffer, int length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=SERIAL_EVENT_TX_COMPLETE)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ae6b3fdf6a0daad673010c7d8891bf610" rel="nofollow" target="_blank">abort_write</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a071189f96cf852565ff04fcecf08d386" rel="nofollow" target="_blank">read</a> (uint8_t *buffer, int length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=SERIAL_EVENT_RX_COMPLETE, unsigned char char_match=SERIAL_RESERVED_CHAR_MATCH)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#aaf1186a7b82f5ec7877998290ff633ba" rel="nofollow" target="_blank">read</a> (uint16_t *buffer, int length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=SERIAL_EVENT_RX_COMPLETE, unsigned char char_match=SERIAL_RESERVED_CHAR_MATCH)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a9d2ae4b1fa5e93967fe83f11b4a85d05" rel="nofollow" target="_blank">abort_read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ad33302d0596e9b038aea6cb24e4e6b90" rel="nofollow" target="_blank">set_dma_usage_tx</a> (DMAUsage usage)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#abd69f422b33f7d18890dd1b612cd9b6d" rel="nofollow" target="_blank">set_dma_usage_rx</a> (DMAUsage usage)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html" rel="nofollow" target="_blank">mbed::Stream</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a0c939bf392b43fffd3b10177d6c1c7c4" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Stream</strong> (const char *name=NULL)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a56261e44e0d63848a4c93d38b2a6b7eb" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>putc</strong> (int c)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a70696119b546bab923221ce0d6ce4853" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>puts</strong> (const char *s)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a4256675de5e29631f1df8df7b0f001aa" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getc</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a2474b8dcc0546e3542a55d05ec8287fa" target="_blank"></a> char *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gets</strong> (char *s, int <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#ac1951de2e295d6070ffb35e830ef76e2" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;"><a id="af224c8e8993babf3278f30f5c5855636" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>printf</strong> (const char *format,...)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a64ee7c172ce2fdf4b99f7033681a01d6" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>scanf</strong> (const char *format,...)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a246692ba57d2ad023d8b6d2d9aa2b95d" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vprintf</strong> (const char *format, std::va_list args)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a4d1dc735f75f2b313a63c661693ab7bf" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vscanf</strong> (const char *format, std::va_list args)</td>
		</tr><tr><td style="vertical-align:top;"><a id="ac18fba9194addd424fe10b7f7cb6376d" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>operator std::FILE *</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_like.html" rel="nofollow" target="_blank">mbed::FileLike</a></td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_like.html#ad1af81bce8ba2d3a0dd6676d681af803" rel="nofollow" target="_blank">FileLike</a> (const char *name=NULL)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html" rel="nofollow" target="_blank">mbed::FileHandle</a></td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#ae33a9f2786253c373b9f617a3c700f07" rel="nofollow" target="_blank">lseek</a> (off_t offset, int whence)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a073c6f4c835d5cf48761f70951e2e51a" rel="nofollow" target="_blank">fsync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a991dddade770154bd53b613b15a251a9" rel="nofollow" target="_blank">flen</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a2127b1e14da42503e33b5a2b1305ab3a" rel="nofollow" target="_blank">set_blocking</a> (bool blocking)</td>
		</tr><tr><td style="vertical-align:top;">virtual bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#ab734060daf29e9aa178314e46eb21248" rel="nofollow" target="_blank">is_blocking</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual short&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a17f420e53823fb7887863a7c8729b014" rel="nofollow" target="_blank">poll</a> (short events) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#aac0c0583caca23a213db95f4e5b4ef89" rel="nofollow" target="_blank">writable</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a19273f41c7b1f970bb1cf3094b59c1c3" rel="nofollow" target="_blank">readable</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html#a800296061a5fa5d360cbbc60853247b4" rel="nofollow" target="_blank">sigio</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">mbed::FileBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a8b19f5dfe489eaa641c32a5096c71af1" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>FileBase</strong> (const char *name, PathType t)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a22078733b15abf28045948d24555ceaf" target="_blank"></a> const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getName</strong> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a59dd77df265c99a2fa0f7c209d0dba18" target="_blank"></a> PathType&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getPathType</strong> (void)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="ae5fe437f829ac9835dc00e704ee0b6cb" target="_blank"></a> virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_getc</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="ab1c7b5a968277baa4fc2802fbe042d00" target="_blank"></a> virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_putc</strong> (int c)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.html#a22f00ffda8ebf77ea9e95a03b40e3183" rel="nofollow" target="_blank">lock</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial.html#ac0d54237014b40a53e7648f7baa2530f" rel="nofollow" target="_blank">unlock</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">mbed::SerialBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a15a4c9833e2333c1f22d824f07b53564" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>start_read</strong> (void *buffer, int buffer_size, char buffer_width, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event, unsigned char char_match)</td>
		</tr><tr><td style="vertical-align:top;"><a id="ac181f70e2b381fc1c54c15c856bf5e25" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>start_write</strong> (const void *buffer, int buffer_size, char buffer_width, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a1d09a80aefa8f9f7d0a3dcc40ffe1973" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>interrupt_handler_asynch</strong> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a9377f0b939cc55b7011e3e41d8094611" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>SerialBase</strong> (PinName tx, PinName rx, int <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ac777186012bec315ebdf8320d5c4d917" rel="nofollow" target="_blank">baud</a>)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a548470925a8c3da77ed28f4834599ed0" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_base_getc</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a4aba8d8a8cb289756469cc30ec401b7c" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_base_putc</strong> (int c)</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html" rel="nofollow" target="_blank">mbed::Stream</a></td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#aab4a2eca58c3ffe1a075d40a840f736d" rel="nofollow" target="_blank">close</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual ssize_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#a83986e912feb3942dac3341330a95c02" rel="nofollow" target="_blank">write</a> (const void *buffer, size_t length)</td>
		</tr><tr><td style="vertical-align:top;">virtual ssize_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#ad44a91927bfc69701594c08502a00631" rel="nofollow" target="_blank">read</a> (void *buffer, size_t length)</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#aad806ac64b50ce0fa560733b8c6f2cff" rel="nofollow" target="_blank">seek</a> (off_t offset, int whence)</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#a56bb16ea3ddb2995c09a852eb107294f" rel="nofollow" target="_blank">tell</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#a0b5be4ddd764922daff983ef77ce3e29" rel="nofollow" target="_blank">rewind</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#ad179e40afb850c4fb10d8012bee83cd9" rel="nofollow" target="_blank">isatty</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#aa44bbe04f822e9f8ed12999a228020f2" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html#ac1951de2e295d6070ffb35e830ef76e2" rel="nofollow" target="_blank">size</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a0c1828da4e38552c82f9df04ca09c72f" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">mbed::SerialBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a74451fb978ebf81fb36ea301cb62766e" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_c_thunk.html" rel="nofollow" target="_blank">CThunk</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">SerialBase</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_thunk_irq</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="ad5849b7f29af7e91a9577bc6903bfd98" target="_blank"></a> DMAUsage&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_tx_usage</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a904dff82d36b11a91834d5f12abe8619" target="_blank"></a> DMAUsage&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_rx_usage</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="af8a1a9c5394024621f6d869b241af945" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_tx_callback</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a5964ea4c4250bcf773609025aea1319c" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_rx_callback</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a0177e785bc9f5ef3d420c092ced8059b" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structserial__t.html" rel="nofollow" target="_blank">serial_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_serial</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a36a3e665ebaf2f62127c65dc3d04caef" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq</strong> [IrqCnt]</td>
		</tr><tr><td style="vertical-align:top;"><a id="a0f470276e7157380c18701cddb7647d6" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_baud</strong></td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_stream.html" rel="nofollow" target="_blank">mbed::Stream</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="ae4ee478b704c5cc1e55fed9b17398875" target="_blank"></a> std::FILE *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_file</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;继承自的公共类型 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">mbed::SerialBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a933693c1992a71ea801326113c6c1175" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Parity</strong> {<br>
			&nbsp;&nbsp;<strong>None</strong> = 0, <strong>Odd</strong>, <strong>Even</strong>, <strong>Forced1</strong>,<br>
			&nbsp;&nbsp;<strong>Forced0</strong><br>
			}</td>
		</tr><tr><td style="vertical-align:top;"><a id="af3e45bd7fcc34d768cbace2fadf1c97e" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>IrqType</strong> { <strong>RxIrq</strong> = 0, <strong>TxIrq</strong>, <strong>IrqCnt</strong> }</td>
		</tr><tr><td style="vertical-align:top;"><a id="aee1d07a2cdac31486ffe45e6e6077cc8" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Flow</strong> { <strong>Disabled</strong> = 0, <strong>RTS</strong>, <strong>CTS</strong>, <strong>RTSCTS</strong> }</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html" rel="nofollow" target="_blank">mbed::SerialBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="af3d381aafb23f27e31afd64a1900451c" target="_blank"></a> static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq_handler</strong> (uint32_t id, SerialIrq irq_type)</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">mbed::FileBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a227997f93c4171392e6aa3868c705a36" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">FileBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lookup</strong> (const char *name, unsigned int len)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a7fb679a04a646da30923820a7c505a19" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">FileBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get</strong> (int n)</td>
		</tr></tbody></table>

**注意**: 在 Windows 计算机上，您需要安装 USB 串行驱动程序。请参阅 Windows 串行配置。

串行通道有许多可配置的参数：

+ 波特率 - 有许多标准波特率，从每秒几百比特到每秒兆比特。Mbed 微控制器上串行连接的默认设置为 9600 波特。
+ 数据长度 - 传输的数据可以是 7 位或 8 位长。Mbed 微控制器上串行连接的默认设置是 8 位。
+ 奇偶校验 - 您可以添加可选的奇偶校验位。奇偶校验位将自动设置为使数据中的 1 的数量为奇数或偶数。奇偶校验设置为奇数，偶数或无。Arm Mbed 微控制器上串行连接的默认设置为 None。
+ 停止位 - 发送数据和奇偶校验位后，插入一个或两个停止位以 “frame” 数据。Mbed 微控制器上串行连接的默认设置是一个停止位。

Mbed 微控制器的默认设置描述为 9600 - 8 - N - 1，这是串行端口设置的常用符号。

## Serial hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/Serial_HelloWorld/file/e540d7769e69/main.cpp)  
```
/* mbed Example Program
 * Copyright (c) 2006-2014 ARM Limited
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
 
Serial pc(USBTX, USBRX); // tx, rx
 
int main() {
    pc.printf("Hello World!\n\r");
    while(1) {
        pc.putc(pc.getc() + 1); // echo input back to terminal
    }
}
```
## Serial 示例
### 示例一

以波特率 19200 向设备写入消息。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/Serial_ex_1/file/7376f17bb36e/main.cpp)        
```
#include "mbed.h"
 
Serial device(USBTX, USBRX);  // tx, rx
 
int main() {
    device.baud(19200);
    device.printf("Hello World\n");
}
```
### 示例二

在 PC 和外部 UART 之间提供串行传递。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/Serial_ex_2/file/8d318218bac1/main.cpp)        
```
#include "mbed.h"
//K64F
Serial pc(USBTX, USBRX); // tx, rx
Serial device(MBED_CONF_APP_UART1_TX, MBED_CONF_APP_UART1_RX);  // tx, rx
 
int main() {
    while(1) {
        if(pc.readable()) {
            device.putc(pc.getc());
        }
        if(device.readable()) {
            pc.putc(device.getc());
        }
    }
}
``` 
