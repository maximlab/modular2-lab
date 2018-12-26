## Queue
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.png">

Queue 类层次结构</div>                                                           
Queue 允许您将指向生产者线程的数据的指针排队到使用者线程。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/queue.png"></div>

## Queue 类参考
[rtos::Queue< T, queue_sz > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#a1c55b77eaad4c13bdbe49748d81eb239" rel="nofollow" target="_blank">Queue</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#ac100f30325f967672ebf382ae5204d5c" rel="nofollow" target="_blank">~Queue</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#a9c4486d808167680cf3882432cf31518" rel="nofollow" target="_blank">empty</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#ac962dfb660a26b61ea8331a89aa46ba4" rel="nofollow" target="_blank">full</a> () const</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#a8e5a81a42997445cfd66abc112b94fa0" rel="nofollow" target="_blank">put</a> (T *data, uint32_t millisec=0, uint8_t prio=0)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structos_event.html" rel="nofollow" target="_blank">osEvent</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_queue.html#aa3f8e33b32ec479c4ca40772dab09440" rel="nofollow" target="_blank">get</a> (uint32_t millisec=osWaitForever)</td>
		</tr></tbody></table>

## Queue 示例
```
Queue<message_t, 32> queue;
 
message_t *message;
 
queue.put(message);
 
osEvent evt = queue.get();
if (evt.status == osEventMessage) {
    message_t *message = (message_t*)evt.value.p;
```
## Queue 和 MemoryPool 示例
此示例显示 Queue 和 [MemoryPool](https://os.mbed.com/docs/v5.9/reference/memorypool.html) 管理测量。

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