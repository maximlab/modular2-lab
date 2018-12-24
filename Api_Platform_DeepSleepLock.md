## DeepSleepLock

DeepSleepLock 类提供用于禁用睡眠的 RAII 对象。换句话说，创建 DeepSleepLock 对象会调用其构造函数，该构造函数会增加深度睡眠防护锁定。当对象超出范围时，DeepSleepLock 对象会在其析构函数中自动释放深度睡眠防护锁。另一种看待它的方法是当 DeepSleepLock 对象存在时，它会阻止深度睡眠。

**注意**: 不在深度睡眠模式下工作的驱动程序会自动阻止深度睡眠模式，因此 DeepSleepLock 不需要保护它们。

## DeepSleepLock 类参考

[mbed::DeepSleepLock 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_deep_sleep_lock.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_deep_sleep_lock.html#a57e764fd24adb190cd3aaf9b101cef2b" rel="nofollow" target="_blank">lock</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_deep_sleep_lock.html#a223b0caa20ca53da614302e8043b5619" rel="nofollow" target="_blank">unlock</a> ()</td>
		</tr></tbody></table>

## 示例

此示例显示了如何锁定深度睡眠以减少中断延迟，但代价是功耗增加。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/DeepSleepLock_Example_1/file/66aac0656e71/main.cpp)      
```
#include "mbed.h"
 
InterruptIn button(BUTTON1);
DigitalOut led(LED1);
 
void toggle()
{
    led = !led;
}
 
int main()
{
    button.rise(&toggle);
    button.fall(&toggle);
 
    // Lock deep sleep to decrease interrupt latency
    // at the expense of high power consumption
    DeepSleepLock lock;
 
    while(1) {
        // Wait and let interrupts take care of the rest
        wait(1.0);
    }
}
```
## 相关内容

[电源管理 API 参考](https://os.mbed.com/docs/v5.9/reference/power-management.html)。