## BusIn
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.png">

BusIn 类层次结构</div>

使用 BusIn API，您可以创建许多可以作为一个值读取的 DigitalIn 引脚。此抽象对于一次检查多个输入非常有用。您可以使用此 API 更快地编写更清晰的代码。

您可以将任何编号的 Arm Mbed 引脚用作 BusIn 中的 DigitalIn。

### 提示:

+ 总线中最多可以有 16 个引脚。
+ 构造函数中引脚的顺序是字节顺序中引脚的相反顺序。如果你有 BusIn（a，b，c，d，e，f，g，h）那么字节中的位的顺序是 hgfedcba，其中 a 位为 0，b 为位 1，c 为位 2，依此类推。

## BusIn 类参考
[mbed::BusIn 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#a60e8a1d93b93bb565d7f6fafacdf6a4b" rel="nofollow" target="_blank">BusIn</a> (PinName p0, PinName p1=NC, PinName p2=NC, PinName p3=NC, PinName p4=NC, PinName p5=NC, PinName p6=NC, PinName p7=NC, PinName p8=NC, PinName p9=NC, PinName p10=NC, PinName p11=NC, PinName p12=NC, PinName p13=NC, PinName p14=NC, PinName p15=NC)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#ae48033f85c46aa99f9693a0b890e65b8" rel="nofollow" target="_blank">BusIn</a> (PinName pins[16])</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#aad43475895a43bca659aef8a81dc4478" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#a93eed47467fec29854399cb7606a123b" rel="nofollow" target="_blank">mode</a> (PinMode pull)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#a22dfbea3293e2acda246d88d3545f346" rel="nofollow" target="_blank">mask</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#adb47444fdd5d8928923b39edaa247963" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html" rel="nofollow" target="_blank">DigitalIn</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in.html#a1fb6e035adfb8e07a3ddfe41f100610d" rel="nofollow" target="_blank">operator[]</a> (int index)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a44b9ec611a79d62de2be00c04ee034a1" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html" rel="nofollow" target="_blank">DigitalIn</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_pin</strong> [16]</td>
		</tr><tr><td style="vertical-align:top;"><a id="a3ccecbfabfbc7bcf74034264be551c3e" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_nc_mask</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2b6ce0a5462a678147235099f0439cd9" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## BusIn Hello World!
[main.cpp](https://os.mbed.com/teams/mbed_example/code/BusIn_HelloWorld/file/2ec7138ea637/main.cpp)   
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
 
BusIn nibble(D0, D1, D2, D3); // Change these pins to buttons on your board.
 
int main() {
    
    // Optional: set mode as PullUp/PullDown/PullNone/OpenDrain
    nibble.mode(PullNone); 
    
    while(1) {
        // check bits set in nibble
        switch(nibble & nibble.mask()) { // read the bus and mask out bits not being used
            case 0x0: printf("0b0000, D3,D2,D1,D0 are low  \n\r");break;
            case 0x1: printf("0b0001,          D0  is high \n\r");break;
            case 0x2: printf("0b0010,       D1     is high \n\r");break; 
            case 0x3: printf("0b0011,       D1,D0 are high \n\r");break;
            case 0x4: printf("0b0100,    D2        is high \n\r");break;
            case 0x5: printf("0b0101,    D2,  ,D0 are high \n\r");break;
            case 0x6: printf("0b0110,    D2,D1    are high \n\r");break;
            case 0x7: printf("0b0111,    D2,D1,D0 are high \n\r");break;
            case 0x8: printf("0b1000, D3           is high \n\r");break; 
            // ...
            case 0xF: printf("0b1111, D3,D2,D1,D0 are high \n\r");break;
        }
        wait(1);
    }
}
```