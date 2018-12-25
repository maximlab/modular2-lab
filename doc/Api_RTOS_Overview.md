## RTOS 概述
Mbed OS RTOS 功能包括管理线程，同步对象和定时器等对象。它还提供用于附加特定于应用程序的空闲挂钩函数的接口，读取操作系统滴答计数并实现报告 RTOS 错误的功能。

Mbed RTOS 的代码可以在 mbed-os 存储库的 [RTOS 子目录](https://github.com/ARMmbed/mbed-os/tree/master/rtos)中找到。有关更多信息，请参阅 [Doxygen](https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html)。

## RTOS Ticker

使用 RTOS 的平台，包括 Mbed OS，需要一种机制来计算时间和调度任务。产生周期性中断的定时器通常称为系统节拍定时器。在 Mbed OS 下，我们将此机制称为 RTOS ticker。

SysTick 是大多数 Cortex-M 内核上的标准定时器。其主要目的是以设定频率（通常为 1 ms）产生中断。此外，许多 Mbed OS 平台都将定时器作为外设的一部分。Mbed OS 支持使用 SysTick 或外设定时器作为 RTOS ticker。

Mbed OS 平台使用 SysTick 作为默认的 RTOS ticker，但如果您想使用其中一个外围计时器作为 RTOS ticker，则可以覆盖默认的 SysTick 计时器。例如，请参阅低功耗 ticker，了解如何使用外部低功耗定时器执行仅需要毫秒精度的高功效定时操作。

## RTOS API

RTOS API 处理 Arm Mbed OS 5 中线程的创建和销毁，以及安全的线程间通信机制。线程是 Mbed OS 5 的核心组件（即使你的主要功能也是从它自己的线程开始），因此了解如何使用它们是开发 Mbed OS 5 应用程序的重要部分。

+ Thread: 允许定义，创建和控制并行任务的类。
+ Mutex: 该类用于同步线程的执行。
+ Semaphore: 管理对特定类型的共享资源池的线程访问的类。
+ Queue: 允许您将指向生产者线程数据的指针排队到使用者线程的类。
+ MemoryPool: 此类可用于定义和管理固定大小的内存池。
+ Mail: 提供队列以及用于分配消息的内存池的 API。
+ RtosTimer: 不推荐使用的类，用于控制系统中的计时器功能。
+ EventFlags: 一个事件通道，提供通知其他线程有关条件或事件的通用方法。您可以从 ISR 上下文调用一些 EventFlags 函数，每个 EventFlags 对象最多可以支持 31 个标志。
+ Event: 存储事件的队列，提取它们并在以后执行它们。
+ ConditionVariable: ConditionVariable 类提供了一种安全等待或发出单个状态更改信号的机制。您无法从 ISR 上下文调用 ConditionVariable 函数。
+ Kernel: 内核命名空间实现控制或读取 RTOS 信息的功能，例如滴答计数。

## 默认超时

Mbed RTOS API 为生产者方法选择了默认为 0 超时（无等待），为消费者方法选择了 osWaitForever（无限等待）。

生产者的典型场景可能是外围设备触发中断以通知事件；在相应的中断服务程序中，您不能等待（这会使整个系统死锁）。另一方面，消费者可以是等待事件的后台线程；在这种情况下，所需的默认行为是在生成此事件之前不使用 CPU 周期，因此 osWaitForever。

**注意**: 在 ISR 中调用 RTOS 对象方法时，所有超时参数必须设置为 0（无等待）；在 ISR 等待是不允许的。

## main() 函数

函数 main 是一个特殊的线程函数，它在系统初始化时启动，并具有初始优先级 osPriorityNormal；它是 RTOS 计划的第一个主题。

线程可以处于以下状态：

+ Running: 当前正在运行的线程。一次只能有一个线程处于此状态。
+ Ready: 准备运行的线程。一旦正在运行的线程终止或正在等待，具有最高优先级的就绪线程将成为正在运行的线程。
+ Waiting: 正在等待事件发生的线程。
+ Inactive: 未创建或终止的线程。这些线程通常不消耗系统资源。
                                                  
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/thread_status.png"></div>

## 信号

每个线程都可以等待信号并收到事件通知：

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_signals/file/476186ff82cf/main.cpp)       
```
#include "mbed.h"
 
Thread thread;
DigitalOut led(LED1);
 
void led_thread() {
    while (true) {
        // Signal flags that are reported as event are automatically cleared.
        Thread::signal_wait(0x1);
        led = !led;
    }
}
 
int main (void) {
    thread.start(callback(led_thread));
 
    while (true) {
        wait(1);
        thread.signal_set(0x1);
    }
}
``` 
状态和错误码

Mbed OS 错误处理系统为 RTOS 相关的错误分配特定的错误代码。有关报告的 RTOS 错误的详细信息，请参阅错误处理文档。