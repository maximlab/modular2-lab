## LoRaWAN网络接口
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.png">

LoRaWANInterface 类层次结构</div>
LoRaWANInterface 提供了一个 C++ API，用于通过 LoRa 网络连接到互联网。本小节解释了 LoRaWAnInterface API 参考，然后提供了一个可以直接导入 Arm Mbed 在线编译器的示例。

## LoRaWANInterface 类参考

[LoRaWANInterface 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html)
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a191afa636497d31468702347698965ae" rel="nofollow" target="_blank">LoRaWANInterface</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html" rel="nofollow" target="_blank">LoRaRadio</a> &amp;radio)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a76264d82d6785acf20613ab96755c45e" rel="nofollow" target="_blank">LoRaWANInterface</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_radio.html" rel="nofollow" target="_blank">LoRaRadio</a> &amp;radio, <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_p_h_y.html" rel="nofollow" target="_blank">LoRaPHY</a> &amp;phy)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a37d63c19f319211914e7d759044efd74" rel="nofollow" target="_blank">initialize</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html" rel="nofollow" target="_blank">events::EventQueue</a> *queue)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a00a7a0568715b7a26d19265c842ca7f9" rel="nofollow" target="_blank">connect</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a34dfd6056a1f4f5220b4946ce7e44003" rel="nofollow" target="_blank">connect</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a0e8b9bddce3ba3d3112b461b2733e65e" rel="nofollow" target="_blank">lorawan_connect_t</a> &amp;connect)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a65ab6550d5140a9a370908d60686a6a5" rel="nofollow" target="_blank">disconnect</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#abb8efef2be6d75f58c4ac94b066aa276" rel="nofollow" target="_blank">add_link_check_request</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a9284812eacca4dee02c590af71bced62" rel="nofollow" target="_blank">remove_link_check_request</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#ae9e4fbaa39049261b65b62ab86405fc0" rel="nofollow" target="_blank">set_datarate</a> (uint8_t data_rate)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a6970698cd2797da65598f2d4a029df3a" rel="nofollow" target="_blank">enable_adaptive_datarate</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a2f7df1d18101b46db3b9caae98d6d10b" rel="nofollow" target="_blank">disable_adaptive_datarate</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#aef92138df25bebbfefe2c274be4ebe68" rel="nofollow" target="_blank">set_confirmed_msg_retries</a> (uint8_t count)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#aac2ede6d392c0cc0720403adcc9a9362" rel="nofollow" target="_blank">set_channel_plan</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#aae2af774bf626ba30618ec5aaf1d2901" rel="nofollow" target="_blank">lorawan_channelplan_t</a> &amp;channel_plan)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a273c9d17aafb78e9b84eb36e3826a1c5" rel="nofollow" target="_blank">get_channel_plan</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#aae2af774bf626ba30618ec5aaf1d2901" rel="nofollow" target="_blank">lorawan_channelplan_t</a> &amp;channel_plan)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#af2c83823711bdcd24a7badfe7ab9c12b" rel="nofollow" target="_blank">remove_channel_plan</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a3a6b0c84585d9dd2f52fd4b594fd42ff" rel="nofollow" target="_blank">remove_channel</a> (uint8_t index)</td>
		</tr><tr><td style="vertical-align:top;">virtual int16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a392077b6f6cf61f7b3bfa7462059bf44" rel="nofollow" target="_blank">send</a> (uint8_t port, const uint8_t *data, uint16_t length, int flags)</td>
		</tr><tr><td style="vertical-align:top;">virtual int16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#acd0b4d2dbe5f19c3f8ca35b668ee4e7d" rel="nofollow" target="_blank">receive</a> (uint8_t port, uint8_t *data, uint16_t length, int flags)</td>
		</tr><tr><td style="vertical-align:top;">virtual int16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a6950395dee75263577225ae81900adb2" rel="nofollow" target="_blank">receive</a> (uint8_t *data, uint16_t length, uint8_t &amp;port, int &amp;flags)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#afb075f43b7fcc825e69d11020b0e9812" rel="nofollow" target="_blank">add_app_callbacks</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structlorawan__app__callbacks__t.html" rel="nofollow" target="_blank">lorawan_app_callbacks_t</a> *callbacks)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a2a8113da595605351c6d8ae0c2c0270f" rel="nofollow" target="_blank">set_device_class</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a594f261dd34319dca9994f181ff1c087" rel="nofollow" target="_blank">device_class_t</a> device_class)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a3fe6f1c6b9d84e8ad7fc10a49a95cb52" rel="nofollow" target="_blank">get_tx_metadata</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structlorawan__tx__metadata.html" rel="nofollow" target="_blank">lorawan_tx_metadata</a> &amp;metadata)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a3a5cf2e255941257c57193c3b7864aed" rel="nofollow" target="_blank">get_rx_metadata</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structlorawan__rx__metadata.html" rel="nofollow" target="_blank">lorawan_rx_metadata</a> &amp;metadata)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#a3202732442318f86c2329b72964856fc" rel="nofollow" target="_blank">get_backoff_metadata</a> (int &amp;backoff)</td>
		</tr><tr><td style="vertical-align:top;">virtual <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/lorawan__types_8h.html#a9efa78377307e6772301c80921b56872" rel="nofollow" target="_blank">lorawan_status_t</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_lo_ra_w_a_n_interface.html#aac0f1df4ddf7421bf22a0f75c98aabb0" rel="nofollow" target="_blank">cancel_sending</a> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="adc93e149a793817dfcf97b3df5858f60" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lock</strong> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a86af6a5b062b92c25614b804ebc97718" target="_blank"></a> void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>unlock</strong> (void)</td>
		</tr></tbody></table>

## LoRaWAN 示例
请访问我们的 Arm Mbed 在线编译器示例，并按照 README.md 中的说明进行操作。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-lorawan/file/dc95ac6d6d4e/main.cpp)
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