## PortOut
使用 PortOut 接口将基础 GPIO 端口写为一个值。这比 BusOut 快得多，因为您可以一次编写一个端口，但由于受到底层 GPIO 端口的端口和位布局的限制，它的灵活性要低得多。

可以提供掩码，因此只使用端口的某些位，允许其他位用于其他接口。

## PortOut 类参考
[mbed::PortOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#a710b211ff80a11d6b69a7273cbb4d42c" rel="nofollow" target="_blank">PortOut</a> (PortName port, int mask=0xFFFFFFFF)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#a5d4d09e3103742a43a7c724beb870ec3" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#a7614a8f1a8e4e9acadd148fac9f40819" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html" rel="nofollow" target="_blank">PortOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#a3a4a7954a17edda68f2177d4f20df723" rel="nofollow" target="_blank">operator=</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html" rel="nofollow" target="_blank">PortOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#acd9e83d03ff0ceafcbd0b297cfbb973c" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html" rel="nofollow" target="_blank">PortOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_out.html#af0edd18487a4503f3f73d0328bf10712" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>

## PortOut hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/PortOut_HelloWorld/file/e4e6fab14d21/main.cpp) 
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
 
 
// Toggle all four LEDs
 
#include "mbed.h"
 
// LED1 = P1.18  LED2 = P1.20  LED3 = P1.21  LED4 = P1.23
#define LED_MASK 0x00B40000
 
PortOut ledport(Port1, LED_MASK);
 
int main() {
    while(1) {
        ledport = LED_MASK;
        wait(1);
        ledport = 0;
        wait(1);
    }
}
```
相关内容
[BusOut](https://os.mbed.com/docs/v5.9/reference/busout.html) API 参考。