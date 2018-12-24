## 6LoWPAN 和 Thread Mesh

该页面描述了 6LoWPAN 和基于 Thread 的网状网络的构建时可配置参数。Mbed OS 支持两种主要的网状协议：6LoWPAN-ND 和 Thread。根据所选协议，您可以配置不同的值集。

Mbed OS 中有一个支持网格的栈称为 Nanostack。

本指南分为几个部分，首先是通用的 Nanostack 配置，然后是 Thread 的配置，然后是 6LoWPAN-ND。

要了解技术和 API，请在此之前参考以下部分：

+ Mbed OS 技术页面中的网络连接。
+ 6LoWPAN Mesh 技术页面。
+ 6LoWPAN Mesh 类参考用户 API。
+ 套接字 API。
### 提供配置

如果要使用非默认设置，应用程序需要创建 mbed_app.json 配置文件。值可以使用 nanostack。* 或 mbed-mesh-api.* 作为前缀，具体取决于它们配置的内部模块。

配置文件的示例：
```
{
    "target_overrides": {
        "*": {
            "target.features_add": ["NANOSTACK", "COMMON_PAL"],
            "nanostack.configuration": "lowpan_router",
            "mbed-mesh-api.6lowpan-nd-device-type": "NET_6LOWPAN_ROUTER",
            "mbed-mesh-api.6lowpan-nd-channel": 12,
        }
    }
```
**注意**: 6LoWPAN 和 Thread 的配置文件用于开发或测试目的。在设置生产配置时，用户需要充分了解整个系统。

### 构建栈的时间配置

为了最小化生成的网络栈的大小，Nanostack 定义了一组构建选项。

### 构建不同网格类型的选项

|选项名称	|功能支持	|Nanostack 的估计二进制大小|
|-|-|:-:|
|ethernet_host	|仅支持以太网主机，无网状网络。	|108 kB|
|lowpan_border_router	|6LoWPAN-ND 边界路由器支持。	|219 kB|
|lowpan_host	|6LoWPAN-ND 非路由主机模式。	|122 kB|
|lowpan_router	|6LoWPAN-ND 路由主机模式。	|169 kB|
|nanostack_full	|一切。这仅用于测试目的。	|355 kB|
|thread_border_router	|具有边界路由器功能的线程路由器	|212 kB|
|thread_end_device	|线程主机没有路由功能。	|166 kB|
|thread_router	|线程主机具有路由功能。	|199 kB|
**注意**: 使用 GNU Arm Embedded Toolchain 4.9 版估算了二进制大小。它们根据工具链或存储库的状态而不同。只有在链接最终应用程序时才能估算最终大小。指定的大小仅为您提供了不同选项之间预期的更改类型的指导。

如果要优化闪存使用率，则需要配置 Nanostack。要选择的配置主要取决于首选用例。

有关星形和网状网络的定义，请参阅 6LoWPAN 技术概述。这些相同的原则也适用于 Thread 协议。

选择网络所基于的协议：

+ 6LoWPAN-ND.
+ Thread.

选择设备角色：

+ 网状网络。路由器。（默认）
+ 星网。非路由设备，也称为主机或困宿主。

在应用程序中，从两个支持的接口类中进行选择：

+ 对于基于 6LoWPAN-ND 的网络，请使用 LoWPANNDInterface。
+ 对于基于 Thread 的网络，请使用 ThreadInterface。

然后，您可以选择为这些网络选择非路由模式。下表显示了 mbed_app.json 文件中用于不同网络中设备的值。

### mesh-type: MESH_LOWPAN

|设备角色	|nanostack.configuration 值	|mbed-mesh-api.6lowpan-nd-device-type|
|-|-|-|
|网状路由器（默认）	|lowpan_router	|NET_6LOWPAN_ROUTER|
|非路由设备	|lowpan_host	|NET_6LOWPAN_HOST|

### mesh-type: MESH_THREAD

