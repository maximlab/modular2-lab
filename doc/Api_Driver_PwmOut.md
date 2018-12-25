## PwmOut
使用 PwmOut 接口控制 PWM 信号的频率和占空比。

### 提示:

首先设置循环时间，然后使用 write() 函数的相对时间段或使用 pulsewidth() 函数的绝对时间段设置占空比。
默认时间为 0.020 秒，默认脉冲宽度为 0。
## PwmOut 类参考
[mbed::PwmOut 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#aeabde4bb4a824f5c493805478629328f" rel="nofollow" target="_blank">PwmOut</a> (PinName pin)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a44e9ac2e3b95e1133d04d993efd59786" rel="nofollow" target="_blank">write</a> (float value)</td>
		</tr><tr><td style="vertical-align:top;">float&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a99a0e317b7151b0ca3079aeeaae3174b" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#af38b6bbdeeea826adeb08a5bc0f589b1" rel="nofollow" target="_blank">period</a> (float seconds)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#afe6978a1258e95c2be951db4b056e1e3" rel="nofollow" target="_blank">period_ms</a> (int ms)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a3b572ee5728d5bd0a0566065009eb72b" rel="nofollow" target="_blank">period_us</a> (int us)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a5eadc941cb8b814228b16d2e2646caf4" rel="nofollow" target="_blank">pulsewidth</a> (float seconds)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a266f50dbfb5e958f34a5a50033621b0b" rel="nofollow" target="_blank">pulsewidth_ms</a> (int ms)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#af628091e2ad735cf17b92ad8428dc2b5" rel="nofollow" target="_blank">pulsewidth_us</a> (int us)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html" rel="nofollow" target="_blank">PwmOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#acc68767ccdc14a7478b3d2a2d6dd7235" rel="nofollow" target="_blank">operator=</a> (float value)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html" rel="nofollow" target="_blank">PwmOut</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a836fd07a726866df544983cb0007eec0" rel="nofollow" target="_blank">operator=</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html" rel="nofollow" target="_blank">PwmOut</a> &amp;rhs)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a59b3748dbd986e9a24f6e6db2417f226" rel="nofollow" target="_blank">operator float</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a2928d260c71279355df1d47289e9e2ba" rel="nofollow" target="_blank">lock_deep_sleep</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_pwm_out.html#a8bb588cd00ad24b1805ec4e7678e36ac" rel="nofollow" target="_blank">unlock_deep_sleep</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5019236623400710fc1d0441bf94de63" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#ga6609ec508d3754cc47e6b771cbdca74d" rel="nofollow" target="_blank">pwmout_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_pwm</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7f7b36a3f9cb538e6fefe0fefaca997b" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_deep_sleep_locked</strong></td>
		</tr></tbody></table>
        
## PwmOut hello, world
此代码示例使用默认时间段 0.020 秒，并将占空比从 0 ％ 增加到 100 ％，增量为 10 ％。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/PwmOut_HelloWorld/file/5160ea45399b/main.cpp)  
```
#include "mbed.h"
 
PwmOut led(LED1);
 
int main() {
    // specify period first
    led.period(4.0f);      // 4 second period
    led.write(0.50f);      // 50% duty cycle, relative to period
    //led = 0.5f;          // shorthand for led.write()
    //led.pulsewidth(2);   // alternative to led.write, set duty cycle time in seconds
    while(1);
}
```
## PwmOut 代码示例
### 示例一

此代码示例将周期（以秒为单位）和占空比设置为浮点周期的百分比（范围：0 到 1）。此代码段的作用是使 LED2 在 4 秒周期内闪烁 50 ％，两秒钟开启，两秒钟关闭。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/PwmOut_ex_1/file/07220dd760cc/main.cpp)        
```
#include "mbed.h"
 
PwmOut led(LED2);
 
int main() {
    // specify period first, then everything else
    led.period(4.0f);  // 4 second period
    led.write(0.50f);  // 50% duty cycle
    while(1);          // led flashing
}
```

### 示例二

下面的示例执行相同的操作，但不是将占空比指定为周期的相对百分比，而是将其指定为以秒为单位的绝对值。在这种情况下，我们有一个四秒的周期和一个两秒的占空比，这意味着 LED 将开启两秒钟并关闭两秒钟。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/PwmOut_ex_2/file/248dfc85bbf9/main.cpp)        
```
#include "mbed.h"
 
PwmOut led(LED2);
 
int main() {
    // specify period first, then everything else
    led.period(4.0f);  // 4 second period
    led.pulsewidth(2); // 2 second pulse (on)
    while(1);          // led flashing
}
``` 
