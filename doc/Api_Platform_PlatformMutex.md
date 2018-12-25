## PlatformMutex
<div align=center><img title="PlatformMutex 类层次结构" src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.png">

PlatformMutex 类层次结构</div>
 

PlarformMutex 类在没有 RTOS 的情况下提供互斥存根函数。此类使您可以在 RTOS 不存在时使用驱动程序/应用程序代码。

## PlatformMutex 类参考

[PlatformMutex 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="a4cc129e1c82efaf3eba58b60cab2553f" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lock</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="acb125431e198c9d2e3e623be58996e6c" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>unlock</strong> ()</td>
		</tr></tbody></table>

## PlatformMutex 示例

下面的代码演示了 PlatformMutex 的用法。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-platform-mutex/file/2084d9e90526/main.cpp) 

```
#include "mbed.h"
 
PlatformMutex stdio_mutex;
Thread t2;
Thread t3;
    
void notify(const char* name, int state) {
    stdio_mutex.lock();
    printf("%s: %d\n\r", name, state);
    stdio_mutex.unlock();
}
 
void test_thread(void const *args) {
    while (true) {
        notify((const char*)args, 0); wait(1);
        notify((const char*)args, 1); wait(1);
    }
}
 
int main() {
    t2.start(callback(test_thread, (void *)"Th 2"));
    t3.start(callback(test_thread, (void *)"Th 3"));
 
    test_thread((void *)"Th 1");
}
``` 
对于所有驱动程序，Mbed OS 使用 PlatformMutex 类而不是 RTOS 互斥锁。例如，请参见 AnalogIn，BusOut，SPI，Serial 和 I2C。

相关内容

[AnalogIn](https://os.mbed.com/docs/v5.9/reference/analogin.html).
[BusOut](https://os.mbed.com/docs/v5.9/reference/busout.html).
[SPI](https://os.mbed.com/docs/v5.9/reference/spi.html).
[Serial](https://os.mbed.com/docs/v5.9/reference/serial.html).
[I2C](https://os.mbed.com/docs/v5.9/reference/i2c.html).