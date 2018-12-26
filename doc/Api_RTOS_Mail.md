## Mail
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.png">

Mail 类层次结构</div>                                                           
Mail 的工作方式类似于队列，还有一个额外的好处，即提供用于分配消息的内存池（不仅仅是指针）。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/mail_queue.png"></div>

## Mail 类参考
[rtos::Mail< T, queue_sz > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#a6d7afe8863d77860db1e754d4452c179" rel="nofollow" target="_blank">Mail</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#adaff7f3d4951ad98585a26bbb12046bd" rel="nofollow" target="_blank">empty</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#a34b602f46adb865fe9eb13fd37bff545" rel="nofollow" target="_blank">full</a> () const</td>
		</tr><tr><td style="vertical-align:top;">T *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#a4391e4794a76521c0d85823d16635576" rel="nofollow" target="_blank">alloc</a> (uint32_t millisec=0)</td>
		</tr><tr><td style="vertical-align:top;">T *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#a019c41d4d10fd2b23551ac3af5defb58" rel="nofollow" target="_blank">calloc</a> (uint32_t millisec=0)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#ac73e0340e539f9445facf40918a1d470" rel="nofollow" target="_blank">put</a> (T *mptr)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structos_event.html" rel="nofollow" target="_blank">osEvent</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#a621818c3f7dd79c9739ec7f5433864c0" rel="nofollow" target="_blank">get</a> (uint32_t millisec=osWaitForever)</td>
		</tr><tr><td style="vertical-align:top;">osStatus&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classrtos_1_1_mail.html#ab827827b9e99b418db2dca678d91c1b6" rel="nofollow" target="_blank">free</a> (T *mptr)</td>
		</tr></tbody></table>

## Mail 示例
此代码使用邮件来管理度量。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_mail/file/6602f2907ac5/main.cpp)                                                                                                               
```
#include "mbed.h"
 
/* Mail */
typedef struct {
  float    voltage; /* AD result of measured voltage */
  float    current; /* AD result of measured current */
  uint32_t counter; /* A counter value               */
} mail_t;
 
Mail<mail_t, 16> mail_box;
Thread thread;
 
void send_thread (void) {
    uint32_t i = 0;
    while (true) {
        i++; // fake data update
        mail_t *mail = mail_box.alloc();
        mail->voltage = (i * 0.1) * 33; 
        mail->current = (i * 0.1) * 11;
        mail->counter = i;
        mail_box.put(mail);
        wait(1);
    }
}
 
int main (void) {
    thread.start(callback(send_thread));
    
    while (true) {
        osEvent evt = mail_box.get();
        if (evt.status == osEventMail) {
            mail_t *mail = (mail_t*)evt.value.p;
            printf("\nVoltage: %.2f V\n\r"   , mail->voltage);
            printf("Current: %.2f A\n\r"     , mail->current);
            printf("Number of cycles: %u\n\r", mail->counter);
            
            mail_box.free(mail);
        }
    }
}
```