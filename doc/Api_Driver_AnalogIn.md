## AnalogIn

使用 AnalogIn API 读取施加到模拟输入引脚的外部电压。AnalogIn() 将电压读取为系统电压的一部分。该值是从 0.0（VSS）到 1.0（VCC）的浮点。例如，如果您有 3.3 V 系统且施加的电压为1.65V，则 AnalogIn() 读取 0.5 作为值。

目前微控制器中使用的最常见的模数转换器之一称为逐次逼近型 ADC。逐次逼近是现代微控制器中的一种流行选择，因为它精确且低功耗，占用微控制器内部的少量空间。

另一种相当常见的 ADC 类型是 Flash ADC。Flash ADC 提供最快的模数转换解决方案。但是，由于 Flash ADC 的构建方式，它们使用大量功率并占用大量空间，因为它们使用了许多组件。

ADC 的分辨率是模拟输入中最小的可区分变化，会导致数字输出发生变化。例如，3.3 V 系统中的 12 位 ADC 具有 4096 个可区分的输出。因此，12 位 ADC 的分辨率为 3.3 / 4096 = 0.81 mV。在 Mbed Enabled 系统中，来自模拟输入的数字结果在 0.0 到 1.0 的范围内，模拟输入中 0.81 mV 的变化导致数字输出的变化为 1.0 / 4096 = 0.00024。

注意: 只有某些引脚能够进行这些测量，因此请检查电路板的 pinmap 是否有兼容的引脚。

## AnalogIn 类参考

[mbed::AnalogIn](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_in.html) 类参考

|公共成员函数||
|-|:-|
| 	|[AnalogIn](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_in.html#a6b6f944caa4bbf118d0b3947ebb410b7) (PinName pin)|
|float 	|[read ()](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_in.html#a5047c42e441bfcde39c46069d96dd082)|
|unsigned short 	|[read_u16 ()](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_in.html#a78a2d1c60bd542bacb785b6cc0701013)|
| 	|[operator float ()](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_analog_in.html#ad6a2c5d25b7366fd2854f464fc54bc53)|
|受保护的成员函数||
|virtual void 	|lock ()|
|virtual void 	|unlock ()|
|受保护的属性||
|[analogin_t](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gafa32cdedb214c3418acfc08948c7c795) 	|_adc|
|静态保护属性||
|static [SingletonPtr](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_singleton_ptr.html)< [PlatformMutex](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html) > |	_mutex|

## AnalogIn hello, world

[main.cpp](https://os.mbed.com/teams/mbed_example/code/AnalogIn_HelloWorld/file/77750f8cba47/main.cpp)                                                                                                                                              <div align=right>[导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed_example/code/AnalogIn_HelloWorld)</div>
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
 
// Initialize a pins to perform analog input and digital output fucntions
AnalogIn   ain(A0);
DigitalOut dout(LED1);
 
int main(void)
{
    while (1) {
        // test the voltage on the initialized analog pin
        //  and if greater than 0.3 * VCC set the digital pin
        //  to a logic 1 otherwise a logic 0
        if(ain > 0.3f) {
            dout = 1;
        } else {
            dout = 0;
        }
        
        // print the percentage and 16 bit normalized values
        printf("percentage: %3.3f%%\n", ain.read()*100.0f);
        printf("normalized: 0x%04X \n", ain.read_u16());
        wait(0.2f);
    }
}
 ```
## AnalogIn 示例

### 示例一

用模拟输入控制 R/C 伺服。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/AnalogIn_ex_1/file/490818b6238b/main.cpp)                                                                                                                                               <div align=right>[导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed_example/code/AnalogIn_ex_1)</div>
```
#include "mbed.h"
 
AnalogIn position(A0);
PwmOut servo(D3);
 
int main() {
    // servo requires a 20ms period    
    servo.period(0.020f);
    while (1) {
        // servo position determined by a pulse width between 1-2ms
        servo.pulsewidth(0.001f + 0.001f * position);
    }
}
 ```
### 示例二

此示例显示 AnalogIn 读取 16 位标准化样本。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/AnalogIn_ex_2/file/cb98929b3895/main.cpp)                                                                                                                                              <div align=right>[导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed_example/code/AnalogIn_ex_2)</div>
```
#include "mbed.h"
 
AnalogIn input(A0);
 
int main() {
    uint16_t samples[1024];
 
    for(int i=0; i<1024; i++) {
        samples[i] = input.read_u16();
        wait(0.001f);
    }
 
    printf("Results:\n");
    for(int i=0; i<1024; i++) {
        printf("%d, 0x%04X\n", i, samples[i]);
    }
}   
```