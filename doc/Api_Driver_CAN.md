## CAN
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.png">

CAN 类层次结构</div>                                           

控制器局域网（CAN）是一种总线标准，允许微控制器和设备相互通信而无需通过主机。

**注意**: 您可以使用 CAN 接口从 CAN 端口写入数据字。它将返回从另一个 CAN 设备接收的数据。您可以配置 CAN 时钟频率。

## CAN 类参考
[mbed::CAN 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;"><a id="a1a36ffd5f523cd0824c30c9609093a0d" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Mode</strong> {<br>
			&nbsp;&nbsp;<strong>Reset</strong> = 0, <strong>Normal</strong>, <strong>Silent</strong>, <strong>LocalTest</strong>,<br>
			&nbsp;&nbsp;<strong>GlobalTest</strong>, <strong>SilentTest</strong><br>
			}</td>
		</tr><tr><td style="vertical-align:top;"><a id="aaceaa04ed523e82d9fe734fbba5033e2" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>IrqType</strong> {<br>
			&nbsp;&nbsp;<strong>RxIrq</strong> = 0, <strong>TxIrq</strong>, <strong>EwIrq</strong>, <strong>DoIrq</strong>,<br>
			&nbsp;&nbsp;<strong>WuIrq</strong>, <strong>EpIrq</strong>, <strong>AlIrq</strong>, <strong>BeIrq</strong>,<br>
			&nbsp;&nbsp;<strong>IdIrq</strong>, <strong>IrqCnt</strong><br>
			}</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a651a3e5049e9f2d3c24eab460dc24513" rel="nofollow" target="_blank">CAN</a> (PinName rd, PinName td)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#ab5183323fda8947fa1c5cf3e7d0efc25" rel="nofollow" target="_blank">CAN</a> (PinName rd, PinName td, int hz)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#ac3434cbb810c572b144c8fc097f3e3ad" rel="nofollow" target="_blank">frequency</a> (int hz)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a71ef2b1327a45e610856629d3771095b" rel="nofollow" target="_blank">write</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n_message.html" rel="nofollow" target="_blank">CANMessage</a> msg)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a914b2167247583cd42944e843cf331b3" rel="nofollow" target="_blank">read</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n_message.html" rel="nofollow" target="_blank">CANMessage</a> &amp;msg, int handle=0)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#afd906df662cfb272e4f76b55ba94614f" rel="nofollow" target="_blank">reset</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a5667d0867051851b9df057bc09509eee" rel="nofollow" target="_blank">monitor</a> (bool silent)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#aaec59a2dc3025d140b88f677893f9dcc" rel="nofollow" target="_blank">mode</a> (Mode mode)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#af8814d5b27d57b94dc1c5db4ee65f00b" rel="nofollow" target="_blank">filter</a> (unsigned int id, unsigned int mask, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__hal.html#ga3728669b02b962d5e84c37d4587189b2" rel="nofollow" target="_blank">CANFormat</a> format=CANAny, int handle=0)</td>
		</tr><tr><td style="vertical-align:top;">unsigned char&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#afd1b1a1e9623a1b3841dd56738731785" rel="nofollow" target="_blank">rderror</a> ()</td>
		</tr><tr><td style="vertical-align:top;">unsigned char&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a6e85192034f2b62000d7b41692bb63dd" rel="nofollow" target="_blank">tderror</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a82e211ed441245d7fa52a9608f4ca5b6" rel="nofollow" target="_blank">attach</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt; func, IrqType type=RxIrq)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a705014aa06484edfb7dfd4f3349996ac" rel="nofollow" target="_blank">attach</a> (T *obj, void(T::*method)(), IrqType type=RxIrq)</td>
		</tr><tr><td colspan="2">template&lt;typename T &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_c_a_n.html#a2780b131a9140f2ff1a31cd9c71b49bb" rel="nofollow" target="_blank">attach</a> (T *obj, void(*method)(T *), IrqType type=RxIrq)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="a87704ea69b38fd9ef0bb1b2c8c0dfcc7" target="_blank"></a> static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq_handler</strong> (uint32_t id, CanIrqType type)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;"><a id="a8f2a442afe3ec2a00da08c384d149f52" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lock</strong> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="abc7e5d2ea722958ad90fea09efd5f94d" target="_blank"></a> virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>unlock</strong> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a50af27616bb778bcf47da02edbf1be8c" target="_blank"></a> can_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_can</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a72eb9145442520d209489c883e7438c7" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq</strong> [IrqCnt]</td>
		</tr><tr><td style="vertical-align:top;"><a id="a8acc89d33b9615e86071b62651d4bb5c" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## CAN Hello World!
此示例从一个 CAN 总线（can1）发送计数器，并在另一个 CAN 总线（can2）上侦听数据包。每个总线控制器应连接到 CAN 总线收发器。这些应该通过 CAN 总线连接在一起。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/CAN_ex_1/file/5791101761f9/main.cpp)           
```
#include "mbed.h"
 
Ticker ticker;
DigitalOut led1(LED1);
DigitalOut led2(LED2);
CAN can1(MBED_CONF_APP_CAN1_RD, MBED_CONF_APP_CAN1_TD);
CAN can2(MBED_CONF_APP_CAN2_RD, MBED_CONF_APP_CAN2_TD);
char counter = 0;
 
void send() {
    printf("send()\n");
    if(can1.write(CANMessage(1337, &counter, 1))) {
        printf("wloop()\n");
        counter++;
        printf("Message sent: %d\n", counter);
    } 
    led1 = !led1;
}
 
int main() {
    printf("main()\n");
    ticker.attach(&send, 1);
    CANMessage msg;
    while(1) {
        printf("loop()\n");
        if(can2.read(msg)) {
            printf("Message received: %d\n", msg.data[0]);
            led2 = !led2;
        } 
        wait(0.2);
    }
}
```