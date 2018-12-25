## PortIn
使用 PortIn 接口将基础 GPIO 端口读取为一个值。这比 BusIn 快得多，因为您可以一次读取端口，但由于受到底层 GPIO 端口的端口和位布局的限制，它的灵活性要低得多。

可以提供掩码，因此只使用端口的某些位，允许其他位用于其他接口。

## PortIn 类参考
[mbed::PortIn 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in.html#ab712a09c4c03de0489003b9d47739f61" rel="nofollow" target="_blank">PortIn</a> (PortName port, int mask=0xFFFFFFFF)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in.html#a88de11041a1e58635668620c9479c721" rel="nofollow" target="_blank">read</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in.html#a2ebbdc8ef49cf9a1a3a83dd66e3f257b" rel="nofollow" target="_blank">mode</a> (PinMode mode)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_port_in.html#a651a76c20ae749b73287e7480d0ceccb" rel="nofollow" target="_blank">operator int</a> ()</td>
		</tr></tbody></table>

## PortIn hello, world
[main.cpp](https://os.mbed.com/users/mbed_official/code/PortIn_HelloWorld/file/92064442fd12/main.cpp) 
```
// Switch on an LED if any of mbed pins 21-26 is high
 
#include "mbed.h"
 
PortIn     p(Port2, 0x0000003F);   // p21-p26
DigitalOut ind(LED4);
 
int main() {
    while(1) {
        int pins = p.read();
        if(pins) {
            ind = 1;
        } else {
            ind = 0;
        }
    }
}
```
相关内容

[BusIn](https://os.mbed.com/docs/v5.9/reference/busin.html) API 参考。