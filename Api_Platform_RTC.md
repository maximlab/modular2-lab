## RTC

RTC（实时时钟）提供了使用 set_time API 设置硬件 RTC 的当前时间的机制。时间设置为从时间纪元（Unix Epoch - 1970 年 1 月 1 日）以秒为单位测量的偏移量。

您可以使用 attach_rtc API 挂接外部 RTC 以使用 C 时间函数。它为您提供了附加的 init()，read()，write() 和 isenabled() 函数。Time 提供有关 C 日期和时间标准库函数的更多信息。

RTC 类 API 是线程安全的。

如果连接了二次电源（电池），RTC 即使在断电状态下也可以跟踪时间。

RTC 函数参考

[mbed_rtc_time.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__rtc__time_8h_source.html)

RTC Time 示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/time_HelloWorld/file/8593c9813840/main.cpp)   
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
 
int main() {
    set_time(1256729737);  // Set RTC time to Wed, 28 Oct 2009 11:35:37
 
    while (true) {
        time_t seconds = time(NULL);
        
        printf("Time as seconds since January 1, 1970 = %d\n", seconds);
        
        printf("Time as a basic string = %s", ctime(&seconds));
 
        char buffer[32];
        strftime(buffer, 32, "%I:%M %p\n", localtime(&seconds));
        printf("Time as a custom formatted string = %s", buffer);
        
        wait(1);
    }
}
```