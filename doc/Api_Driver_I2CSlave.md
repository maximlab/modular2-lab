## I2CSlave
使用 I2C Slave 与 I2C Master 通信。

同步级别：不受保护。

## I2CSlave 类参考
[mbed::I2CSlave 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;"><a id="acf62d5f8023e5c32a226e4ddae7e7b12" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>RxStatus</strong> { <strong>NoData</strong> = 0, <strong>ReadAddressed</strong> = 1, <strong>WriteGeneral</strong> = 2, <strong>WriteAddressed</strong> = 3 }</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a6ed38d25df68cbe3eb70618eb11c6c30" rel="nofollow" target="_blank">I2CSlave</a> (PinName sda, PinName scl)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#aa4c71862c2219dd0860e8f85703553f9" rel="nofollow" target="_blank">frequency</a> (int hz)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#ac51527a8644be7adff6c7797b554e2cc" rel="nofollow" target="_blank">receive</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#abb49e483f86c03886c26555cb04d3bdd" rel="nofollow" target="_blank">read</a> (char *data, int length)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a9d46cd876f8416ecd970e8379a57525e" rel="nofollow" target="_blank">read</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a4dbd1349382b04a9678420e8400afa4e" rel="nofollow" target="_blank">write</a> (const char *data, int length)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a2d7703d64fbc55dda5fc50eace35e285" rel="nofollow" target="_blank">write</a> (int data)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a3031afac87b8a413e0efa8767e1555e3" rel="nofollow" target="_blank">address</a> (int address)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c_slave.html#a24f9f7038718fbff364d2fa26b1ae0c8" rel="nofollow" target="_blank">stop</a> (void)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a057b0165c6d83301716a427abf2dcf58" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structi2c__t.html" rel="nofollow" target="_blank">i2c_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_i2c</strong></td>
		</tr></tbody></table>
        
## I2CSlave 示例
尝试此示例以查看 I2C 响应器的工作原理。

```
#include <mbed.h>
 
I2CSlave slave(p9, p10);
 
int main() {
   char buf[10];
   char msg[] = "Slave!";
 
   slave.address(0xA0);
   while (1) {
       int i = slave.receive();
       switch (i) {
           case I2CSlave::ReadAddressed:
               slave.write(msg, strlen(msg) + 1); // Includes null char
               break;
           case I2CSlave::WriteGeneral:
               slave.read(buf, 10);
               printf("Read G: %s\n", buf);
               break;
           case I2CSlave::WriteAddressed:
               slave.read(buf, 10);
               printf("Read A: %s\n", buf);
               break;
       }
       for(int i = 0; i < 10; i++) buf[i] = 0;    // Clear buffer
   }
}
```