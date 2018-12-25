## SPI
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.png">

SPI 类层次结构</div>                                           
                                                                      
SPI 接口提供串行外设接口主机。

您可以使用此接口与 SPI 从设备进行通信，例如 FLASH 存储器，LCD 屏幕和其他模块或集成电路。

## 接口

SPI 接口的默认设置为 1 MHz，8 位，模式 0。

您可以使用 SPI 接口从 SPI 端口写入数据字，返回从 SPI 从器件接收的数据。您还可以配置 SPI 时钟频率和格式。格式设置为数据字长度为 8 到 16 位，模式如下表所示：

|模式	|极性	|相位|
|:-:|:-:|:-:|
|0	|0	|0|
|1	|0	|1|
|2	|1	|0|
|3	|1	|1|

SPI 主控制器生成一个时钟，以同步驱动串行位流从器件。从机返回一个比特流，也与时钟同步。要与通过同一 SPI 外设连接的多个从器件通信，必须使用多个 SPI 对象，每个从器件对应一个，但使用不同的从器件选择（SSEL）和与每个从器件对应的配置对它们进行实例化。请注意，当应用程序代码调用 SPI 对象上的接口时，SPI 对象会自动使用当前对象的配置来配置 SPI 外设。

## SPI 类参考
[mbed::SPI 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#aa53e0d99c74a74ad33cccca327402f2e" rel="nofollow" target="_blank">SPI</a> (PinName mosi, PinName miso, PinName sclk, PinName ssel=NC)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#ac4df1e7b405a5227b46a7a907f1e8723" rel="nofollow" target="_blank">format</a> (int bits, int mode=0)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a3ed90979de66970c5d9e30fa6e180222" rel="nofollow" target="_blank">frequency</a> (int hz=1000000)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#acad381099c2b75b4f84087de352e3085" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#abb55a78da9be054354997065128b52e0" rel="nofollow" target="_blank">write</a> (const char *tx_buffer, int tx_length, char *rx_buffer, int rx_length)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#ae11f92d0417cea03c95a94f1b893dfd4" rel="nofollow" target="_blank">lock</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#aa5d469ff381aab3fb7d87c310b575cb8" rel="nofollow" target="_blank">unlock</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a625de73341938ff8794d4c24cbce17ff" rel="nofollow" target="_blank">set_default_write_value</a> (char data)</td>
		</tr><tr><td colspan="2">template&lt;typename Type &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a2fc48089d7aacb2b1c3903b2f22feb03" rel="nofollow" target="_blank">transfer</a> (const Type *tx_buffer, int tx_length, Type *rx_buffer, int rx_length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=SPI_EVENT_COMPLETE)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a1df880bccc568017f2d199e3fd9a9814" rel="nofollow" target="_blank">abort_transfer</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a48c6af9742e1548992569f8c9fb213bc" rel="nofollow" target="_blank">clear_transfer_buffer</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a9a3474575b392954261ad3a17dee215d" rel="nofollow" target="_blank">abort_all_transfers</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#aaa666b584707a50aefaa041c76e65b9a" rel="nofollow" target="_blank">set_dma_usage</a> (DMAUsage usage)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a8837f4f0976c871d327c6ebe700fac47" rel="nofollow" target="_blank">irq_handler_asynch</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a07bd996765db9f0a994dc7147efaf9b3" rel="nofollow" target="_blank">transfer</a> (const void *tx_buffer, int tx_length, void *rx_buffer, int rx_length, unsigned char bit_width, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a2641e4038d25e84ea07f5e396c5d778b" rel="nofollow" target="_blank">queue_transfer</a> (const void *tx_buffer, int tx_length, void *rx_buffer, int rx_length, unsigned char bit_width, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html#a7a515b4579e4fdd5f8c0894cb1f87790" rel="nofollow" target="_blank">start_transfer</a> (const void *tx_buffer, int tx_length, void *rx_buffer, int rx_length, unsigned char bit_width, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aba0d005543c70a430b3f22302591e4e4" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>aquire</strong> (void)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a2434599649ea60278d2e9f927b5c2d1b" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structspi__t.html" rel="nofollow" target="_blank">spi_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_spi</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2bbd260513eb876b352bd77717d38e3b" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_c_thunk.html" rel="nofollow" target="_blank">CThunk</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html" rel="nofollow" target="_blank">SPI</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a65ce4e1a5178c2438d845507d0c290ef" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_callback</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a10adb425506e22ecb4f1c3a183add333" target="_blank"></a> DMAUsage&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_usage</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="ab14ec7833493505940fa68ce6d41ee9b" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_deep_sleep_locked</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a6261c41d9453ac2fd398921a91d46634" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bits</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a33fc65e733165744914c769710741237" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mode</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a8070b49adecf4ab8bcd9f6020eac5f19" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_hz</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a8720065da3d62bd67e716ad1c967a484" target="_blank"></a> char&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_write_fill</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="aeb41abd46d5b88dc954402ee9b508aee" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i.html" rel="nofollow" target="_blank">SPI</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_owner</strong> = NULL</td>
		</tr><tr><td style="vertical-align:top;"><a id="a35618a0cab551f9c69b8f93f6abd79ce" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_singleton_ptr.html" rel="nofollow" target="_blank">SingletonPtr</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## SPI hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/SPI_HelloWorld/file/dd9e7d208cbd/main.cpp)     
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
 
SPI spi(D11, D12, D13); // mosi, miso, sclk
DigitalOut cs(D0);
 
int main() {
    // Chip must be deselected
    cs = 1;
 
    // Setup the spi for 8 bit data, high steady state clock,
    // second edge capture, with a 1MHz clock rate
    spi.format(8,3);
    spi.frequency(1000000);
 
    // Select the device by seting chip select low
    cs = 0;
 
    // Send 0x8f, the command to read the WHOAMI register
    spi.write(0x8F);
 
    // Send a dummy byte to receive the contents of the WHOAMI register
    int whoami = spi.write(0x00);
    printf("WHOAMI register = 0x%X\n", whoami);
 
    // Deselect the device
    cs = 1;
}
```