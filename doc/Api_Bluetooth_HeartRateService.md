## iBeacon
iBeacon 是一种基于 BLE 的 Apple 技术，可用作室内定位系统。它允许 iOS 应用程序跟踪用户是否进入特定区域并提供用户上下文的操作和通知。

iBeacon 类构建模仿 iBeacon 的广告有效载荷并将其分配给给定的 BLE 接口。

**警告**: 要制造 iBeacons，您必须从 Apple 获得许可。有关更多信息，请访问 [Apple 的网站](https://developer.apple.com/ibeacon/)。许可证还授予对 iBeacon 技术规范的访问权限。

## iBeacon 类参考
[iBeacon 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classi_beacon.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">union &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/unioni_beacon_1_1_payload.html" rel="nofollow" target="_blank">Payload</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">typedef const uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classi_beacon.html#aaddf66b28c749992ee6b0ceb7799e1b0" rel="nofollow" target="_blank">LocationUUID_t</a>[16]</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classi_beacon.html#a33f8eb5b866fad6dbc066d9c6b231083" rel="nofollow" target="_blank">iBeacon</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;_ble, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classi_beacon.html#aaddf66b28c749992ee6b0ceb7799e1b0" rel="nofollow" target="_blank">LocationUUID_t</a> uuid, uint16_t majNum, uint16_t minNum, uint8_t txP=0xC8, uint16_t compID=0x004C)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a093758d4bb3db703b89edf8b3e79d5fe" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>ble</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aeb504a040a7830497c23ab6d0061b221" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/unioni_beacon_1_1_payload.html" rel="nofollow" target="_blank">Payload</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>data</strong></td>
		</tr></tbody></table>

## iBeacon 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-Beacon/file/863f3fea9978/source/main.cpp)   
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2015 ARM Limited
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
 
#include <events/mbed_events.h>
#include <mbed.h>
#include "ble/BLE.h"
#include "ble/services/iBeacon.h"
 
static iBeacon* ibeaconPtr;
 
static EventQueue eventQueue(/* event count */ 4 * EVENTS_EVENT_SIZE);
 
/**
 * This function is called when the ble initialization process has failled
 */
void onBleInitError(BLE &ble, ble_error_t error)
{
    /* Initialization error handling should go here */
}
 
void printMacAddress()
{
    /* Print out device MAC address to the console*/
    Gap::AddressType_t addr_type;
    Gap::Address_t address;
    BLE::Instance().gap().getAddress(&addr_type, address);
    printf("DEVICE MAC ADDRESS: ");
    for (int i = 5; i >= 1; i--){
        printf("%02x:", address[i]);
    }
    printf("%02x\r\n", address[0]);
}
 
/**
 * Callback triggered when the ble initialization process has finished
 */
void bleInitComplete(BLE::InitializationCompleteCallbackContext *params)
{
    BLE&        ble   = params->ble;
    ble_error_t error = params->error;
 
    if (error != BLE_ERROR_NONE) {
        /* In case of error, forward the error handling to onBleInitError */
        onBleInitError(ble, error);
        return;
    }
 
    /* Ensure that it is the default instance of BLE */
    if(ble.getInstanceID() != BLE::DEFAULT_INSTANCE) {
        return;
    }
 
    /**
     * The Beacon payload has the following composition:
     * 128-Bit / 16byte UUID = E2 0A 39 F4 73 F5 4B C4 A1 2F 17 D1 AD 07 A9 61
     * Major/Minor  = 0x1122 / 0x3344
     * Tx Power     = 0xC8 = 200, 2's compliment is 256-200 = (-56dB)
     *
     * Note: please remember to calibrate your beacons TX Power for more accurate results.
     */
    static const uint8_t uuid[] = {0xE2, 0x0A, 0x39, 0xF4, 0x73, 0xF5, 0x4B, 0xC4,
                                   0xA1, 0x2F, 0x17, 0xD1, 0xAD, 0x07, 0xA9, 0x61};
    uint16_t majorNumber = 1122;
    uint16_t minorNumber = 3344;
    uint16_t txPower     = 0xC8;
    ibeaconPtr = new iBeacon(ble, uuid, majorNumber, minorNumber, txPower);
 
    ble.gap().setAdvertisingInterval(1000); /* 1000ms. */
    ble.gap().startAdvertising();
 
    printMacAddress();
}
 
void scheduleBleEventsProcessing(BLE::OnEventsToProcessCallbackContext* context) {
    BLE &ble = BLE::Instance();
    eventQueue.call(Callback<void()>(&ble, &BLE::processEvents));
}
 
int main()
{
    BLE &ble = BLE::Instance();
    ble.onEventsToProcess(scheduleBleEventsProcessing);
    ble.init(bleInitComplete);
 
    eventQueue.dispatch_forever();
 
    return 0;
}
```