## MemoryPool
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.png">

MemoryPool 类层次结构</div>                                                           
您可以使用 MemoryPool 类来定义和管理固定大小的内存池。您可以使用 alloc 或 calloc 方法从池中分配固定大小的内存块，如果池中没有可用空间，则返回指向内存块的指针或 NULL。用户有责任初始化块中放置的对象。calloc 函数在将块的指针返回给调用者之前将内存块设置为零。

## MemoryPool 类参考
[rtos::MemoryPool< T, pool_sz > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html#a9e4dcde12d2da15b809140847263a167" rel="nofollow" target="_blank">MemoryPool</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html#ab4f6cabffa3c2a5c21910d0fd9e4f61c" rel="nofollow" target="_blank">~MemoryPool</a> ()</td>
		</tr><tr><td style="vertical-align:top;">T *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html#a1442610d3be1ecfc3c65d74deb4da2e7" rel="nofollow" target="_blank">alloc</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">T *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html#a70e4472ccd1507f18978013a5736451c" rel="nofollow" target="_blank">calloc</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_memory_pool.html#af07d428ec2823d4a2a349865db299dc1" rel="nofollow" target="_blank">free</a> (T *block)</td>
		</tr></tbody></table>

## MemoryPool 示例
```
MemoryPool<message_t, 16> mpool;
 
message_t *message = mpool.alloc();
 
mpool.free(message);
```
## Queue 和 MemoryPool 示例
此示例显示 Queue 和 MemoryPool 管理测量。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_queue/file/0cb43a362538/main.cpp)         
```
#include "mbed.h"
 
typedef struct {
    float    voltage;   /* AD result of measured voltage */
    float    current;   /* AD result of measured current */
    uint32_t counter;   /* A counter value               */
} message_t;
 
MemoryPool<message_t, 16> mpool;
Queue<message_t, 16> queue;
Thread thread;
 
/* Send Thread */
void send_thread (void) {
    uint32_t i = 0;
    while (true) {
        i++; // fake data update
        message_t *message = mpool.alloc();
        message->voltage = (i * 0.1) * 33; 
        message->current = (i * 0.1) * 11;
        message->counter = i;
        queue.put(message);
        wait(1);
    }
}
 
int main (void) {
    thread.start(callback(send_thread));
    
    while (true) {
        osEvent evt = queue.get();
        if (evt.status == osEventMessage) {
            message_t *message = (message_t*)evt.value.p;
            printf("\nVoltage: %.2f V\n\r"   , message->voltage);
            printf("Current: %.2f A\n\r"     , message->current);
            printf("Number of cycles: %u\n\r", message->counter);
            
            mpool.free(message);
        }
    }
}
```