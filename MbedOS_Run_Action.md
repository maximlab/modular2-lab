## 执行

## 线程

您的应用程序（主函数）在主线程中开始执行，但它不是 Mbed OS 中唯一运行的线程。有许多线程在运行系统服务，例如：

+ Main - 执行应用程序主函数的默认线程。主线程默认具有 4kB 的栈空间。应用程序可以通过定义 MAIN_STACK_SIZE 参数在 mbed_app.json 中对其进行配置。
+ Idle - 当系统中没有其他活动时由调度程序运行的线程（例如，所有其他线程都在等待某个事件）。它用于确保电路板没有烧掉空的处理器周期，但是尽可能长时间地进入休眠状态。
+ Timer - 处理系统和用户计时器对象的线程。注意：不推荐使用用户计时器类 RtosTimer。您不应该将它用于新设计。请改用 EventQueue。

在标准系统线程之上，某些驱动程序可能使用其他线程。用户可以使用 Thread 类创建线程。

## 模式

Mbed OS 以两种模式执行：

+ 线程模式 - 默认应用程序模式。所有用户线程都以此模式执行。它使用专用线程特定的栈内存。
+ 处理程序模式 - 中断模式，系统代码和中断处理程序在此模式下执行。它使用静态系统 ISR 栈内存。
### 处理程序模式

所有 ISR 处理程序都以此模式执行。您可以在 ISR 处理程序中使用相同的 RTOS API。模式之间的重要区别在于为处理程序模式编写的代码不能等待；它尽可能快地执行并返回到线程模式。因此：

+ 你不能使用互斥锁。
+ 等待 ISR 是不允许的；方法参数中的所有超时都必须设置为 0。
### ISR 的例子

此示例使用队列中的消息来触发中断。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_isr/file/40078e697304/main.cpp)                                                                                              
```
#include "mbed.h"
 
Thread thread;
Ticker ticker;
Queue<uint32_t, 5> queue;
DigitalOut myled(LED1);
 
void queue_isr() {
    queue.put((uint32_t*)2);
    myled = !myled;
}
 
void queue_thread() {
    while (true) {
        queue.put((uint32_t*)1);
        wait(1);
    }
}
 
int main (void) {
    thread.start(callback(queue_thread));
    ticker.attach(queue_isr, 1.0);
 
    while (true) {
        osEvent evt = queue.get();
        if (evt.status != osEventMessage) {
            printf("queue->get() returned %02x status\n\r", evt.status);
        } else {
            printf("queue->get() returned %d\n\r", evt.value.v);
        }
    }
}
```
