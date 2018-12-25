## Thread
                                                                     
<div align=center><img title="Thread 类层次结构" src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_thread.png">

Thread 类层次结构</div>


Thread 类允许定义，创建和控制并行任务。

注意: 函数 main 是在系统初始化时启动的特殊线程函数。

## Thread 类参考

[rtos::Thread 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_thread.html)

|公共类型||
|-|:-|
|enum | 	State {  Inactive, Ready, Running, WaitingDelay,WaitingJoin, WaitingThreadFlag, WaitingEventFlag, WaitingMutex,WaitingSemaphore, WaitingMemoryPool, WaitingMessageGet,WaitingMessagePut,WaitingInterval, WaitingOr, WaitingAnd, WaitingMailbox,Deleted}|

|公共成员函数||
|-|:-|
|| 	Thread (osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL, const char *name=NULL)|
|| 	Thread (uint32_t tz_module, osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL, const char *name=NULL)|
|| 	Thread (mbed::Callback< void()> task, osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL)|
|template|\<typename T>|
|| 	Thread (T *argument, void(T::*task)(), osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL)|
|template|\<typename T>|
|| 	Thread (T *argument, void(*task)(T *), osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL)|
|| 	Thread (void(*task)(void const *argument), void *argument=NULL, osPriority priority=osPriorityNormal, uint32_t stack_size=OS_STACK_SIZE, unsigned char *stack_mem=NULL)|
|osStatus |	start (mbed::Callback< void()> task)|
|template |<typename T , typename M >|
|osStatus |	start (T *obj, M method)|
|osStatus |	join ()|
|osStatus |	terminate ()|
|osStatus |	set_priority (osPriority priority)|
|osPriority| 	get_priority ()|
|int32_t  |	signal_set (int32_t signals)|
|State |	get_state ()|
|uint32_t |	stack_size ()|
|uint32_t |	free_stack ()|
|uint32_t |	used_stack ()|
|uint32_t |	max_stack ()|
|const char *| 	get_name ()|
|virtual |	~Thread ()|

