## AnalogOut
使用 AnalogOut 接口将模拟输出引脚的输出电压设置为百分比或无符号短路。Mbed OS 提供单独的 API 以使用百分比或范围。  Mbed OS 支持最大分辨率 VCC/65536 V，但实际分辨率取决于硬件。

**注意**: 并非所有引脚都能够成为 AnalogOut，因此请检查电路板的 pinmap。

## AnalogOut 类参考
[mbed::AnalogOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#ae328c0ba454e0025ace9254121980593" rel="nofollow" target="_blank">AnalogOut</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#a0e521119147950eeb7a5a88e7da51784" rel="nofollow" target="_blank">write</a> (float value)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#ae229398abe666ee2d733ec002d754256" rel="nofollow" target="_blank">write_u16</a> (unsigned short value)</td>
		</tr><tr><td style="vertical-align:top;">float&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#a46cc272dc4b9db9f79f0a81445da7c39" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html" rel="nofollow" target="_blank">AnalogOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#aec07c15218777b62bbbd4b0d7e2bc4c7" rel="nofollow" target="_blank">operator=</a> (float percent)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html" rel="nofollow" target="_blank">AnalogOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#ae7e7ccd73c8abd10995c57a77b10b4c0" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html" rel="nofollow" target="_blank">AnalogOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_out.html#a059e43a3e1ed54b7f8582be0232a5dbc" rel="nofollow" target="_blank">operator float</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="ad9aefc05b96badd8fb15751fa967668d" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lock</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5b8b780f6a4f590e14657d7677007592" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>unlock</strong> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a767cd3412d940f1b45c4e949dd947c28" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#ga125c25ad6ab46870e3c0a3310cae2a2e" rel="nofollow" target="_blank">dac_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_dac</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a4814775e67688b73a33defbcfa2e00cf" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## AnalogOut hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/AnalogOut_HelloWorld/file/a32148e02ecf/main.cpp)         
```
/* mbed Example Program
 * Copyright (c) 2006-2015 ARM Limited
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
 
// Initialize a pins to perform analog and digital output fucntions
AnalogOut  aout(A5);
DigitalOut dout(LED1);
 
int main(void)
{
    while (1) {
        // change the voltage on the digital output pin by 0.1 * VCC
        //  and print what the measured voltage should be (assuming VCC = 3.3v)
        for (float i = 0.0f; i < 1.0f; i += 0.1f) {
            aout = i;
            printf("aout = %1.2f volts\n", aout.read() * 3.3f);
            // turn on the led if the voltage is greater than 0.5f * VCC
            dout = (aout > 0.5f) ? 1 : 0;
            wait(1.0f);
        }
    }
}
``` 
## AnalogOut 示例
创建一个正弦波。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/AnalogOut_ex_1/file/066510b55650/main.cpp)     
```
#include "mbed.h"
 
const double pi = 3.141592653589793238462;
const double amplitude = 0.5f;
const double offset = 65535/2;
 
// The sinewave is created on this pin
AnalogOut aout(A5);
 
int main()
{
    double rads = 0.0;
    uint16_t sample = 0;
    
    while(1) {
        // sinewave output
        for (int i = 0; i < 360; i++) {
            rads = (pi * i) / 180.0f;
            sample = (uint16_t)(amplitude * (offset * (cos(rads + pi))) + offset);
            aout.write_u16(sample);
        }
    }
}
```