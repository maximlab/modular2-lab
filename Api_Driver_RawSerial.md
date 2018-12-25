## RawSerial
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.png">

RawSerial 类层次结构</div>                                                            

RawSerial 类提供 UART 功能，而不像 Serial 类那样使用 Stream 的打印和扫描功能。RawSerial 不会重新定位标准库打印和扫描功能。相反，RawSerial 重新实现打印和扫描功能，以使用每个目标的底层串行通信功能。有关目标串行支持，请参阅移植指南。这使得 RawSerial 适合用于 RTOS 的中断处理程序。

串行通道在构造函数中具有以下可配置参数：

+ Tx 和 Rx 引脚 - 物理串行发送和接收引脚。您可以将 Tx 或 Tx 引脚指定为未连接（NC）以进行 Simplex 通信，或指定两者以获得全双工。
+ 波特率 - 此设置是可选的构造函数参数。标准波特率范围从每秒几百位到每秒兆位。Mbed 微控制器上串行连接的默认设置为 9600 波特。也可以在运行时配置此设置。

可以在 RawSerial 对象的运行时配置以下参数。您可以在类引用中查看有关可配置设置和函数的更多信息。

+ 波特率 - 标准波特率范围从每秒几百位到每秒兆位。Mbed 微控制器上串行连接的默认设置为 9600 波特。
+ 数据长度 - 传输的数据可以是 7 位或 8 位长。Mbed 微控制器上串行连接的默认设置为 8 位。
+ 奇偶校验 - 您可以添加可选的奇偶校验位。对象自动设置奇偶校验位，使数据中的 1 的数量为奇数或偶数。奇偶校验设置为奇数，偶数或无。Arm Mbed 微控制器上串行连接的默认设置为 None。
+ 停止位 - 在传输数据和奇偶校验位之后，RawSerial 对象插入一个或两个停止位以 “frame” 数据。Mbed 微控制器上串行连接的默认设置是一个停止位。

9600 - 8 - N - 1 是串行端口设置的常用符号，描述了 Mbed 微控制器的默认设置。

## RawSerial 类参考
[mbed::RawSerial 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#ab501a0ddbc6c8dc41edcd0e6b69812cb" rel="nofollow" target="_blank">RawSerial</a> (PinName tx, PinName rx, int <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#ac777186012bec315ebdf8320d5c4d917" rel="nofollow" target="_blank">baud</a>=MBED_CONF_PLATFORM_DEFAULT_SERIAL_BAUD_RATE)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#a8e6add5588f0ccdb9fc7722e608ff27c" rel="nofollow" target="_blank">putc</a> (int c)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#a944d91636369cf0773d7b61b268a85f2" rel="nofollow" target="_blank">getc</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#af9fd487b61b30ebfbf05cede80af0807" rel="nofollow" target="_blank">puts</a> (const char *str)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5fbeb8149c7fc2e4f45e8869d09797cb" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>printf</strong> (const char *<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_serial_base.html#a768f1e9fd9e14c787f693745fa2538a4" rel="nofollow" target="_blank">format</a>,...)</td>
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
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#a2898055a53d4208d39044f8afa995289" rel="nofollow" target="_blank">lock</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_raw_serial.html#af73408d1441960d63dacbc1140d91af4" rel="nofollow" target="_blank">unlock</a> (void)</td>
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
		</tr></tbody></table>

**注意**: 在 Windows 计算机上，您需要安装 USB 串行驱动程序。请参阅 Windows 串行设置。

## RawSerial hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/RawSerial_HelloWorld/file/112a40a5991a/main.cpp)         
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
 
RawSerial pc(USBTX, USBRX); // tx, rx
 
int main() {
    pc.printf("Hello World!\n\r");
    while(1) {
        pc.putc(pc.getc()); // echo input back to terminal
    }
}
```
## RawSerial 示例
### 示例一

以波特率 19200 向设备写入消息。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/RawSerial_ex_1/file/6a0d9cb21969/main.cpp)     
```
#include "mbed.h"
 
RawSerial device(USBTX, USBRX);  // tx, rx
 
int main() {
    device.baud(19200);
    device.printf("Hello World\n");
}
```
### 示例二

在生成串行中断期间附加要调用的函数。此功能默认为 RX 引脚上的中断：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/RawSerial_ex_2/file/3ad999bfc3c4/main.cpp)     
```
#include "mbed.h"
 
DigitalOut led1(LED1);
DigitalOut led2(LED2);
 
RawSerial pc(USBTX, USBRX);
 
void callback_ex() {
    // Note: you need to actually read from the serial to clear the RX interrupt
    pc.putc(pc.getc());
    led2 = !led2;
}
 
int main() {
    pc.attach(&callback_ex);
 
    while (1) {
        led1 = !led1;
        wait(0.5);
    }
}
``` 
## Mbed OS 示例

RawSerial 的常见用例是 IRQ 重 UART 操作，例如 ESP8266 驱动程序中的 ATParser。该驱动器在用户提供的引脚上使用 UART 与片外 ESP8266 模块通信。