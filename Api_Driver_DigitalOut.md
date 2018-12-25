## DigitalOut
使用 DigitalOut 接口通过将引脚设置为逻辑电平 0 或 1 来配置和控制数字输出引脚。

DigitalOut 类参考
[mbed::DigitalOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#aad0eaa96c3fad0b2e31c167d616fe3c2" rel="nofollow" target="_blank">DigitalOut</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#a6068274615ee97f1ff3a3ceb701faa26" rel="nofollow" target="_blank">DigitalOut</a> (PinName pin, int value)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#a780c53a27d6ef36e8f57dc796d4c117c" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#aee5b6dba79cb58aa87a18b3dc38621bd" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#ae0166d6aa26e5befe5a51058a132503c" rel="nofollow" target="_blank">is_connected</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html" rel="nofollow" target="_blank">DigitalOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#a99e9d68df5fb296fbaf1c682aae3ce41" rel="nofollow" target="_blank">operator=</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html" rel="nofollow" target="_blank">DigitalOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#ad3a4dbb96e5cef32aefdf2e98ea7baf2" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html" rel="nofollow" target="_blank">DigitalOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_out.html#afa966c7a9c8a66c499839c7be55d2d9b" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a3f5716320aba4d372a74107f95a97c81" target="_blank"></a> gpio_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gpio</strong></td>
		</tr></tbody></table>

## DigitalOut hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/DigitalOut_HelloWorld/file/928e709317d9/main.cpp)        
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
 
DigitalOut myled(LED1);
 
int main()
{
    // check that myled object is initialized and connected to a pin
    if(myled.is_connected()) {
        printf("myled is initialized and connected!\n\r");
    }
 
    // Blink LED
    while(1) {
        myled = 1;          // set LED1 pin to high
        printf("myled = %d \n\r", (uint8_t)myled );
        wait(0.5);
 
        myled.write(0);     // set LED1 pin to low
        printf("myled = %d \n\r",myled.read() );
        wait(0.5);
    }
}
```