|设备角色	|nanostack.configuration 值	|mbed-mesh-api.thread-device-type|
|-|-|-|
|网状路由器（默认）	|thread_router	|MESH_DEVICE_TYPE_THREAD_ROUTER|
|非路由设备	|thread_end_device	|MESH_DEVICE_TYPE_THREAD_SLEEPY_END_DEVICE|

### Nanostack 的配置
```
Configuration parameters
------------------------
 
Name: nanostack-eventloop.exclude_highres_timer
    Description: Exclude high resolution timer from build
    Defined by: library:nanostack-eventloop
    No value set
Name: nanostack-eventloop.use_platform_tick_timer
    Description: Use platform provided low resolution tick timer for eventloop
    Defined by: library:nanostack-eventloop
    No value set
Name: nanostack-hal.critical-section-usable-from-interrupt
    Description: Make critical section API usable from interrupt context. Else a mutex is used as locking primitive. Consult arm_hal_interrupt.c for possible side effects on interrupt latency.
    Defined by: library:nanostack-hal
    No value set
Name: nanostack-hal.event-loop-dispatch-from-application
    Description: Application is responsible of message dispatch loop. Else launch a separate thread for event-loop.
    Defined by: library:nanostack-hal
    No value set
Name: nanostack-hal.event_loop_thread_stack_size
    Description: Define event-loop thread stack size. [bytes]
    Defined by: library:nanostack-hal
    Macro name: MBED_CONF_NANOSTACK_HAL_EVENT_LOOP_THREAD_STACK_SIZE
    Value: 6144 (set by library:nanostack-hal)
Name: nanostack-hal.nvm_cfstore
    Description: Use cfstore as a NVM storage. Else RAM simulation will be used
    Defined by: library:nanostack-hal
    No value set
Name: nanostack.configuration
    Description: Build time configuration. Refer to Handbook for valid values. Default: full stack
    Defined by: library:nanostack
    Macro name: MBED_CONF_NANOSTACK_CONFIGURATION
    Value: nanostack_full (set by library:nanostack)
```
### 通用 Mbed 网格 API 配置值

通用配置允许您微调 Nanostack 的堆使用情况。
```
Configuration parameters
------------------------
 
Name: mbed-mesh-api.use-malloc-for-heap
    Description: Use `malloc()` for reserving the Nanostack's internal heap.
    Defined by: library:mbed-mesh-api
    No value set
Name: mbed-mesh-api.heap-size
    Description: Nanostack's heap size [bytes: 0-65534]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_HEAP_SIZE
    Value: 32500 (set by library:mbed-mesh-api)
``` 
### Thread 相关的配置参数

以下参数仅对 Thread mesh 协议有效。当应用程序使用 ThreadInterface 类时，这些正在使用中。
```
Configuration parameters
------------------------
 
Name: mbed-mesh-api.thread-config-channel
    Description: RF channel to use. [11-26]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_CHANNEL
    Value: 22 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-channel-mask
    Description: Channel bit mask, 0x7ffff800 scans all channels. [0-0x07fff800]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_CHANNEL_MASK
    Value: 0x7fff800 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-channel-page
    Description: Channel page, 0 for 2.4 GHz radio.
    Defined by: library:mbed-mesh-api
    No value set
Name: mbed-mesh-api.thread-config-commissioning-dataset-timestamp
    Description: [48 bit timestamp seconds]-[15 bit timestamp ticks]-[U bit] (0-0xFFFFFFFFFFFFFFFF)
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_COMMISSIONING_DATASET_TIMESTAMP
    Value: 0x10000 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-extended-panid
    Description: Extended PAN ID. [8 byte array]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_EXTENDED_PANID
    Value: {0xf1, 0xb5, 0xa1, 0xb2,0xc4, 0xd5, 0xa1, 0xbd } (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-ml-prefix
    Description: Mesh Local prefix. [8 byte array]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_ML_PREFIX
    Value: {0xfd, 0x0, 0x0d, 0xb8, 0x0, 0x0, 0x0, 0x0} (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-network-name
    Description: Network name [string, max 16 characters]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_NETWORK_NAME
    Value: "Thread Network" (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-panid
    Description: Network identifier [0-0xFFFF]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_PANID
    Value: 0x0700 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-config-pskc
    Description: Pre-Shared Key for the Commissioner. [16 byte array]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_CONFIG_PSKC
    Value: {0xc8, 0xa6, 0x2e, 0xae, 0xf3, 0x68, 0xf3, 0x46, 0xa9, 0x9e, 0x57, 0x85, 0x98, 0x9d, 0x1c, 0xd0} (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-device-type
    Description: Supported device operating modes: MESH_DEVICE_TYPE_THREAD_ROUTER, MESH_DEVICE_TYPE_THREAD_SLEEPY_END_DEVICE, MESH_DEVICE_TYPE_THREAD_MINIMAL_END_DEVICE
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_DEVICE_TYPE
    Value: MESH_DEVICE_TYPE_THREAD_ROUTER (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-master-key
    Description: Network master key. [16 byte array]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_MASTER_KEY
    Value: {0x10, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff} (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-pskd
    Description: Human-scaled commissioning credentials. Uppercase alphanumeric string (0-9, A-Y excluding I, O, Q and Z), 6-32 characters.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_PSKD
    Value: "ABCDEFGH" (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-security-policy
    Description: Commissioning security policy bits [0-0xFF]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_SECURITY_POLICY
    Value: 255 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.thread-use-static-link-config
    Description: True: Use the below link config, False: Use commissioning, ignore the below link config.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_THREAD_USE_STATIC_LINK_CONFIG
    Value: 1 (set by library:mbed-mesh-api)
```
### 6LoWPAN 相关配置参数

