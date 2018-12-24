## 能源管理

## 睡眠

Mbed OS 中只有一个睡眠功能：
```
void sleep();
```
此函数调用睡眠管理器，它选择最合适的睡眠模式。

**注意**: 在大多数情况下，您不需要直接调用 sleep()。只要系统空闲，Mbed OS 就会自动进入睡眠模式。这是所有线程都处于等待状态，例如等待事件或超时。

### 睡眠模式

有两种可用的睡眠模式：

    1. 睡眠模式

核心的系统时钟停止，直到发生复位或中断。这消除了处理器，存储器系统和总线使用的动态功率。此模式保持处理器，外设和存储器状态，外设继续工作并可产生中断。

您可以通过任何内部外设中断或外部引脚中断唤醒处理器。

    2. 深度睡眠模式

此模式类似于睡眠但节省更多功率并具有更长的唤醒时间。它通过关闭高速时钟节省了额外的功率。因此，只有在不使用高速时钟的外设时才能进入此模式。不依赖于高速时钟的外设包括 LowPowerTicker，RTC 和 InterruptIn API。此模式保持所有状态。

### 睡眠管理

睡眠管理器提供 API 和逻辑来控制设备睡眠模式选择。虽然标准睡眠不会影响应用程序执行，但深度睡眠可能会引入一些可能影响应用程序的额外功耗，例如高速时钟相关驱动程序。为了确保应用程序的正确运行，睡眠管理器可能会禁用深度睡眠，在这种情况下，您的电路板会进入正常睡眠状态。此机制对用户来说几乎是不可见的，但您应该知道它可能会影响硬件的功耗。

这些 Mbed OS 驱动程序可以锁定深度睡眠：

+ Ticker.
+ Timeout.
+ Timer.
+ SPI.
+ I2C.
+ CAN.
+ SerialBase.

### 睡眠/深度睡眠分析工具

Mbed OS 可以帮助您了解设备的睡眠模式，特别是持有睡眠锁的人，防止您的电路板进入深度睡眠状态。要启用跟踪，您需要做的就是定义 MBED_SLEEP_TRACING_ENABLED 宏。您可以通过修改 mbed_app.json 配置文件或将 -DMBED_SLEEP_TRACING_ENABLED 附加到 mbed 编译命令来完成此操作。

Mbed OS 将在标准输出上打印睡眠跟踪，默认情况下为 UART。我们跟踪的一些事件：

+ 锁定深度睡眠：LOCK：<文件名>，ln：<文件中的行>，锁定计数：<持有的锁数>
+ 解锁深度睡眠：UNLOCK：<文件名>，ln：<文件中的行>，锁定计数：<持有的锁数>
+ 进入睡眠状态：Mbed OS 将打印一个锁定列表，防止电路板进入深度睡眠状态：
```
Sleep locks held:
[id: <file name 1>, count: <number of locks>]
[id: <file name 2>, count: <number of locks>]
```
示例跟踪可能如下所示：
```
LOCK: mbed_rtx_idle.cpp, ln: 129, lock count: 2
Sleep locks held:
[id: mbed_wait_api_, count: 1]
[id: mbed_rtx_idle., count: 1]
UNLOCK: mbed_rtx_idle.cpp, ln: 131, lock count: 1
LOCK: mbed_rtx_idle.cpp, ln: 129, lock count: 2
Sleep locks held:
[id: mbed_wait_api_, count: 1]
[id: mbed_rtx_idle., count: 1]
UNLOCK: mbed_rtx_idle.cpp, ln: 131, lock count: 1
```
**注意**: 睡眠跟踪是一种调试功能，只应在开发周期中启用。大量使用 UART 会影响器件性能。

### 示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/SleepManager_Example_1/file/e85412b4147e/main.cpp)                                                                                              
```
#include "mbed.h"
 
int main()
{
    // Deep sleep for 1 second
    printf("Deep sleep allowed: %i\r\n", sleep_manager_can_deep_sleep());
    wait(1.0);
    
    // Lock deep sleep
    printf("Locking deep sleep\r\n");
    sleep_manager_lock_deep_sleep();
    
    // Sleep for 1 second
    printf("Deep sleep allowed: %i\r\n", sleep_manager_can_deep_sleep());
    wait(1.0);
}
```

## 系统重置

Mbed OS 提供标准化调用以对系统进行电源循环：
```
void system_reset();
```
调用后，处理器和大多数组件将重置，但不会影响调试子系统。

### 函数参考

[电源管理函数](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__platform__power__mgmt.html)

## 空闲循环

空闲循环是后台系统线程，当没有其他线程准备好运行时，调度程序执行。当您的应用程序等待事件发生时，可能会发生这种情况。默认情况下，空闲循环调用睡眠管理器进入睡眠模式。您可以通过提供不同的处理程序来覆盖此行为：
```
void new_idle_loop()
{
    // do nothing
}
 
void main()
{
    rtos_attach_idle_hook(&new_idle_loop);
}
```
### 函数参考

[空闲挂钩函数](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos___idle.html)

### 示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/SleepManager_Example_1/file/e85412b4147e/main.cpp)                                                                                              
```
#include "mbed.h"
 
int main()
{
    // Deep sleep for 1 second
    printf("Deep sleep allowed: %i\r\n", sleep_manager_can_deep_sleep());
    wait(1.0);
    
    // Lock deep sleep
    printf("Locking deep sleep\r\n");
    sleep_manager_lock_deep_sleep();
    
    // Sleep for 1 second
    printf("Deep sleep allowed: %i\r\n", sleep_manager_can_deep_sleep());
    wait(1.0);
}
```
## 相关内容

[DeepSleepLock API 参考](https://os.mbed.com/docs/v5.9/reference/deepsleeplock.html).
