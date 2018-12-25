## ATCmdParser
<div align=center><img title="ATCmdParser 类层次结构" src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.png">

ATCmdParser 类层次结构</div>

ATCmdParser 是一个兼容 Mbed OS 的 AT 命令解析器和序列化器。AT 命令是用于与诸如调制解调器，电话或 Wi-Fi 模块之类的通信设备通信的指令。每个命令都是 ASCII 格式的文本字符串，每个命令都以 “AT” 字符开头，后跟一个指定要执行的操作的命令。

Mbed OS 中的 ATCmdParser 类实现了向能够使用 AT 命令进行通信的设备发送和接收 AT 命令的功能。ATCmdParser 在内部使用通信通道的驱动程序与设备通信。它希望驱动程序实现 FileHandle 接口以调用驱动程序上的函数。

例如，UARTSerial 通信驱动程序实现 FileHandle 接口，您可以将其与 ATCmdParser 一起用于向通过 UART 连接的设备发送和接收 AT 命令。ATCmdParser 还执行 AT 命令解析，它验证数据格式并分离 AT 事务的命令和数据部分。实际的命令集和使用的 AT 命令的格式取决于所使用的通信设备。您正在与之通信的设备的供应商指定此命令集和格式。

要使用 ATCmdParser，创建 ATCmdParser 对象的实体会将实现 FileHandle 接口的对象的引用作为参数传递给 ATCmdParser 构造函数。ATCmdParser 还支持配置特定的输出分隔符字符序列，具体取决于连接到通信接口的接口或设备。

## ATCmdParser 类参考

