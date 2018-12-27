## HeartRateService
练习体育活动的人使用心率监测器实时跟踪他们的脉搏并改善他们的身体表现。

[蓝牙心率服务](https://www.bluetooth.org/docman/handlers/downloaddoc.ashx?doc_id=239866)定义了如何通过 BLE 链路暴露心率传感器的数据。该服务的标准性质允许收集器（通常是智能手机应用程序）和符合该服务的心率监视器之间的无缝操作。

HeartRateService 类实现蓝牙机身定义的蓝牙心率服务。支持 BLE 的健身设备的制造商可以使用它来暴露可互操作的心率传感器数据。

注意: 蓝牙心率服务是[蓝牙心率配置文](https://www.bluetooth.org/docman/handlers/downloaddoc.ashx?doc_id=239865)件的一部分，它定义了蓝牙心率传感器所期望的行为。您必须确保您的应用符合心率配置文件，以保证心率传感器的互操作性。

## HeartRateService 类参考
[HeartRateService 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html)

<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_heart_rate_service_1_1_heart_rate_value_bytes.html" rel="nofollow" target="_blank">HeartRateValueBytes</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;">enum &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89" rel="nofollow" target="_blank">BodySensorLocation</a> {<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89a3d89f019f25e51aff98218d40a03792e" rel="nofollow" target="_blank">LOCATION_OTHER</a> = 0, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89a35c442827e84f4b35c5c48452df8f0fe" rel="nofollow" target="_blank">LOCATION_CHEST</a> = 1, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89a94d832ae15ac7ef91e463d1af2a1e2ea" rel="nofollow" target="_blank">LOCATION_WRIST</a> = 2, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89a4e65240f86ece4ce1f692bffeb5574b7" rel="nofollow" target="_blank">LOCATION_FINGER</a>,<br>
			&nbsp;&nbsp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89adcec0ed39f059c0335fae25611957994" rel="nofollow" target="_blank">LOCATION_HAND</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89ab0c8e626f79ae600bc70af164376b914" rel="nofollow" target="_blank">LOCATION_EAR_LOBE</a>, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89a73c9a4a71d7d0158f43b6cc122350235" rel="nofollow" target="_blank">LOCATION_FOOT</a><br>
			}</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a38f3b24ca96324d3114c69a570d81a76" rel="nofollow" target="_blank">HeartRateService</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;_ble, uint16_t hrmCounter, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a57928e32d89dfb9a04e633c0f8b90c89" rel="nofollow" target="_blank">BodySensorLocation</a> location)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a9d5eb1fb2f6b69324fdb9c2b2886b479" rel="nofollow" target="_blank">updateHeartRate</a> (uint16_t hrmCounter)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heart_rate_service.html#a7a2ae4ab8e76c3e5e248ecd8a660fb6c" rel="nofollow" target="_blank">setupService</a> (void)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a7155d7e955386203e34cb1dc055b6f8e" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>ble</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aee937a9b24612bc67c27164147cf0929" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/struct_heart_rate_service_1_1_heart_rate_value_bytes.html" rel="nofollow" target="_blank">HeartRateValueBytes</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>valueBytes</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aac20251de2b98197e59aa64f9dc70df6" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_gatt_characteristic.html" rel="nofollow" target="_blank">GattCharacteristic</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>hrmRate</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a03aef259eda3434a5c3c595af46e7dd1" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_read_only_gatt_characteristic.html" rel="nofollow" target="_blank">ReadOnlyGattCharacteristic</a>&lt; uint8_t &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>hrmLocation</strong></td>
		</tr></tbody></table>

## HeartRateService 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-HeartRate/file/307bde0f868f/source/main.cpp)
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
#include "ble/Gap.h"
#include "ble/services/HeartRateService.h"
 
DigitalOut led1(LED1, 1);
 
const static char     DEVICE_NAME[] = "HRM";
static const uint16_t uuid16_list[] = {GattService::UUID_HEART_RATE_SERVICE};
 
static uint8_t hrmCounter = 100; // init HRM to 100bps
static HeartRateService *hrServicePtr;
 
static EventQueue eventQueue(/* event count */ 16 * EVENTS_EVENT_SIZE);
 
void disconnectionCallback(const Gap::DisconnectionCallbackParams_t *params)
{
    BLE::Instance().gap().startAdvertising(); // restart advertising
}
 
void updateSensorValue() {
    // Do blocking calls or whatever is necessary for sensor polling.
    // In our case, we simply update the HRM measurement.
    hrmCounter++;
 
    //  100 <= HRM bps <=175
    if (hrmCounter == 175) {
        hrmCounter = 100;
    }
 
    hrServicePtr->updateHeartRate(hrmCounter);
}
 
void periodicCallback(void)
{
    led1 = !led1; /* Do blinky on LED1 while we're waiting for BLE events */
 
    if (BLE::Instance().getGapState().connected) {
        eventQueue.call(updateSensorValue);
    }
}
 
void onBleInitError(BLE &ble, ble_error_t error)
{
    (void)ble;
    (void)error;
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
 
void bleInitComplete(BLE::InitializationCompleteCallbackContext *params)
{
    BLE&        ble   = params->ble;
    ble_error_t error = params->error;
 
    if (error != BLE_ERROR_NONE) {
        onBleInitError(ble, error);
        return;
    }
 
    if (ble.getInstanceID() != BLE::DEFAULT_INSTANCE) {
        return;
    }
 
    ble.gap().onDisconnection(disconnectionCallback);
 
    /* Setup primary service. */
    hrServicePtr = new HeartRateService(ble, hrmCounter, HeartRateService::LOCATION_FINGER);
 
    /* Setup advertising. */
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::BREDR_NOT_SUPPORTED | GapAdvertisingData::LE_GENERAL_DISCOVERABLE);
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LIST_16BIT_SERVICE_IDS, (uint8_t *)uuid16_list, sizeof(uuid16_list));
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::GENERIC_HEART_RATE_SENSOR);
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LOCAL_NAME, (uint8_t *)DEVICE_NAME, sizeof(DEVICE_NAME));
    ble.gap().setAdvertisingType(GapAdvertisingParams::ADV_CONNECTABLE_UNDIRECTED);
    ble.gap().setAdvertisingInterval(1000); /* 1000ms */
    ble.gap().startAdvertising();
 
    printMacAddress();
}
 
void scheduleBleEventsProcessing(BLE::OnEventsToProcessCallbackContext* context) {
    BLE &ble = BLE::Instance();
    eventQueue.call(Callback<void()>(&ble, &BLE::processEvents));
}
 
int main()
{
    eventQueue.call_every(500, periodicCallback);
 
    BLE &ble = BLE::Instance();
    ble.onEventsToProcess(scheduleBleEventsProcessing);
    ble.init(bleInitComplete);
 
    eventQueue.dispatch_forever();
 
    return 0;
}
```