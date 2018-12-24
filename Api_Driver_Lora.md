## LoRa 无线电驱动程序

LoRaRadio 是一个纯虚类，它定义了 LoRa 无线电驱动程序的 API。

该类的实现被传递给 Arm Mbed LoRaWAN 栈。有关更多信息，请参阅[Mbed OS 支持的驱动程序](https://github.com/ARMmbed/mbed-semtech-lora-rf-drivers)。

## LoRaRadio 类参考

[LoRaRadio 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html)

|公共成员函数||
|------|:-|
|virtual void |	[init_radio](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a6c6f8602f99b5b2241d9b34d3ad36537) ([radio_events_t](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structradio__events.html) *events)=0|
|virtual void |	[radio_reset](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#af3d543c7a4a2535a267774ee4556d4de) ()=0|
|virtual void |	[sleep](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a6c1e9cc99fb8e568ebda17b32f7deea7) (void)=0|
|virtual void |	[standby](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a3ab943e1b7ce8b851e9c9964b603ebaf) (void)=0|
|virtual void |	[set_rx_config](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#aeb38a013cd7ca03170e3535465e69120) (radio_modems_t modem, uint32_t bandwidth, uint32_t datarate, uint8_t coderate, uint32_t bandwidth_afc, uint16_t preamble_len, uint16_t symb_timeout, bool fix_len, uint8_t payload_len, bool crc_on, bool freq_hop_on, uint8_t hop_period, bool iq_inverted, bool rx_continuous)=0|
|virtual void |	[set_tx_config](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a55d71e0c505f725778a306988a4baa45) (radio_modems_t modem, int8_t power, uint32_t fdev, uint32_t bandwidth, uint32_t datarate, uint8_t coderate, uint16_t preamble_len, bool fix_len, bool crc_on, bool freq_hop_on, uint8_t hop_period, bool iq_inverted, uint32_t timeout)=0|
|virtual void |	[send](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#afe8dbcb94b786ed9f112ee0919a9b733) (uint8_t *buffer, uint8_t size)=0|
|virtual void |	[receive](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#ac6a5c58d7bfe81ac25d21c314887273c) (void)=0|
|virtual void |	[set_channel](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a7eec5d8d9fa7a432fee4008379a0b242) (uint32_t freq)=0|
|virtual uint32_t |	[random](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a35dcc46134eae880d8f1607da0f289da) (void)=0|
|virtual uint8_t |	[get_status](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a1f1a1d6003d92b7d670fc225ac70d007) (void)=0|
|virtual void |	[set_max_payload_length](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a82e7ab7abb6107f31e21c4cffb5c4ae2) (radio_modems_t modem, uint8_t max)=0|
|virtual void |	[set_public_network](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a8bf057b29a5adbec7f3c8acc661c170f) (bool enable)=0|
|virtual uint32_t |	[time_on_air](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a55d400ce86dc6d44c4c720bf1242682b) (radio_modems_t modem, uint8_t pkt_len)=0|
|virtual bool |	[perform_carrier_sense](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#ae40b58787d83e9e8f5fdc1f1847a213c) (radio_modems_t modem, uint32_t freq, int16_t rssi_threshold, uint32_t max_carrier_sense_time)=0|
|virtual void |	[start_cad](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a1ee238e89125ac6240a3c9ffdec7b740) (void)=0|
|virtual bool |	[check_rf_frequency](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a871adee8837863a725f02af41cc4fbc9) (uint32_t frequency)=0|
|virtual void |	[set_tx_continuous_wave](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#aed0e8297a1b09a85b6b09f44c1cf7bd6) (uint32_t freq, int8_t power, uint16_t time)=0|
|virtual void |	[lock](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a7b02efe569d5aa54f0bcf244e075e2d5) (void)=0|
|virtual void |	[unlock](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html#a743ebd1e177b3305dffcf666328ad25e) (void)=0|
## LoRaRadio 示例

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-lorawan/file/dc95ac6d6d4e/main.cpp)                                                                                                                                               <div align=right>[导入到 Mbed IDE](https://os.mbed.com/compiler/#import:https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-lorawan)</div>
```
/**
 * Copyright (c) 2017, Arm Limited and affiliates.
 * SPDX-License-Identifier: Apache-2.0
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
#include <stdio.h>
#include "lorawan/LoRaWANInterface.h"
#include "lorawan/system/lorawan_data_structures.h"
#include "events/EventQueue.h"
 
// Application helpers
#include "DummySensor.h"
#include "trace_helper.h"
#include "lora_radio_helper.h"
 
using namespace events;
 
uint8_t tx_buffer[LORAMAC_PHY_MAXPAYLOAD];
uint8_t rx_buffer[LORAMAC_PHY_MAXPAYLOAD];
 
/*
 * Sets up an application dependent transmission timer in ms. Used only when Duty Cycling is off for testing
 */
#define TX_TIMER                        10000
 
/**
 * Maximum number of events for the event queue.
 * 16 is the safe number for the stack events, however, if application
 * also uses the queue for whatever purposes, this number should be increased.
 */
#define MAX_NUMBER_OF_EVENTS            16
 
/**
 * Maximum number of retries for CONFIRMED messages before giving up
 */
#define CONFIRMED_MSG_RETRY_COUNTER     3
 
/**
 * Dummy pin for dummy sensor
 */
#define PC_9                            0
 
/**
 * Dummy sensor class object
 */
DS1820  ds1820(PC_9);
 
/**
* This event queue is the global event queue for both the
* application and stack. To conserve memory, the stack is designed to run
* in the same thread as the application and the application is responsible for
* providing an event queue to the stack that will be used for ISR deferment as
* well as application information event queuing.
*/
static EventQueue ev_queue(MAX_NUMBER_OF_EVENTS * EVENTS_EVENT_SIZE);
 
/**
 * Event handler.
 *
 * This will be passed to the LoRaWAN stack to queue events for the
 * application which in turn drive the application.
 */
static void lora_event_handler(lorawan_event_t event);
 
/**
 * Constructing Mbed LoRaWANInterface and passing it down the radio object.
 */
static LoRaWANInterface lorawan(radio);
 
/**
 * Application specific callbacks
 */
static lorawan_app_callbacks_t callbacks;
 
/**
 * Entry point for application
 */
int main (void)
{
    // setup tracing
    setup_trace();
 
    // stores the status of a call to LoRaWAN protocol
    lorawan_status_t retcode;
 
    // Initialize LoRaWAN stack
    if (lorawan.initialize(&ev_queue) != LORAWAN_STATUS_OK) {
        printf("\r\n LoRa initialization failed! \r\n");
        return -1;
    }
 
    printf("\r\n Mbed LoRaWANStack initialized \r\n");
 
    // prepare application callbacks
    callbacks.events = mbed::callback(lora_event_handler);
    lorawan.add_app_callbacks(&callbacks);
 
    // Set number of retries in case of CONFIRMED messages
    if (lorawan.set_confirmed_msg_retries(CONFIRMED_MSG_RETRY_COUNTER)
                                          != LORAWAN_STATUS_OK) {
        printf("\r\n set_confirmed_msg_retries failed! \r\n\r\n");
        return -1;
    }
 
    printf("\r\n CONFIRMED message retries : %d \r\n",
           CONFIRMED_MSG_RETRY_COUNTER);
 
    // Enable adaptive data rate
    if (lorawan.enable_adaptive_datarate() != LORAWAN_STATUS_OK) {
        printf("\r\n enable_adaptive_datarate failed! \r\n");
        return -1;
    }
 
    printf("\r\n Adaptive data  rate (ADR) - Enabled \r\n");
 
    retcode = lorawan.connect();
 
    if (retcode == LORAWAN_STATUS_OK ||
        retcode == LORAWAN_STATUS_CONNECT_IN_PROGRESS) {
    } else {
        printf("\r\n Connection error, code = %d \r\n", retcode);
        return -1;
    }
 
    printf("\r\n Connection - In Progress ...\r\n");
 
    // make your event queue dispatching events forever
    ev_queue.dispatch_forever();
}
 
/**
 * Sends a message to the Network Server
 */
static void send_message()
{
    uint16_t packet_len;
    int16_t retcode;
    float sensor_value;
 
    if (ds1820.begin()) {
        ds1820.startConversion();
        sensor_value = ds1820.read();
        printf("\r\n Dummy Sensor Value = %3.1f \r\n", sensor_value);
        ds1820.startConversion();
    } else {
        printf("\r\n No sensor found \r\n");
        return;
    }
 
    packet_len = sprintf((char*) tx_buffer, "Dummy Sensor Value is %3.1f",
                    sensor_value);
 
    retcode = lorawan.send(MBED_CONF_LORA_APP_PORT, tx_buffer, packet_len,
                           MSG_CONFIRMED_FLAG);
 
    if (retcode < 0) {
        retcode == LORAWAN_STATUS_WOULD_BLOCK ? printf("send - WOULD BLOCK\r\n")
                : printf("\r\n send() - Error code %d \r\n", retcode);
        return;
    }
 
    printf("\r\n %d bytes scheduled for transmission \r\n", retcode);
    memset(tx_buffer, 0, LORAMAC_PHY_MAXPAYLOAD);
}
 
/**
 * Receive a message from the Network Server
 */
static void receive_message()
{
    int16_t retcode;
    retcode = lorawan.receive(MBED_CONF_LORA_APP_PORT, rx_buffer,
                              LORAMAC_PHY_MAXPAYLOAD,
                              MSG_CONFIRMED_FLAG|MSG_UNCONFIRMED_FLAG);
 
    if (retcode < 0) {
        printf("\r\n receive() - Error code %d \r\n", retcode);
        return;
    }
 
    printf(" Data:");
 
    for (uint8_t i = 0; i < retcode; i++) {
        printf("%x", rx_buffer[i]);
    }
 
    printf("\r\n Data Length: %d\r\n", retcode);
 
    memset(rx_buffer, 0, LORAMAC_PHY_MAXPAYLOAD);
}
 
/**
 * Event handler
 */
static void lora_event_handler(lorawan_event_t event)
{
    switch (event) {
        case CONNECTED:
            printf("\r\n Connection - Successful \r\n");
            if (MBED_CONF_LORA_DUTY_CYCLE_ON) {
                send_message();
            } else {
                ev_queue.call_every(TX_TIMER, send_message);
            }
 
            break;
        case DISCONNECTED:
            ev_queue.break_dispatch();
            printf("\r\n Disconnected Successfully \r\n");
            break;
        case TX_DONE:
            printf("\r\n Message Sent to Network Server \r\n");
            if (MBED_CONF_LORA_DUTY_CYCLE_ON) {
                send_message();
            }
            break;
        case TX_TIMEOUT:
        case TX_ERROR:
        case TX_CRYPTO_ERROR:
        case TX_SCHEDULING_ERROR:
            printf("\r\n Transmission Error - EventCode = %d \r\n", event);
            // try again
            if (MBED_CONF_LORA_DUTY_CYCLE_ON) {
                send_message();
            }
            break;
        case RX_DONE:
            printf("\r\n Received message from Network Server \r\n");
            receive_message();
            break;
        case RX_TIMEOUT:
        case RX_ERROR:
            printf("\r\n Error in reception - Code = %d \r\n", event);
            break;
        case JOIN_FAILURE:
            printf("\r\n OTAA Failed - Check Keys \r\n");
            break;
        default:
            MBED_ASSERT("Unknown Event");
    }
}
 
// EOF
``` 
相关内容

[LoRa 架构](https://os.mbed.com/docs/v5.9/reference/lora-tech.html)。