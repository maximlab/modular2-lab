## BatteryService
通常要求使用电池工作的设备向用户报告电池充电水平。

[蓝牙电池服务](https://www.bluetooth.org/docman/handlers/downloaddoc.ashx?doc_id=245138)定义了如何通过 BLE 链路显示电池电量。它允许设备的客户端（通常是智能手机应用程序）读取当前的电池电量并跟踪其演变。

BatteryService 类实现 Bluetooth SIG 定义的蓝牙电池服务。使用电池运行的 BLE 设备制造商可以使用 API 以互操作的方式公开其产品的充电水平。

## BatteryService 类参考
[BatteryService 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html)

公<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html#a22b361b6e0a77a512f62e4d6209547ed" rel="nofollow" target="_blank">BatteryService</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;_ble, uint8_t level=100)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html#ab3b12effa0ed860ae6fcfb65a3472a1b" rel="nofollow" target="_blank">updateBatteryLevel</a> (uint8_t newLevel)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_b_l_e.html" rel="nofollow" target="_blank">BLE</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html#a2eedbcb0e3b8b62652685c3f91423cba" rel="nofollow" target="_blank">ble</a></td>
		</tr><tr><td style="vertical-align:top;">uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html#abbb836787138d93fe5d6ade966328224" rel="nofollow" target="_blank">batteryLevel</a></td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_read_only_gatt_characteristic.html" rel="nofollow" target="_blank">ReadOnlyGattCharacteristic</a>&lt; uint8_t &gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_battery_service.html#af858f9946bb0bd88338f25808ffda084" rel="nofollow" target="_blank">batteryLevelCharacteristic</a></td>
		</tr></tbody></table>

## BatteryService 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-BatteryLevel/file/5d8484f69181/source/main.cpp)       
```
/* mbed Microcontroller Library
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
 
#include <events/mbed_events.h>
#include <mbed.h>
#include "ble/BLE.h"
#include "ble/Gap.h"
#include "ble/services/BatteryService.h"
 
DigitalOut led1(LED1, 1);
 
const static char     DEVICE_NAME[] = "BATTERY";
static const uint16_t uuid16_list[] = {GattService::UUID_BATTERY_SERVICE};
 
static uint8_t batteryLevel = 50;
static BatteryService* batteryServicePtr;
 
static EventQueue eventQueue(/* event count */ 16 * EVENTS_EVENT_SIZE);
 
void disconnectionCallback(const Gap::DisconnectionCallbackParams_t *params)
{
    BLE::Instance().gap().startAdvertising();
}
 
void updateSensorValue() {
    batteryLevel++;
    if (batteryLevel > 100) {
        batteryLevel = 20;
    }
 
    batteryServicePtr->updateBatteryLevel(batteryLevel);
}
 
void blinkCallback(void)
{
    led1 = !led1; /* Do blinky on LED1 while we're waiting for BLE events */
 
    BLE &ble = BLE::Instance();
    if (ble.gap().getState().connected) {
        eventQueue.call(updateSensorValue);
    }
}
 
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
 
    ble.gap().onDisconnection(disconnectionCallback);
 
    /* Setup primary service */
    batteryServicePtr = new BatteryService(ble, batteryLevel);
 
    /* Setup advertising */
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::BREDR_NOT_SUPPORTED | GapAdvertisingData::LE_GENERAL_DISCOVERABLE);
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LIST_16BIT_SERVICE_IDS, (uint8_t *) uuid16_list, sizeof(uuid16_list));
    ble.gap().accumulateAdvertisingPayload(GapAdvertisingData::COMPLETE_LOCAL_NAME, (uint8_t *) DEVICE_NAME, sizeof(DEVICE_NAME));
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
    eventQueue.call_every(500, blinkCallback);
 
    BLE &ble = BLE::Instance();
    ble.onEventsToProcess(scheduleBleEventsProcessing);
    ble.init(bleInitComplete);
 
    eventQueue.dispatch_forever();
 
    return 0;
}
```