## Semaphore
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.png">

Semaphore 类层次结构</div>                                                                          

信号量管理对特定类型的共享资源池的线程访问。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Semaphore.png"></div>

## Semaphore 类参考
[rtos::Semaphore 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#a4b8ed761eacc1224603d7bd6dd95f62a" rel="nofollow" target="_blank">Semaphore</a> (int32_t count=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#a86039c3d5993b00a8c2cf20972e5faa6" rel="nofollow" target="_blank">Semaphore</a> (int32_t count, uint16_t max_count)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#a70fcb54c8a53508aef82cf8528d0f02c" rel="nofollow" target="_blank">wait</a> (uint32_t millisec=osWaitForever)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#a398a70a2d2126d55a3f2af8efd9143ad" rel="nofollow" target="_blank">wait_until</a> (uint64_t millisec)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#ad82e4bc6f4096bd8c465b3f288fccef4" rel="nofollow" target="_blank">release</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_semaphore.html#a47573340e5d0979f88ead8d63d36569c" rel="nofollow" target="_blank">~Semaphore</a> ()</td>
		</tr></tbody></table>

## Semaphore 示例
使用信号量来保护 printf()。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_semaphore/file/574f47121e8e/main.cpp)     
```
#include "mbed.h"
 
Semaphore two_slots(2);
Thread t2;
Thread t3;
    
void test_thread(void const *name) {
    while (true) {
        two_slots.wait();
        printf("%s\n\r", (const char*)name);
        wait(1);
        two_slots.release();
    }
}
 
int main (void) {
    t2.start(callback(test_thread, (void *)"Th 2"));
    t3.start(callback(test_thread, (void *)"Th 3"));
 
    test_thread((void *)"Th 1");
}
```