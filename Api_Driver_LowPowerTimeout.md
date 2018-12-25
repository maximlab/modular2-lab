LowPowerTimeout
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.png">

LowPowerTimeout 类层次结构</div>                

使用 LowPowerTimeout 接口设置中断以在指定的延迟后调用函数。您可以创建任意数量的 LowPowerTimeout 对象。这允许同时有多个未完成的中断。有关电源管理的更多信息，请参阅我们的电源管理 API。

**注意**

+ ISR 中没有阻塞代码：避免任何调用等待，无限循环或阻塞调用。
+ 在 ISR 中没有 printf，malloc 或 new：避免调用庞大的库函数。特别是，某些库函数（例如 printf，malloc 和 new）不可重入，并且当从 ISR 调用时它们的行为可能会被破坏。
## LowPowerTimeout 类参考
[mbed::LowPowerTimeout 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_low_power_timeout.html)

<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html" rel="nofollow" target="_blank">mbed::Ticker</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a631e5575d55463ac52879318adda281f" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Ticker</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structticker__data__t.html" rel="nofollow" target="_blank">ticker_data_t</a> *data)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#af427ceb53b3bdb54acec21cfd8d06db3" rel="nofollow" target="_blank">attach</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func, float t)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#aabdea52998c98ac3b5f001b3e4d7e0c6" rel="nofollow" target="_blank">attach</a> (T *obj, M method, float t)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#a1569815754be96a80a592a38353b95e9" rel="nofollow" target="_blank">attach_us</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a> t)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#aeb296fef1fea42b35444d0a4f671b74b" rel="nofollow" target="_blank">attach_us</a> (T *obj, M method, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a> t)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#a07a1e3eae57ba0586ad5680f7efdb3db" rel="nofollow" target="_blank">detach</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html" rel="nofollow" target="_blank">mbed::TimerEvent</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7040dd69b30324b7220d07ccaca9a538" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>TimerEvent</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structticker__data__t.html" rel="nofollow" target="_blank">ticker_data_t</a> *data)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html#a54b6f956609dde77a2a8ee9f0ada6213" rel="nofollow" target="_blank">~TimerEvent</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html" rel="nofollow" target="_blank">mbed::TimerEvent</a></td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html#a5b37d4b07b725eee820078805577c2db" rel="nofollow" target="_blank">irq</a> (uint32_t id)</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html" rel="nofollow" target="_blank">mbed::Ticker</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="adb8284c32831bccba05b288ab5906786" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>setup</strong> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a> t)</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html" rel="nofollow" target="_blank">mbed::TimerEvent</a></td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html#adbc9c36ead585c3880d775ba6f7852ac" rel="nofollow" target="_blank">insert</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gaf889abd7a487d58af4c374658afc1dd3" rel="nofollow" target="_blank">timestamp_t</a> timestamp)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html#a6f98a425f37d96d23aa7155ba4202836" rel="nofollow" target="_blank">insert_absolute</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a> timestamp)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html#a5b885f43fc22826b0f735a72841dca84" rel="nofollow" target="_blank">remove</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html" rel="nofollow" target="_blank">mbed::Ticker</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#abd48d5170bc96db6beac55d8f83d3cc1" rel="nofollow" target="_blank">_delay</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#a2fae9dbbc834590c77314b2b6a771fd8" rel="nofollow" target="_blank">_function</a></td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_ticker.html#aa108404e9f466a04e0447048a1611389" rel="nofollow" target="_blank">_lock_deepsleep</a></td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer_event.html" rel="nofollow" target="_blank">mbed::TimerEvent</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a80ea97a2c88250aa898f4adda12a9228" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#ga09bb9e24187801076cb6bdd965e563fb" rel="nofollow" target="_blank">ticker_event_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>event</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="acc2c35b1cf2900aa08357b1a2a64db02" target="_blank"></a> const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structticker__data__t.html" rel="nofollow" target="_blank">ticker_data_t</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_ticker_data</strong></td>
		</tr></tbody></table>

## LowPowerTimeout 示例
在给定时间后设置超时 LED 的时间：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/LowPowerTimeout-example/file/28699dc8770e/main.cpp)      
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
 
LowPowerTimeout flipper;
DigitalOut led1(LED1);
DigitalOut led2(LED2);
 
void flip() {
    led2 = !led2;
}
 
int main() {
    led2 = 1;
    flipper.attach(&flip, 2.0); // setup flipper to call flip after 2 seconds
 
    // spin in a main loop. flipper will interrupt it to call flip
    while(1) {
        led1 = !led1;
        wait(0.2);
    }
}
```