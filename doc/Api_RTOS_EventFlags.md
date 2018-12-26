## EventFlags

<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.png">

EventFlags 类层次结构</div>                                                           
EventFlags 类提供了一种设置和等待特定条件的机制。它提供了一种通知其他线程有关条件或事件的通用方法。您可以将 EventFlags 类的每个实例视为事件通道。每个活动有 31 种不同的标志。

## EventFlag 类参考
[rtos::EventFlags 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html)
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a32dea6c492e93250732e01606d3b7d63" rel="nofollow" target="_blank">EventFlags</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#ac81b3d9a567099db37e14a10b78776b2" rel="nofollow" target="_blank">EventFlags</a> (const char *name)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a9e029fe0bf4613d9e80eab210431ee98" rel="nofollow" target="_blank">set</a> (uint32_t flags)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a0d9c4c3212ce8b30f5b1bccce6a6cc2d" rel="nofollow" target="_blank">clear</a> (uint32_t flags=0x7fffffff)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a0182a8d6fa978ffbbd9b23d08bcd0a14" rel="nofollow" target="_blank">get</a> () const</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a102f2801e08ce07c3ae6a416349b72c4" rel="nofollow" target="_blank">wait_all</a> (uint32_t flags=0, uint32_t timeout=osWaitForever, bool <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a0d9c4c3212ce8b30f5b1bccce6a6cc2d" rel="nofollow" target="_blank">clear</a>=true)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a1542784f0aafdd4bd83432defb8df7c5" rel="nofollow" target="_blank">wait_any</a> (uint32_t flags=0, uint32_t timeout=osWaitForever, bool <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#a0d9c4c3212ce8b30f5b1bccce6a6cc2d" rel="nofollow" target="_blank">clear</a>=true)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_event_flags.html#aaf7e9d0f09afd08441ba5e5d9b6f368c" rel="nofollow" target="_blank">~EventFlags</a> ()</td>
		</tr></tbody></table>

## EventFlags 示例
下面是 EventFlags 用法的示例，其中一个线程每 1 秒生成事件，第二个线程正在等待事件并执行某些操作。

```
#include "mbed.h"
 
EventFlags event;
 
void worker_f()
{
    while (true) {
        event.wait_all(0x1);
 
        printf("Got signal!\r\n");
    }
}
 
int main()
{
    Thread worker;
 
    worker.start(callback(worker_f));
 
    while (true) {
        wait(1);
        event.set(0x1);
    }
}
```