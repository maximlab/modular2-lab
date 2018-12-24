## CircularBuffer

CircularBuffer 类提供了用于从缓冲区推送和弹出数据的 API。在推送数据之前，应检查缓冲区是否已满，因为完整缓冲区会覆盖数据。在执行弹出操作之前，空 API 可用于检查缓冲区中的内容。

CircularBuffer 类是中断安全的；所有数据操作都在关键部分内执行。

CircularBuffer 是一个支持不同数据类型的模板化类。CircularBuffer 类的声明必须指定数据类型和缓冲区大小。

#### 声明示例

这是 BUF_SIZE长 整数 CircularBuffer 的一个例子：
```
CircularBuffer<int, BUF_SIZE> buf;
```
## CircularBuffer 类参考

[mbed::CircularBuffer< T, BufferSize, CounterType > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#a7912eb5ef637aee9dec87ccc2c142027" rel="nofollow" target="_blank">push</a> (const T &amp;data)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#ad3f648bd0c4c64dca2a4549eac41381c" rel="nofollow" target="_blank">pop</a> (T &amp;data)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#a56fe3bd2ff6675dbb26f0394379ba077" rel="nofollow" target="_blank">empty</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#a7f65816f880070ec2fe5c6789c5107b4" rel="nofollow" target="_blank">full</a> () const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#aeaa832ce32a966c1605af04e988c273f" rel="nofollow" target="_blank">reset</a> ()</td>
		</tr><tr><td style="vertical-align:top;">CounterType&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#ae7e61debe736579f2103abfb5afcfd5b" rel="nofollow" target="_blank">size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_circular_buffer.html#ab2a987e38060ad96506c3c33b67e57be" rel="nofollow" target="_blank">peek</a> (T &amp;data) const</td>
		</tr></tbody></table>

## CircularBuffer 示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-circular-buffer/file/6c43979d0645/main.cpp) 
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
#include "mbed.h"
#include "platform/CircularBuffer.h"
 
#define BUF_SIZE    10
 
CircularBuffer<char, BUF_SIZE> buf;
char data_stream[] = "DataToBeAddedToBuffer";
 
int main()
{
    uint32_t bytes_written = 0;
    
    while (!buf.full()) {
        buf.push(data_stream[bytes_written++]);
    }
    
    printf("Circular buffer is full: \"%s\" or empty: \"%s\" \n", 
           (buf.full()? "true":"false"), 
           (buf.empty()? "true":"false") );
    printf ("Bytes written %d \n", bytes_written);
    
    // If buffer is full, contents will be over-written
    buf.push(data_stream[bytes_written++]);
    
    char data;
    printf ("Buffer contents: ");
    while (!buf.empty()) {
        buf.pop(data);
        printf("%c", data);
    }
    printf("\n");
 
    printf("Circular buffer is full: \"%s\" or empty: \"%s\" \n", 
           (buf.full()? "true":"false"), 
           (buf.empty()? "true":"false") );
 
    return 0;
    
}
```