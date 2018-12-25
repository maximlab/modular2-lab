## LowPowerTimer
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_low_power_timer.png">

LowPowerTimer 类层次结构</div>                

LowPowerTimer 继承自 Timer 类。在这种情况下，计时器即使在深度睡眠模式下也继续运行。它依赖于 lp_ticker，这是低功率的自动收报机。

您可以使用 LowPowerTimer 界面创建，启动，停止和读取计时器，以测量小时间（微秒和秒之间）。您可以独立创建，启动和停止任意数量的 LowPowerTimer 对象。有关电源管理的更多信息，请参阅我们的[电源管理 API](https://os.mbed.com/docs/v5.9/reference/power-management.html)。

## LowPowerTimer 类参考
[mbed::LowPowerTimer 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_low_power_timer.html)

<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html" rel="nofollow" target="_blank">mbed::Timer</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a1f7242a01d99cb0c9c2b80c2966f7f63" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Timer</strong> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structticker__data__t.html" rel="nofollow" target="_blank">ticker_data_t</a> *data)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a3a8b5272198d029779dc9302a54305a8" rel="nofollow" target="_blank">start</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a63f0eb44b27402196590a03781515dba" rel="nofollow" target="_blank">stop</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a9020542d73357a4eef512eefaf57524b" rel="nofollow" target="_blank">reset</a> ()</td>
		</tr><tr><td style="vertical-align:top;">float&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a3836166fa4955dd6d792da5bd6eee48f" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a44decfe8ebd1eada0a60349a17b92720" rel="nofollow" target="_blank">read_ms</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a0b5d2367438dd98b3156b4f11be89a0c" rel="nofollow" target="_blank">read_us</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#af34acd7d7fc46cda500ea533ec9bc4a1" rel="nofollow" target="_blank">operator float</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html#a5c3e0df6091d7427560b5bf7c5d273de" rel="nofollow" target="_blank">read_high_resolution_us</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html" rel="nofollow" target="_blank">mbed::Timer</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a8e5f812d3cdab23fa8ebb06375ffcf55" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>slicetime</strong> ()</td>
		</tr><tr><td colspan="2">&nbsp;受保护的属性继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_timer.html" rel="nofollow" target="_blank">mbed::Timer</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a4d3e749708de44d051e90d49d58ac4b4" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_running</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="adbb65297f8f50630ca5880efbd928796" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_start</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="acf1f4a2b500ffc76a11466e3d7a547ce" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafbbb0a24d16addef2bc749c63e2a7f0f" rel="nofollow" target="_blank">us_timestamp_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_time</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7e3f16c5747dd07da0980f6107d4e7de" target="_blank"></a> const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structticker__data__t.html" rel="nofollow" target="_blank">ticker_data_t</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_ticker_data</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2b866f34a2946c3f7b61eec9c4050d8c" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_lock_deepsleep</strong></td>
		</tr></tbody></table>

## LowPowerTimer 示例
[main.cpp](https://os.mbed.com/teams/mbed_example/code/LowPowerTimer-example/file/13760b19fc77/main.cpp)        
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
 
LowPowerTimer t;
 
int main() {
    t.start();
    printf("Hello World!\n");
    t.stop();
    printf("The time taken was %f seconds\n", t.read());
}
``` 
