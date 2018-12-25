## I2C
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.png">

I2C 类层次结构</div>                                           

I2C 接口提供 I2C 主控功能。I2C 是双线串行协议，允许 I2C 主设备与 I2C 从设备交换数据。您可以使用它与 I2C 设备进行通信，例如串行存储器，传感器和其他模块或集成电路。

I2C 协议每条总线最多支持 127 个设备，其默认时钟频率为 100 KHz。

**注意**: 请记住，在 sda 和 scl 上需要一个上拉电阻。I2C 总线上的所有驱动器都需要是开路集电极，因此必须在两个信号上使用上拉电阻。上拉电阻的典型值约为 2.2 k 欧姆，连接在引脚和 3v3 之间。

## I2C 类参考
**注意**: Arm Mbed API 使用 8 位地址，因此请确保在传递它们之前将 7 位地址左移 1 位。

[mbed::I2C 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;"><a id="a73914ba935abc8250120fd46950513aa" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>RxStatus</strong> { <strong>NoData</strong>, <strong>MasterGeneralCall</strong>, <strong>MasterWrite</strong>, <strong>MasterRead</strong> }</td>
		</tr><tr><td style="vertical-align:top;"><a id="a8eed34076cd0a83c62b0693bbb732c4d" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Acknowledge</strong> { <strong>NoACK</strong> = 0, <strong>ACK</strong> = 1 }</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#af0cadf24338d4a5dca5a9ee6d1d00b49" rel="nofollow" target="_blank">I2C</a> (PinName sda, PinName scl)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a46b21f291c3a07391d8beba7c1627726" rel="nofollow" target="_blank">frequency</a> (int hz)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a7c70e76c7d845a9566e8d5899aca7fc5" rel="nofollow" target="_blank">read</a> (int address, char *data, int length, bool repeated=false)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#add3bb9ee03b9c5812f239735f8343383" rel="nofollow" target="_blank">read</a> (int ack)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a98ec0213fcdae0d382dac08719b6bdcc" rel="nofollow" target="_blank">write</a> (int address, const char *data, int length, bool repeated=false)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a3d1fc5585e3e6a4a72c324f504674e0d" rel="nofollow" target="_blank">write</a> (int data)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a63ce50d8344861db364b6058c9792537" rel="nofollow" target="_blank">start</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#ac08c87c12aaa2fdb56065c631987f5d6" rel="nofollow" target="_blank">stop</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#aacb927244b8f6b08b5ef9d35e14faded" rel="nofollow" target="_blank">lock</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#af6698273ff28cd6a4cb6c7de65846f21" rel="nofollow" target="_blank">unlock</a> (void)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a12491b48831e59753bdd9ad0a70ffaef" rel="nofollow" target="_blank">transfer</a> (int address, const char *tx_buffer, int tx_length, char *rx_buffer, int rx_length, const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a> &amp;callback, int event=I2C_EVENT_TRANSFER_COMPLETE, bool repeated=false)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#ab97729d4efdb208a431bba7b9c3b8c64" rel="nofollow" target="_blank">abort_transfer</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#af4b7bbf9e5435bc27efd5f9716afcb1f" rel="nofollow" target="_blank">lock_deep_sleep</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html#a67760683768595ee165c921b8f2d9ae9" rel="nofollow" target="_blank">unlock_deep_sleep</a> ()</td>
		</tr><tr><td style="vertical-align:top;"><a id="aee3339c029cf4642a655011501c66aef" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>irq_handler_asynch</strong> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="aebdf3a847eb8deec075e87df4957860f" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>aquire</strong> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a398b0af7e144ca32f63f4fab65c06eb4" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">event_callback_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_callback</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="abcc9bcd2afbfa3839c9e7cd40f4fbb40" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_c_thunk.html" rel="nofollow" target="_blank">CThunk</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html" rel="nofollow" target="_blank">I2C</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_irq</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7e607f1f7e4ecfd394568ddeb8a73571" target="_blank"></a> DMAUsage&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_usage</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aaf5e188aea1f2bbc2ae9bd1e18373624" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_deep_sleep_locked</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7541663e21d70d244319d07fccb9007f" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structi2c__t.html" rel="nofollow" target="_blank">i2c_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_i2c</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="acf7137540833bd4db825a680abf77a20" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_hz</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态保护属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="aa815c6372fb6ec57500bfd561691acce" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_i2_c.html" rel="nofollow" target="_blank">I2C</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_owner</strong> = NULL</td>
		</tr><tr><td style="vertical-align:top;"><a id="ad813b1cec04f84a4386506cfa14be835" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_singleton_ptr.html" rel="nofollow" target="_blank">SingletonPtr</a>&lt; <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_platform_mutex.html" rel="nofollow" target="_blank">PlatformMutex</a> &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_mutex</strong></td>
		</tr></tbody></table>

## I2C hello, world
[main.cpp](https://os.mbed.com/teams/mbed_example/code/I2C_HelloWorld/file/fa13d56ff9ff/main.cpp)     
```
/* mbed Example Program
 * Copyright (c) 2006-2014 ARM Limited
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#include "mbed.h"
 
// Read temperature from LM75BD
 
I2C i2c(I2C_SDA , I2C_SCL ); 
 
const int addr7bit = 0x48;      // 7 bit I2C address
const int addr8bit = 0x48 << 1; // 8bit I2C address, 0x90
 
int main() {
    char cmd[2];
    while (1) {
        cmd[0] = 0x01;
        cmd[1] = 0x00;
        i2c.write(addr8bit, cmd, 2);
 
        wait(0.5);
 
        cmd[0] = 0x00;
        i2c.write(addr8bit, cmd, 1);
        i2c.read( addr8bit, cmd, 2);
 
        float tmp = (float((cmd[0]<<8)|cmd[1]) / 256.0);
        printf("Temp = %.2f\n", tmp);
    }
}
```