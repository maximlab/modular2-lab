## DigitalIn
使用 DigitalIn 接口读取数字输入引脚的值。逻辑电平为 1 或 0。

您可以使用任何编号的 Arm Mbed 引脚可以用作 DigitalIn。

## DigitalIn 类参考
API 摘要

[mbed::DigitalIn 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#a6593a15bcecfd3666c49bba83c81ee9b" rel="nofollow" target="_blank">DigitalIn</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#a4f07c90ffec20a9724ef42a61f7d21eb" rel="nofollow" target="_blank">DigitalIn</a> (PinName pin, PinMode <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#a9f3e23f670999a3f0ecb5ad959d1667a" rel="nofollow" target="_blank">mode</a>)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#aa19e2bc687842e7a1414ec5599f4f0e9" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#a9f3e23f670999a3f0ecb5ad959d1667a" rel="nofollow" target="_blank">mode</a> (PinMode pull)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#a0d765cc5944adfd9544cfb881d3d25e2" rel="nofollow" target="_blank">is_connected</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_digital_in.html#add1742ff230f5a6ba35f26056d11b4f6" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a6cbb51f8b90fc874a7f720f8e5c70e9e" target="_blank"></a> gpio_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gpio</strong></td>
		</tr></tbody></table>

## DigitalIn hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/DigitalIn_HelloWorld/file/954ac88dda04/main.cpp)                                                                                            
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
 
DigitalIn  mypin(SW2); // change this to the button on your board
DigitalOut myled(LED1);
 
int main()
{
    // check mypin object is initialized and connected to a pin
    if(mypin.is_connected()) {
        printf("mypin is connected and initialized! \n\r");
    }
    
    // Optional: set mode as PullUp/PullDown/PullNone/OpenDrain
    mypin.mode(PullNone); 
    
    // press the button and see the console / led change
    while(1) {
        printf("mypin has value : %d \n\r", mypin.read());
        myled = mypin; // toggle led based on value of button
        wait(0.25);
    }
}
``` 
## DigitalIn 示例
要处理中断，请参阅 [InterruptIn](https://os.mbed.com/docs/v5.9/reference/interruptin.html)。

逻辑函数的示例 - 布尔逻辑 NOT，AND，OR，XOR：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/DigitalIn_ex_1/file/10c4d3aa026e/main.cpp)     
```
#include "mbed.h"
 
DigitalIn a(D0);
DigitalIn b(D1);
DigitalOut z_not(LED1);
DigitalOut z_and(LED2);
DigitalOut z_or(LED3);
DigitalOut z_xor(LED4);
 
int main() {
    while(1) {
        z_not = !a;
        z_and = a && b;
        z_or = a || b;
        z_xor = a ^ b;
    }
}
```