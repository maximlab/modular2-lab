## CriticalSectionLock

CriticalSectionLock 类提供了一种不间断地访问资源的机制。使用 CriticalSectionLock :: enable() API，您可以输入禁用中断的关键部分。CriticalSectionLock :: disable() API是从关键部分退出，最后一个退出调用恢复中断状态。

CriticalSectionLock 类基于 RAII 方法。换句话说，构造函数获取锁，并且析构函数在超出范围时自动销毁它。我们不建议您将CriticalSectionLock 用作全局或类的成员，因为您将在对象创建时输入关键部分，并且将禁用所有中断。

Mbed OS 支持关键部分的嵌套，并且析构函数仅在您从最后一个嵌套关键部分退出时启用中断。

**注意**: 您不得在关键部分内使用耗时的操作，标准库和 RTOS 功能。

### CriticalSectionLock 类参考

[mbed::CriticalSectionLock 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_critical_section_lock.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_critical_section_lock.html#a87d4a6d8b800233b53b3ba3edfae0e73" rel="nofollow" target="_blank">lock</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_critical_section_lock.html#a5ac094cd27b86fe9da70f68394f02986" rel="nofollow" target="_blank">unlock</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_critical_section_lock.html#a405439868776c1c32b932eb8a4d61047" rel="nofollow" target="_blank">enable</a> ()</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_critical_section_lock.html#ab25f6b65ae3413b831b16915d20beee2" rel="nofollow" target="_blank">disable</a> ()</td>
		</tr></tbody></table>

### CriticalSectionLock 示例

这是一个演示竞争条件问题以及 CriticalSectionLock 如何帮助解决它的示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-critical-section/file/a88acbffd78b/main.cpp)                                                                                                  
```
/*
 * Copyright (c) 2016-2016, ARM Limited, All Rights Reserved
 * SPDX-License-Identifier: Apache-2.0
 *
 * Licensed under the Apache License, Version 2.0 (the "License"); you may
 * not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#include "rtos/Thread.h"
#include "mbed.h"
#include "rtos/rtos_idle.h"
#include "platform/mbed_critical.h"
 
#define  USE_CRITICAL_SECTION_LOCK      1   // Set 0 to see race condition
// Note: Might require few runs to see race condition
 
#define THREAD_CNT  8
 
int32_t value = 100000;
volatile int32_t count = 0;
 
void increment(void) {
    for (int i = 0; i < value; i++) {
#if (USE_CRITICAL_SECTION_LOCK == 1)
        CriticalSectionLock  lock;
#endif
        count += 1;
    }
}
 
int get_count(void) {
    if (count == (value * THREAD_CNT)) {
        printf("No Race condition\n");
    } else {
        printf("Race condition\n");
    }
    return count;
}
 
int main()
{
    Thread counter_thread[THREAD_CNT];    
 
    for (int i = 0; i < THREAD_CNT; i++) {
        counter_thread[i].start(callback(increment));
    }
    
    // Wait for the threads to finish
    for (int i = 0; i < THREAD_CNT; i++) {
        counter_thread[i].join();
    }    
    printf ("Counter = %d\n", get_count());
}
```