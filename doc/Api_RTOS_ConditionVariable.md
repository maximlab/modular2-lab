## ConditionVariable

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_condition_variable.png">

ConditionVariable 类层次结构</div>                                                           
ConditionVariable 类提供了一种安全等待或发出状态更改信号的机制。编写多线程代码时的常见情况是使用互斥锁保护共享资源，然后释放该互斥锁以等待更改该数据。如果您不小心这样做，这可能会导致代码中的竞争条件。条件变量通过处理等待状态更改以及在此等待期间自动释放和获取互斥锁来提供此问题的安全解决方案。请注意，您无法在 ISR 上下文中对条件变量进行等待或通知调用。与 EventFlags 不同，ConditionVariable 不允许您同时等待多个事件。

## ConditionVariable 类参考
[rtos::ConditionVariable 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_condition_variable.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#gad68bc69879781ff39afb1af87bdfe7ed" rel="nofollow" target="_blank">ConditionVariable</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html" rel="nofollow" target="_blank">Mutex</a> &amp;mutex)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga4ec3fd7ec3509ddd2b94045fd14af424" rel="nofollow" target="_blank">wait</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga45d2a5ac078fc53f7b271ea657746cb9" rel="nofollow" target="_blank">wait_until</a> (uint64_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga16c9cbd0c071ccb661fdfc39939027cf" rel="nofollow" target="_blank">wait_for</a> (uint32_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga8104c8857b96e1f4e928e33989422226" rel="nofollow" target="_blank">notify_one</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga09306b738b0c094a5948a7d2532387a0" rel="nofollow" target="_blank">notify_all</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__rtos.html#ga7d6a3407a23b280baa078d0380327172" rel="nofollow" target="_blank">~ConditionVariable</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_add_wait_list</strong> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a> **wait_list, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a> *waiter)</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_remove_wait_list</strong> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a> **wait_list, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a> *waiter)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html" rel="nofollow" target="_blank">Mutex</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structrtos_1_1_condition_variable_1_1_waiter.html" rel="nofollow" target="_blank">Waiter</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_wait_list</strong></td>
		</tr></tbody></table>

## ConditionVariable 示例
下面是 ConditionVariable 用法的示例，其中一个线程每 1 秒生成事件，第二个线程正在等待事件并执行操作。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/ConditionVariable_Example_1/file/36d0e9449606/main.cpp)  
```
#include "mbed.h"
 
Mutex mutex;
ConditionVariable cond(mutex);
 
// These variables are protected by locking mutex
uint32_t count = 0;
bool done = false;
 
void worker_thread()
{
    mutex.lock();
    do {
        printf("Worker: Count %lu\r\n", count);
 
        // Wait for a condition to change
        cond.wait();
 
    } while (!done);
    printf("Worker: Exiting\r\n");
    mutex.unlock();
}
 
int main() {
    Thread thread;
    thread.start(worker_thread);
 
    for (int i = 0; i < 5; i++) {
 
        mutex.lock();
        // Change count and signal this
        count++;
        printf("Main: Set count to %lu\r\n", count);
        cond.notify_all();
        mutex.unlock();
 
        wait(1.0);
    }
 
    mutex.lock();
    // Change done and signal this
    done = true;
    printf("Main: Set done\r\n");
    cond.notify_all();
    mutex.unlock();
 
    thread.join();
}
```