|静态公共成员函数||
|-|:-|
|static int32_t |	signal_clr (int32_t signals)|
|static osEvent |	signal_wait (int32_t signals, uint32_t millisec=osWaitForever)|
|static osStatus |	wait (uint32_t millisec)|
|static osStatus |	wait_until (uint64_t millisec)|
|static osStatus |	yield ()|
|static osThreadId |	gettid ()|
|static void |	attach_idle_hook (void(*fptr)(void))|
|static void |	attach_terminate_hook (void(*fptr)(osThreadId id))|
```
/// Priority values.
typedef enum {
  osPriorityNone          =  0,         ///< No priority (not initialized).
  osPriorityIdle          =  1,         ///< Reserved for Idle thread.
  osPriorityLow           =  8,         ///< Priority: low
  osPriorityLow1          =  8+1,       ///< Priority: low + 1
  osPriorityLow2          =  8+2,       ///< Priority: low + 2
  osPriorityLow3          =  8+3,       ///< Priority: low + 3
  osPriorityLow4          =  8+4,       ///< Priority: low + 4
  osPriorityLow5          =  8+5,       ///< Priority: low + 5
  osPriorityLow6          =  8+6,       ///< Priority: low + 6
  osPriorityLow7          =  8+7,       ///< Priority: low + 7
  osPriorityBelowNormal   = 16,         ///< Priority: below normal
  osPriorityBelowNormal1  = 16+1,       ///< Priority: below normal + 1
  osPriorityBelowNormal2  = 16+2,       ///< Priority: below normal + 2
  osPriorityBelowNormal3  = 16+3,       ///< Priority: below normal + 3
  osPriorityBelowNormal4  = 16+4,       ///< Priority: below normal + 4
  osPriorityBelowNormal5  = 16+5,       ///< Priority: below normal + 5
  osPriorityBelowNormal6  = 16+6,       ///< Priority: below normal + 6
  osPriorityBelowNormal7  = 16+7,       ///< Priority: below normal + 7
  osPriorityNormal        = 24,         ///< Priority: normal
  osPriorityNormal1       = 24+1,       ///< Priority: normal + 1
  osPriorityNormal2       = 24+2,       ///< Priority: normal + 2
  osPriorityNormal3       = 24+3,       ///< Priority: normal + 3
  osPriorityNormal4       = 24+4,       ///< Priority: normal + 4
  osPriorityNormal5       = 24+5,       ///< Priority: normal + 5
  osPriorityNormal6       = 24+6,       ///< Priority: normal + 6
  osPriorityNormal7       = 24+7,       ///< Priority: normal + 7
  osPriorityAboveNormal   = 32,         ///< Priority: above normal
  osPriorityAboveNormal1  = 32+1,       ///< Priority: above normal + 1
  osPriorityAboveNormal2  = 32+2,       ///< Priority: above normal + 2
  osPriorityAboveNormal3  = 32+3,       ///< Priority: above normal + 3
  osPriorityAboveNormal4  = 32+4,       ///< Priority: above normal + 4
  osPriorityAboveNormal5  = 32+5,       ///< Priority: above normal + 5
  osPriorityAboveNormal6  = 32+6,       ///< Priority: above normal + 6
  osPriorityAboveNormal7  = 32+7,       ///< Priority: above normal + 7
  osPriorityHigh          = 40,         ///< Priority: high
  osPriorityHigh1         = 40+1,       ///< Priority: high + 1
  osPriorityHigh2         = 40+2,       ///< Priority: high + 2
  osPriorityHigh3         = 40+3,       ///< Priority: high + 3
  osPriorityHigh4         = 40+4,       ///< Priority: high + 4
  osPriorityHigh5         = 40+5,       ///< Priority: high + 5
  osPriorityHigh6         = 40+6,       ///< Priority: high + 6
  osPriorityHigh7         = 40+7,       ///< Priority: high + 7
  osPriorityRealtime      = 48,         ///< Priority: realtime
  osPriorityRealtime1     = 48+1,       ///< Priority: realtime + 1
  osPriorityRealtime2     = 48+2,       ///< Priority: realtime + 2
  osPriorityRealtime3     = 48+3,       ///< Priority: realtime + 3
  osPriorityRealtime4     = 48+4,       ///< Priority: realtime + 4
  osPriorityRealtime5     = 48+5,       ///< Priority: realtime + 5
  osPriorityRealtime6     = 48+6,       ///< Priority: realtime + 6
  osPriorityRealtime7     = 48+7,       ///< Priority: realtime + 7
  osPriorityISR           = 56,         ///< Reserved for ISR deferred thread.
  osPriorityError         = -1,         ///< System cannot determine priority or illegal priority.
  osPriorityReserved      = 0x7FFFFFFF  ///< Prevents enum down-size compiler optimization.
} osPriority_t;
```
## Thread 示例

下面的代码使用两个单独的线程来闪烁两个 LED。第一个线程自动创建并执行 main 函数；第二个线程是在 main 中明确创建的。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_basic/file/dc33cd3f4eb9/main.cpp)                                                         
```
#include "mbed.h"
 
DigitalOut led1(LED1);
DigitalOut led2(LED2);
Thread thread;
 
void led2_thread() {
    while (true) {
        led2 = !led2;
        wait(1);
    }
}
 
int main() {
    thread.start(led2_thread);
    
    while (true) {
        led1 = !led1;
        wait(0.5);
    }
}
``` 
## Thread 回调示例

Callback API 提供了一种将参数传递给生成线程的便捷方法。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_threading_with_callback/file/d4b2a035ffe3/main.cpp)                                                                                                                                           
```
#include "mbed.h"
 
Thread thread;
DigitalOut led1(LED1);
volatile bool running = true;
 
// Blink function toggles the led in a long running loop
void blink(DigitalOut *led) {
    while (running) {
        *led = !*led;
        wait(1);
    }
}
 
// Spawns a thread to run blink for 5 seconds
int main() {
    thread.start(callback(blink, &led1));
    wait(5);
    running = false;
    thread.join();
}
```