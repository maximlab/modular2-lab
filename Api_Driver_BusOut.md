## BusOut
![BusOut 类层次结构](https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_out.png)
BusOut 类层次结构

使用 BusOut 接口创建许多可以写为一个值的[DigitalOut](https://os.mbed.com/docs/v5.9/reference/digitalout.html) 引脚。此 API 对于一次写入多个输出非常有用。您可以使用此 API 更快地编写更清晰的代码。

您可以在 BusOut 中使用任何编号的 Arm Mbed 引脚作为 DigitalOut。

提示:

* 总线中最多可以有 16 个引脚。
* 构造函数中引脚的顺序是字节顺序中引脚的相反顺序。因此，如果你有 BusOut（a，b，c，d，e，f，g，h），则字节中的位顺序为 hgfedcba，其中 a 为位 0，b 为位 1，c 为位 2 且等等。
BusOut 类参考

[mbed::BusOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_bus_out.html)

|公共成员函数||
|---------------------| :---- |
| 	|BusOut (PinName p0, PinName p1=NC, PinName p2=NC, PinName p3=NC, PinName p4=NC, PinName p5=NC, PinName p6=NC, PinName p7=NC, PinName p8=NC, PinName p9=NC, PinName p10=NC, PinName p11=NC, PinName p12=NC, PinName p13=NC, PinName p14=NC, PinName p15=NC)|
||BusOut (PinName pins[16])|
|void 	|write (int value)|
|int 	|read ()|
|int 	|mask ()|
|BusOut &| 	operator= (int v)|
|BusOut &| 	operator= (BusOut &rhs)|
|DigitalOut &| 	operator[] (int index)|
| 	|operator int ()|
|受保护的成员函数||
|virtual void         	|lock ()|
|virtual void       	|unlock ()|
|受保护的属性||
|DigitalOut *           |	_pin [16]|
|int 	                |_nc_mask|
|PlatformMutex      	|_mutex|
## BusOut Hello World!

[main.cpp](https://os.mbed.com/teams/mbed_example/code/BusOut_HelloWorld/file/6337070122f8/main.cpp)                                                                                                                                             [导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed_example/code/BusOut_HelloWorld)
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
 
BusOut myleds(LED1, LED2, LED3, LED4);
 
int main() {
    while(1) {
        for(int i=0; i<16; i++) {
            myleds = i;
            wait(0.25);
        }
    }
}
```
相关内容

[DigitalOut](https://os.mbed.com/docs/v5.9/reference/digitalout.html) API 参考。