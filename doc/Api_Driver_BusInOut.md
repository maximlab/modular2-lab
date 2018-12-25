## BusInOut
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.png">

BusInOut 类层次结构</div>

使用 BusInOut 接口作为双向总线，支持最多 16 个 DigitalInOut 引脚，您可以读取和写入一个值。

您可以将任何编号的 Arm Mbed 引脚用作 DigitalInOut。

### 提示:

构造函数中引脚的顺序是字节顺序中引脚的相反顺序。如果你有 BusInOut（a，b，c，d，e，f，g，h），那么字节中的位的顺序是 hgfedcba，其中 a 位为 0，b 为位 1，c 为位 2，依此类推。

## BusInOut 类参考
[mbed::BusInOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#aeb307d492d797e5a10919a92f1da5e31" rel="nofollow" target="_blank">BusInOut</a> (PinName p0, PinName p1=NC, PinName p2=NC, PinName p3=NC, PinName p4=NC, PinName p5=NC, PinName p6=NC, PinName p7=NC, PinName p8=NC, PinName p9=NC, PinName p10=NC, PinName p11=NC, PinName p12=NC, PinName p13=NC, PinName p14=NC, PinName p15=NC)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#ad8e4b46a0066126a575c054e22aa4b42" rel="nofollow" target="_blank">BusInOut</a> (PinName pins[16])</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#a36473cded1109d3960d51c6f8e1ee123" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#a98154c0add9d2e8bec0e27ca42249b31" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#aea68cf05f895ef5d7a6c4a963fe695d4" rel="nofollow" target="_blank">output</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#a2f5cdeb39d9f1b2e71281f48ead9090f" rel="nofollow" target="_blank">input</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#ae16e26bbb20523c2ae428db3fca5bb15" rel="nofollow" target="_blank">mode</a> (PinMode pull)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#a45354e1e41ecf96b5fb5377ea4fcad72" rel="nofollow" target="_blank">mask</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html" rel="nofollow" target="_blank">BusInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#ac0614da22e30b548c0ab863ade51428b" rel="nofollow" target="_blank">operator=</a> (int v)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa0a4bd4bb035ba4b6ba3772112ca36fc" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html" rel="nofollow" target="_blank">BusInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>operator=</strong> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html" rel="nofollow" target="_blank">BusInOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html" rel="nofollow" target="_blank">DigitalInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#afde4f3bcc2012633195c641e7ebad936" rel="nofollow" target="_blank">operator[]</a> (int index)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html#a63844c4d74e7de4818fa07447c2ba7c2" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="acec107fb8d9edde6b8ac0b189f50f055" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html" rel="nofollow" target="_blank">DigitalInOut</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_pin</strong> [16]</td>
		</tr><tr><td style="vertical-align:top;"><a id="af4a2854a611341b55a9b62075092a53f" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_nc_mask</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7efb97d055fc81191e1ff3c6147c3a15" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## BusInOut Hello World!
[main.cpp](https://os.mbed.com/teams/mbed_example/code/BusInOut_HelloWorld/file/68629c6c4970/main.cpp)                                                                                                      
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
 
BusInOut pins(D0, D1, D2);
 
int main() {
    while(1) {
        pins.output();
        pins = 0x3;
        wait(1);
        pins.input();
        wait(1);
        if(pins == 0x6) {
            printf("Hello!\n");
        }
    }
}
```