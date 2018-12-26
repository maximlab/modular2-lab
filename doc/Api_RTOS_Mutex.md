Mutex
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.png">

Mutex 类层次结构</div>                                                                          

Mutex 用于同步线程的执行，例如，以保护对共享资源的访问。

**注意**: 无法从中断服务例程（ISR）调用 Mutex 方法。在当前版本的 Mbed OS 中，如果您尝试在 ISR 中使用互斥锁，则不会发生任何事情；无论锁实际上是否空闲，尝试锁定互斥锁都会立即成功。换句话说，如果在 ISR 中获得互斥锁，则可以破坏线程安全机制并将竞争条件引入其他安全的代码段。未来版本的 Mbed OS 将提供警告并最终防止这种情况发生。

<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Mutex.png"></div>  
**注意**: 对于所有驱动程序，Mbed OS 使用 PlatformMutex 类而不是 RTOS 互斥锁。

## Mutex 类参考
[rtos::Mutex 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#a687eb3bc015fe6bd781fddd67b268f7e" rel="nofollow" target="_blank">Mutex</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#a903b3421e6187007115e2f8bb2815f16" rel="nofollow" target="_blank">Mutex</a> (const char *name)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#ae6211ae2a49d7f895f6a17ede7255ae8" rel="nofollow" target="_blank">lock</a> (uint32_t millisec=osWaitForever)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#acbec30fd47cba290337fa35d042dffb7" rel="nofollow" target="_blank">trylock</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#a24258eaac46af8d80e51b8b7181fd9eb" rel="nofollow" target="_blank">trylock_for</a> (uint32_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#ab6c45ffe55ecf0f392e0f301b8eefb4b" rel="nofollow" target="_blank">trylock_until</a> (uint64_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#afc703e66bd0a9ca484e4584c4154a254" rel="nofollow" target="_blank">unlock</a> ()</td>
		</tr><tr><td style="vertical-align:top;">osThreadId&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#a82befa06b53cbc3e8393a06db274f470" rel="nofollow" target="_blank">get_owner</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mutex.html#a750d79fb84d3f7ccde929e43a2b66025" rel="nofollow" target="_blank">~Mutex</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">友元</td>
		</tr><tr><td style="vertical-align:top;"><a id="ab270e49e575fdf0fe1a4f2ee911df116" target="_blank"></a> class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>ConditionVariable</strong></td>
		</tr></tbody></table>

## Mutex 示例
使用 Mutex 保护 printf()。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_mutex/file/1ae0d86d2020/main.cpp)         
```
#include "mbed.h"
 
Mutex stdio_mutex;
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
**注意**: C 标准库互斥体
Arm C 标准库已经具有互斥锁以保护对 stdio 的访问，因此在 LPC1768 上不需要上述示例。另一方面，LPC11U24 不提供默认的 stdio Mutexes，因此上述示例是必需的。

**注意**: 由于 Arm C 标准库中的互斥锁，您不能在 ISR 中使用 stdio（printf，putc，getc 等），malloc 和 new。