[mbed::ATCmdParser 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#ac356160a5b9f7071993c98fd634ae85b" rel="nofollow" target="_blank">ATCmdParser</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html" rel="nofollow" target="_blank">FileHandle</a> *fh, const char *output_delimiter="\r", int buffer_size=256, int timeout=8000, bool debug=false)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a6c13a71ca63ad6e85dac0c9c3ddafceb" rel="nofollow" target="_blank">~ATCmdParser</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a5793dc3e465ea1d75900fd39cd521a39" rel="nofollow" target="_blank">set_timeout</a> (int timeout)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#aa6f75c5412af6ec0f32ec37a47fe0141" rel="nofollow" target="_blank">setTimeout</a> (int timeout)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a161f45bc303b531bf244649d3dc2abf7" rel="nofollow" target="_blank">set_delimiter</a> (const char *output_delimiter)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#ac62403dd25cd69c0313ef0dcf469d733" rel="nofollow" target="_blank">setDelimiter</a> (const char *output_delimiter)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#af52940b44048cabaf4a9dd57a3b7e8d2" rel="nofollow" target="_blank">debug_on</a> (uint8_t on)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#ab0caafded88c752969c1885e919ce710" rel="nofollow" target="_blank">debugOn</a> (uint8_t on)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a1840d783ca5a932ae3a63e2b24083068" rel="nofollow" target="_blank">send</a> (const char *command,...) MBED_PRINTF_METHOD(1</td>
		</tr><tr><td style="vertical-align:top;"><a id="ad439cb8be709b3ba75a0894025290524" target="_blank"></a> bool bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vsend</strong> (const char *command, va_list args)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#ae1423ae3220c4f33ce68d0048d84805b" rel="nofollow" target="_blank">recv</a> (const char *response,...) MBED_SCANF_METHOD(1</td>
		</tr><tr><td style="vertical-align:top;"><a id="a0483ca6634e0749fe8c327f0c1c08d27" target="_blank"></a> bool bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vrecv</strong> (const char *response, va_list args)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a7413fde82d92056db6ab15500ed06eba" rel="nofollow" target="_blank">putc</a> (char c)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#af9624e0d8bedd2fd9c44969676298a86" rel="nofollow" target="_blank">getc</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#af18e22e7f2ef71c7085dca69e9514d71" rel="nofollow" target="_blank">write</a> (const char *data, int size)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a0c94fc00011f581b123b9f7a1f957a4a" rel="nofollow" target="_blank">read</a> (char *data, int size)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a62745f65942fa900f8db942c41d71eb2" rel="nofollow" target="_blank">printf</a> (const char *format,...) MBED_PRINTF_METHOD(1</td>
		</tr><tr><td style="vertical-align:top;"><a id="ac213f5a5a9ee6e3d2aa8db665a407ce0" target="_blank"></a> int int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vprintf</strong> (const char *format, va_list args)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#adacc05f03d8cbd5525c2ee6bb7c4b2cc" rel="nofollow" target="_blank">scanf</a> (const char *format,...) MBED_SCANF_METHOD(1</td>
		</tr><tr><td style="vertical-align:top;"><a id="a551ffc2d5b690a6d8a8db2fad836873e" target="_blank"></a> int int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>vscanf</strong> (const char *format, va_list args)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#aa56612d840083453e15c9783a6432edf" rel="nofollow" target="_blank">oob</a> (const char *prefix, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt; func)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a08ba24d981217ba5cbb5ec3b2f6d570a" rel="nofollow" target="_blank">flush</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#ab8262849789f2048670a846d229da2da" rel="nofollow" target="_blank">abort</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_a_t_cmd_parser.html#a0853ff207329997afe958d984aa98dcd" rel="nofollow" target="_blank">process_oob</a> (void)</td>
		</tr></tbody></table>

## ATCmdParser 示例

### 示例 1

[main.cpp](https://github.com/ARMmbed/mbed-os-example-atcmdparser/blob/master/main.cpp)               
```
/* ATCmdParser usage example
 * Copyright (c) 2016 ARM Limited
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
#include "platform\ATCmdParser.h"
#include "drivers\UARTSerial.h"
 
#define   ESP8266_DEFAULT_BAUD_RATE   115200
 
UARTSerial *_serial;
ATCmdParser *_parser;
 
int main()
{
    printf("\nATCmdParser with ESP8266 example");
    
    _serial = new UARTSerial(D1, D0, ESP8266_DEFAULT_BAUD_RATE);
    _parser = new ATCmdParser(_serial);
    _parser->debug_on( 1 );
    _parser->set_delimiter( "\r\n" );
    
    //Now get the FW version number of ESP8266 by sending an AT command 
    printf("\nATCmdParser: Retrieving FW version");
    _parser->send("AT+GMR");
    int version;
    if(_parser->recv("SDK version:%d", &version) && _parser->recv("OK")) {
        printf("\nATCmdParser: FW version: %d", version);
        printf("\nATCmdParser: Retrieving FW version success");
    } else { 
        printf("\nATCmdParser: Retrieving FW version failed");
        return -1;
    }
    
    printf("\nReset ESP8266 WiFi module");
    for (int i = 0; i < 2; i++) {
        if (_parser->send("AT+RST")
            && _parser->recv("OK\r\nready")) {
            printf("\nATCmdParser: Reseting ESP8266 success");
        } else {
            printf("\nATCmdParser: Reseting ESP8266 failure");
        }
    }
    
    printf("\nStarting-up ESP8266");
    bool success = _parser->send("AT+CWMODE_CUR=%d", 1)
        && _parser->recv("OK")
        && _parser->send("AT+CIPMUX=1")
        && _parser->recv("OK");
    if( success ) {
        printf("\nATCmdParser: Starting-up ESP8266 success");
    } else {
        printf("\nATCmdParser: Starting-up ESP8266 failure");
    }      
 
    printf("\nScan for WiFi networks");
    unsigned cnt = 0;
    unsigned sec = 0;
    unsigned scan_limit = 5;
    nsapi_wifi_ap_t ap;
    bool ret = true;
    
    if (!_parser->send("AT+CWLAP")) {
        printf("\nScan for WiFi networks failed");
    }
 
    do
    {
        ret = _parser->recv("+CWLAP:(%d,\"%32[^\"]\",%hhd,\"%hhx:%hhx:%hhx:%hhx:%hhx:%hhx\",%d", 
                            &sec, 
                            ap.ssid,
                            &ap.rssi, 
                            &ap.bssid[0], 
                            &ap.bssid[1], 
                            &ap.bssid[2], 
                            &ap.bssid[3], 
                            &ap.bssid[4],
                            &ap.bssid[5], 
                            &ap.channel);
        
 
        printf("\nSSID: %s", ap.ssid );
        cnt++;
        if (cnt >= scan_limit) {
            break;
        }
    } while(ret);
    
    printf("\nDone\n");
}
```
### 示例 2

您可以在 ESP8266 设备的 Wi-Fi 驱动程序实现中找到另一个真实示例。ESP8266 是一个 Wi-Fi 模块，您可以通过 UART 连接到 SoC 以获得 Wi-Fi 支持。
<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/atcmdparser_esp8266.png">
</div>
上图显示了 ESP8266 Wifi 驱动程序如何使用 ATCmdParser 与 ESP8266 设备进行通信。