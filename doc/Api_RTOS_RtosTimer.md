## RtosTimer
**弃用**: EventQueue 取代了 RtosTimer。RtosTimer 和 EventQueue 复制了中断上下文之外的定时事件的功能；但是，EventQueue 具有其他功能来处理将其他事件推迟到多个上下文。
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.png">

RtosTimer 类层次结构</div>                                                           
使用 RtosTimer 类在系统中创建和控制计时器功能。当时间段到期时调用定时器功能，因此单触发和定时定时器都是可能的。您可以启动，重新启动或停止计时器。

线程 osTimerThread 处理定时器。回调函数在此线程的控制下运行，并可能使用基础 RTOS API 调用。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/rtos_timer.png"></div>

RtosTimer 类参考
[rtos::RtosTimer 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html)
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#aa61f330321c777f08022a018ca8c8df1" rel="nofollow" target="_blank">RtosTimer</a> (void(*func)(void const *argument), os_timer_type type=osTimerPeriodic, void *argument=NULL)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#adf21491808d4db56847768340c72f689" rel="nofollow" target="_blank">RtosTimer</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt; func, os_timer_type type=osTimerPeriodic)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename M &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#a48e4774c26ee03f0d5e3d75db87da4d9" rel="nofollow" target="_blank">RtosTimer</a> (T *obj, M method, os_timer_type type=osTimerPeriodic)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#a33a6c31979451fa4a17b2a065ce9e5d4" rel="nofollow" target="_blank">stop</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#afc4a4b752ce764cf0b47d4213acc8869" rel="nofollow" target="_blank">start</a> (uint32_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_rtos_timer.html#a17b653ae7c598cd25f7c66493cffda38" rel="nofollow" target="_blank">~RtosTimer</a> ()</td>
		</tr></tbody></table>

## RtosTimer 示例
控制四个 LED 的时序。

[main.cpp](https://os.mbed.com/teams/mbed/code/rtos_timer/file/tip/main.cpp)        
```
#include "mbed.h"
#include "rtos.h"
 
DigitalOut LEDs[4] = {
    DigitalOut(LED1), DigitalOut(LED2), DigitalOut(LED3), DigitalOut(LED4)
};
 
void blink(void const *n) {
    LEDs[(int)n] = !LEDs[(int)n];
}
 
int main(void) {
    RtosTimer led_1_timer(blink, osTimerPeriodic, (void *)0);
    RtosTimer led_2_timer(blink, osTimerPeriodic, (void *)1);
    RtosTimer led_3_timer(blink, osTimerPeriodic, (void *)2);
    RtosTimer led_4_timer(blink, osTimerPeriodic, (void *)3);
    
    led_1_timer.start(2000);
    led_2_timer.start(1000);
    led_3_timer.start(500);
    led_4_timer.start(250);
    
    Thread::wait(osWaitForever);
}
```