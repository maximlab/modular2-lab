## PortInOut
使用 PortInOut 接口将基础 GPIO 端口读写为一个值。这比 BusInOut 快得多，因为您可以一次编写一个端口，但由于受到底层 GPIO 端口的端口和位布局的限制，它的灵活性要低得多。

可以提供掩码，因此您只使用端口的某些部分，允许其他位用于其他接口。

## PortInOut 类参考
[mbed::PortInOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#a4040f1bb4fbd30dfc9b29f2fe98e3972" rel="nofollow" target="_blank">PortInOut</a> (PortName port, int mask=0xFFFFFFFF)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#aeb5a38523ce618ab30797a176d33267a" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#a74d30470fe2a9cf91b32613811925d63" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#aa088bafb97bf4ad2c8b24155cb631fa2" rel="nofollow" target="_blank">output</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#ae079f031a30f98ba519d05174f765df9" rel="nofollow" target="_blank">input</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#a1dbdd640ad69d27ba96ef37c42ba7ee0" rel="nofollow" target="_blank">mode</a> (PinMode mode)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html" rel="nofollow" target="_blank">PortInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#ab7dcfd8e53b049b3859b2cb7f9657b49" rel="nofollow" target="_blank">operator=</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html" rel="nofollow" target="_blank">PortInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#afd85907d5dcafdc3731fcd50f6ca3640" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html" rel="nofollow" target="_blank">PortInOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in_out.html#ad40603b4ee91ada3936011347d9d59a5" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>

## PortInOut hello, world
[main.cpp](https://os.mbed.com/users/mbed_official/code/PortInOut_HelloWorld/file/018ca8a43b33/main.cpp)        
```
// Toggle all four LEDs
 
#include "mbed.h"
 
// LED1 = P1.18  LED2 = P1.20  LED3 = P1.21  LED4 = P1.23
#define LED_MASK 0x00B40000
 
PortInOut ledport(Port1, LED_MASK);
 
int main() {
    int v = ledport;
    ledport.output();
    while(1) {
        ledport = LED_MASK;
        wait(0.5);
        ledport = 0;
        wait(1);
    }
}
```
相关内容

[BusInOut](https://os.mbed.com/docs/v5.9/reference/businout.html) API 参考。