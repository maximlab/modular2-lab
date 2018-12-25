## SPISlave
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.png">

SPISlave 类层次结构</div>                                           

使用 SPISlave 类与 SPI 主设备通信。

默认格式设置为 8 位，模式 0 和 1 MHz 的时钟频率。同步级别：不受保护。

## SPISlave 类参考
[mbed::SPISlave 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#aaa5f0e6e39441c96f3a23651978e4d0d" rel="nofollow" target="_blank">SPISlave</a> (PinName mosi, PinName miso, PinName sclk, PinName ssel)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#af70672da6e2c8012248a12180215f866" rel="nofollow" target="_blank">format</a> (int bits, int mode=0)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#ad34d991f4960c543bd75750d6c33fe6b" rel="nofollow" target="_blank">frequency</a> (int hz=1000000)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#a91bddd0100a37417ed0c00db9a4d7655" rel="nofollow" target="_blank">receive</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#a467374620ebabc35e5bbcc437734d1fa" rel="nofollow" target="_blank">read</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_s_p_i_slave.html#a32dad52b1130f442a14b6748369d5446" rel="nofollow" target="_blank">reply</a> (int value)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa2eaa0a56e4d23aad87285512f0c6c10" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structspi__t.html" rel="nofollow" target="_blank">spi_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_spi</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a1407116174464c2d5758e5d232fbb127" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bits</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a66ccdaf05c01d4f5ccb2a40d3b4e3f79" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mode</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a55fccf4e5a851f9d278037913575cfd6" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_hz</strong></td>
		</tr></tbody></table>

## SPISlave 示例
回复 SPI 主站作为 slave：
```
#include "mbed.h"
 
SPISlave device(p5, p6, p7, p8); // mosi, miso, sclk, ssel
 
int main() {
   device.reply(0x00);              // Prime SPI with first reply
   while(1) {
       if(device.receive()) {
           int v = device.read();   // Read byte from master
           v = (v + 1) % 0x100;     // Add one to it, modulo 256
           device.reply(v);         // Make this the next reply
       }
   }
}
```