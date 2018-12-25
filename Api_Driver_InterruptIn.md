## InterruptIn
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.png">

InterruptIn 类层次结构</div>                                           

使用 InterruptIn 接口在数字输入引脚发生变化时触发事件。您可以在信号的上升沿（从 0 变为 1）或下降沿（从 1 变为 0）触发中断。

## InterruptIn 类参考
[mbed::InterruptIn 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a8cadb613d31308a2907bfe24e03126ea" rel="nofollow" target="_blank">InterruptIn</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#ad0948567dccabedecdab72c55776ff85" rel="nofollow" target="_blank">InterruptIn</a> (PinName pin, PinMode <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#acd131699a73622f6c41c6518ee68a2c8" rel="nofollow" target="_blank">mode</a>)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a828c51d43e56c601886423df71c8e36d" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a853ebe4e34cc1c532c4c89c3108f7f38" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a87a5a96f7d3c6f2b25222fa6b452834f" rel="nofollow" target="_blank">rise</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a84e157fe5824b863e0a06f392fae1092" rel="nofollow" target="_blank">rise</a> (T *obj, M method)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a15c7a6e768786cae6de5bdcc92455452" rel="nofollow" target="_blank">fall</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a774eed83bdbd9a95ea530b2eee9b7754" rel="nofollow" target="_blank">fall</a> (T *obj, M method)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#acd131699a73622f6c41c6518ee68a2c8" rel="nofollow" target="_blank">mode</a> (PinMode pull)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#ab4321a51acb3ddb1b501ace05a9c77f3" rel="nofollow" target="_blank">enable_irq</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_interrupt_in.html#a82678a2930c33c0b2b121f109a0a6302" rel="nofollow" target="_blank">disable_irq</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="ada6beda7d7947c4946aa2e516d68f16c" target="_blank"></a> static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq_handler</strong> (uint32_t id, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gaa0af91058c138031cbcc5b93121644af" rel="nofollow" target="_blank">gpio_irq_event</a> event)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="abdee0dac8340646a3579902e0a0770f7" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>irq_init</strong> (PinName pin)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a3adb4e42b8c06ad9e31b2e8d12c4f5fc" target="_blank"></a> gpio_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gpio</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7618c6ecb1cad04abbb7927ec02bc1b6" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#gaa7bafeb9d84d6a832a86441a38b9c64c" rel="nofollow" target="_blank">gpio_irq_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>gpio_irq</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7743ab84bb3649d131974431105b42d4" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_rise</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="adbb802a1ae3412d0a1e879fc2a24d6dd" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_fall</strong></td>
		</tr></tbody></table>

**警告**:

+ ISR 中没有阻塞代码：避免任何调用等待，无限循环或阻塞调用。

+ 在 ISR 中没有 printf，malloc 或 new：避免调用庞大的库函数。特别是，某些库函数（例如 printf，malloc 和 new）是不可重入的，并且当从 ISR 调用时它们的行为可能会被破坏。

+ 对于来自中断上下文的 printfs，请改用 Event。

## 相关
要阅读输入，请参阅 [DigitalIn](https://os.mbed.com/docs/v5.9/reference/digitalin.html)。

## InterruptIn hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/InterruptIn_HelloWorld/file/f729f0421740/main.cpp)       
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
 
InterruptIn button(SW2);
DigitalOut led(LED1);
DigitalOut flash(LED4);
 
void flip() {
    led = !led;
}
 
int main() {
    button.rise(&flip);  // attach the address of the flip function to the rising edge
    while(1) {           // wait around, interrupts will interrupt this!
        flash = !flash;
        wait(0.25);
    }
}
```
## InterruptIn 示例
尝试以下示例来计算引脚上的上升沿。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/InterruptIn_ex_1/file/8c7b073576c5/main.cpp)   
```
#include "mbed.h"
 
class Counter {
public:
    Counter(PinName pin) : _interrupt(pin) {        // create the InterruptIn on the pin specified to Counter
        _interrupt.rise(callback(this, &Counter::increment)); // attach increment function of this counter instance
    }
 
    void increment() {
        _count++;
    }
 
    int read() {
        return _count;
    }
 
private:
    InterruptIn _interrupt;
    volatile int _count;
};
 
Counter counter(SW2);
 
int main() {
    while(1) {
        printf("Count so far: %d\n", counter.read());
        wait(2);
    }
}
```
相关内容

[Event](https://os.mbed.com/docs/v5.9/reference/event.html) API 参考。

[DigitalIn](https://os.mbed.com/docs/v5.9/reference/digitalin.html) API 参考。