以下参数仅对 6LoWPAN-ND 网状网络有效。当应用程序使用 LoWPANNDInterface 类时，这些正在使用中。
```
Configuration parameters
------------------------
 
Name: mbed-mesh-api.6lowpan-nd-channel
    Description: RF channel to use when `channel_mask` is not defined. [0-26].
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_CHANNEL
    Value: 14 (set by application[*])
Name: mbed-mesh-api.6lowpan-nd-channel-mask
    Description: Channel mask, bit-mask of channels to use. [0-0x07fff800]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_CHANNEL_MASK
    Value: 0x7fff800 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.6lowpan-nd-channel-page
    Description: 0 for 2.4 GHz and 2 for sub-GHz radios.
    Defined by: library:mbed-mesh-api
    No value set
Name: mbed-mesh-api.6lowpan-nd-device-type
    Description: Device mode (NET_6LOWPAN_ROUTER or NET_6LOWPAN_HOST). Router is routing packets from other device, creating a mesh network.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_DEVICE_TYPE
    Value: NET_6LOWPAN_ROUTER (set by library:mbed-mesh-api)
Name: mbed-mesh-api.6lowpan-nd-panid-filter
    Description: Beacon PAN ID filter, 0xffff means no filtering. [0-0xffff]
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_PANID_FILTER
    Value: 0xAB42 (set by application[*])
Name: mbed-mesh-api.6lowpan-nd-psk-key
    Description: Pre-shared network key. Byte array of 16 bytes. In form of: {0x00, 0x11, ... 0xff}
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_PSK_KEY
    Value: {0xa0, 0xa1, 0xa2, 0xa3, 0xa4, 0xa5, 0xa6, 0xa7, 0xa8, 0xa9, 0xaa, 0xab, 0xac, 0xad, 0xae, 0xaf} (set by library:mbed-mesh-api)
Name: mbed-mesh-api.6lowpan-nd-psk-key-id
    Description: PSK key ID when PSK is enabled.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_PSK_KEY_ID
    Value: 1 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.6lowpan-nd-sec-level
    Description: Network security level (1-7). Use default `5`.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_SEC_LEVEL
    Value: 5 (set by library:mbed-mesh-api)
Name: mbed-mesh-api.6lowpan-nd-security-mode
    Description: NONE or PSK to use either no security, or pre-shared network key.
    Defined by: library:mbed-mesh-api
    Macro name: MBED_CONF_MBED_MESH_API_6LOWPAN_ND_SECURITY_MODE
    Value: NONE (set by library:mbed-mesh-api)
```