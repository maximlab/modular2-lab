## Time

C 日期和时间函数是 C 编程语言的标准库中的一组函数，用于实现日期和时间操作操作。它们支持时间获取，日期格式之间的转换以及格式化输出到字符串。

您可以使用 ctime，localtime，strftime 和其他 C 标准函数将时间转换为人类可读的格式。

您不能在具有 GCC 工具链的中断处理程序中使用 time，mktime 和 localtime C 标准库函数。我们添加了专用例程 _rtc_mktime 和 _rtc_localtime，它们优化得比 C 标准库函数更快，以克服这个问题。

## Time 函数参考

[mbed_mktime.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__mktime_8h_source.html)

## Time 示例

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
## 2038

我们将为 2038 年的问题准备 Arm Mbed 库，并希望尽可能减少干扰。有关[维基百科](https://en.wikipedia.org/wiki/Year_2038_problem) 2038 年问题的更多信息：

2038 年问题是计算和数据存储情况的问题，其中时间值被存储或计算为带符号的 32 位整数，并且该数字被解释为自 1970 年 1 月 1 日 00:00:00 UTC 以来的秒数。（“时代”）。[1] 此类实现无法对 2038 年 1 月 19 日 03:14:07 UTC 之后的时间进行编码，这个问题与 “Y2K 问题”（也称为 “千年虫”）类似但不完全类似，其中 2 位数值代表自 1900 年以来的年数无法编码 2000 年或更晚。大多数 32 位类 Unix 系统以这种 “Unix 时间” 格式存储和操作时间，因此 2038 年的问题有时被称为“Unix Millennium Bug”。