## DigitalInOut
使用 DigitalInOut 接口作为双向数字引脚：

设置为 input() 时，读取数字引脚的值。
设置为 output() 时写入值。
您可以将任何编号的 Arm Mbed 引脚用作 DigitalInOut。

**注意**: 某些平台在输入和输出之间切换时会有时间延迟。

## DigitalInOut 类参考
[mbed::DigitalInOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a45aeb16f525f8fd23b468b761d44034a" rel="nofollow" target="_blank">DigitalInOut</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#acdebfaf292d2c361db6a3040e4d34c8c" rel="nofollow" target="_blank">DigitalInOut</a> (PinName pin, PinDirection direction, PinMode <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#ac055602d6e364974d9096d6a9cdeaa45" rel="nofollow" target="_blank">mode</a>, int value)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a2407c36ddf7aeca0a3d941d13001431b" rel="nofollow" target="_blank">write</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a19cf94937f2ab85012fc5418e5808c44" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#acc847afdb691a4628ac23612d7944e6b" rel="nofollow" target="_blank">output</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#acc7775ff8fe2e40cc2882ce2a2e2e3d0" rel="nofollow" target="_blank">input</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#ac055602d6e364974d9096d6a9cdeaa45" rel="nofollow" target="_blank">mode</a> (PinMode pull)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a185f22a87707167a3841e1d62b6e2736" rel="nofollow" target="_blank">is_connected</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html" rel="nofollow" target="_blank">DigitalInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a055dae2e002e9a95a06462746fb1685f" rel="nofollow" target="_blank">operator=</a> (int value)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html" rel="nofollow" target="_blank">DigitalInOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#a6d1174bf281a925f52a63157819425d9" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html" rel="nofollow" target="_blank">DigitalInOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in_out.html#ace8466be1d1a836a1ecb1dd1621af7a2" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="ad12461401f91ed957b17d0ec363915c0" target="_blank"></a> gpio_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gpio</strong></td>
		</tr></tbody></table>

## DigitalInOut hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/DigitalInOut_HelloWorld/file/185e0d3e7212/main.cpp)      
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
 
DigitalInOut mypin(LED1);
 
int main()
{
    // check that mypin object is initialized and connected to a pin
    if(mypin.is_connected()) {
        printf("mypin is initialized and connected!\n\r");
    }
 
    // Optional: set mode as PullUp/PullDown/PullNone/OpenDrain
    mypin.mode(PullNone);
 
    while(1) {
        // write to pin as output
        mypin.output();
        mypin = !mypin; // toggle output
        wait(0.5);
 
        // read from pin as input
        mypin.input();
        printf("mypin.read() = %d \n\r",mypin.read());
        wait(0.5);
    }
}
```