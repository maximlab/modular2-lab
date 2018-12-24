## 配置系统

Arm Mbed OS 配置系统是 Arm Mbed OS 构建工具的一部分，可自定义编译时配置参数。每个库可以在其 mbed_lib.json 中定义许多配置参数。mbed_app.json 可以覆盖这些配置参数的值。配置使用 JSON 定义。配置参数的一些示例：

+ 数据采集应用程序的采样周期。
+ 新创建的 OS 线程的默认栈大小。
+ 串行通信库的接收缓冲区大小。
+ Mbed 目标的 flash 和 RAM 内存大小。
Arm Mbed OS 配置系统收集并解释目标配置中目标中定义的配置，所有 mbed_lib.json 文件和 mbed_app.json 文件。配置系统创建单个头文件 mbed_config.h，其中包含转换为 C 预处理器宏的所有已定义配置参数。mbed 编译将 mbed_config.h 放在 build 目录中，mbed 导出将它放在应用程序根目录中。mbed 编译在调用编译器之前运行 Mbed 配置系统，mbed 导出在创建项目文件之前运行配置系统。

     **注意**: 在本文档中，“library” 表示其自己目录中的任何可重用代码段。

     **注意**: 在以前的版本中，配置系统提供了添加自定义目标的方法。Mbed OS 工具现在在应用程序根目录中的名为 custom_targets.json 的文件中查找自定义目标，并将自定义目标视为与 Mbed 目标相同。

## 检查可用的配置参数

Mbed CLI 包含一个用于列出和解释编译时配置的命令，mbed compile --config。此命令打印配置参数的摘要，例如：
```
Configuration parameters
------------------------
cellular.random_max_start_delay = 0 (macro name: "MBED_CONF_CELLULAR_RANDOM_MAX_START_DELAY")
cellular.use-apn-lookup = 1 (macro name: "MBED_CONF_CELLULAR_USE_APN_LOOKUP")
configuration-store.storage_disable = 0 (macro name: "CFSTORE_STORAGE_DISABLE")
drivers.uart-serial-rxbuf-size = 256 (macro name: "MBED_CONF_DRIVERS_UART_SERIAL_RXBUF_SIZE")
drivers.uart-serial-txbuf-size = 256 (macro name: "MBED_CONF_DRIVERS_UART_SERIAL_TXBUF_SIZE")
events.present = 1 (macro name: "MBED_CONF_EVENTS_PRESENT")
events.shared-dispatch-from-application = 0 (macro name: "MBED_CONF_EVENTS_SHARED_DISPATCH_FROM_APPLICATION")
events.shared-eventsize = 256 (macro name: "MBED_CONF_EVENTS_SHARED_EVENTSIZE")
events.shared-highprio-eventsize = 256 (macro name: "MBED_CONF_EVENTS_SHARED_HIGHPRIO_EVENTSIZE")
events.shared-highprio-stacksize = 1024 (macro name: "MBED_CONF_EVENTS_SHARED_HIGHPRIO_STACKSIZE")
events.shared-stacksize = 1024 (macro name: "MBED_CONF_EVENTS_SHARED_STACKSIZE")
<output truncated for brevity>
```
使用 -v 开关包括使用配置参数定义的帮助文本，其中定义了配置参数的值以及其他详细信息。命令 mbed compile --config -v 在与上面相同的应用程序中打印：
```
Configuration parameters
------------------------
Name: cellular.random_max_start_delay
    Description: Maximum random delay value used in start-up sequence in milliseconds
    Defined by: library:cellular
    No value set
Name: cellular.use-apn-lookup
    Description: Use APN database lookup
    Defined by: library:cellular
    Macro name: MBED_CONF_CELLULAR_USE_APN_LOOKUP
    Value: 1 (set by library:cellular)
Name: configuration-store.storage_disable
    Description: Configuration parameter to disable flash storage if present. Default = 0, implying that by default flash storage is used if present.
    Defined by: library:configuration-store
    No value set
<output truncated for brevity>
```
## 在代码中使用配置数据

编译或导出时，配置系统会生成配置参数的 C 预处理器宏定义。配置系统将这些定义写入位于构建目录中的名为 mbed_config.h 的文件中。在编译与目标 K64F 的前一部分相同的示例时，mbed_config.h 文件包含此代码段（请注意，定义的顺序可能不同）：
```
// Automatically generated configuration file.
// DO NOT EDIT, content will be overwritten.
 
#ifndef __MBED_CONFIG_DATA__
#define __MBED_CONFIG_DATA__
 
// Configuration parameters
#define MBED_CONF_CELLULAR_RANDOM_MAX_START_DELAY         0 // set by library:cellular
#define MBED_CONF_CELLULAR_USE_APN_LOOKUP                 1 // set by library:cellular
<file truncated for brevity>
```
配置参数的宏名称是带前缀的名称或由 macro_name 显式指定。配置系统从前缀 MBED_CONF_ 构造一个带前缀的名称，后跟库或 APP 的名称，后跟参数的名称。然后，配置系统将前缀名称大写并将其转换为有效的 C 宏名称。例如，配置系统将库蜂窝中的 random_max_start_delay 配置参数转换为 MBED_CONF_CELLULAR_RANDOM_MAX_START_DELAY。

Mbed OS 构建工具指示编译器处理文件 mbed_config.h，就像它是第一个包含任何 C 或 C++ 源文件一样，因此您不必手动包含 mbed_config.h。

不要手动编辑 mbed_config.h。下次编译或导出应用程序时可能会覆盖它，您将丢失所有更改。

## mbed_app.json，mbed_lib.json 中的配置参数

应用程序可能在应用程序的根目录中有一个 mbed_app.json，在整个应用程序中有许多 mbed_lib.json 文件。如果存在，mbed_app.json 可以覆盖库和目标中定义的配置参数，并定义新的配置参数。

### 覆盖配置参数

配置系统允许用户使用名为 “target_overrides” 的 JSON 对象覆盖任何已定义的配置参数。

“target_overrides” 部分中的键是覆盖适用的目标的名称，或者适用于所有目标的特殊通配符 *。“target_overrides” 部分中的值是将配置参数（由 mbed compile --conifg 打印）映射到新值的对象。请参阅下面的示例 “target_overrides” 部分。
```
"target_overrides": {
    "*": {
        "cellular.random_max_start_delay": "100"
    },
    "K64F": {
        "cellular.use-apn-lookup": false
    }
}
```
使用 mbed compile --config -m LPC1768 检查目标 LPC1768 的配置会导致以下配置：
```
Configuration parameters
------------------------
cellular.random_max_start_delay = 100 (macro name: "MBED_CONF_CELLULAR_RANDOM_MAX_START_DELAY")
cellular.use-apn-lookup = 1 (macro name: "MBED_CONF_CELLULAR_USE_APN_LOOKUP")
<output truncated for brevity>
```
使用 mbed compile --config -m K64F 检查目标 K64F 的配置会导致以下配置：
```
Configuration parameters
------------------------
cellular.random_max_start_delay = 100 (macro name: "MBED_CONF_CELLULAR_RANDOM_MAX_START_DELAY")
cellular.use-apn-lookup = 0 (macro name: "MBED_CONF_CELLULAR_USE_APN_LOOKUP")
<output truncated for brevity>
```
考虑覆盖的顺序是：

1. 库使用 mbed_lib.json 覆盖目标配置。
2. 应用程序使用 mbed_app.json 覆盖目标和库配置
### 定义配置参数

配置系统了解目标，库和应用程序使用名为 “config” 的 JSON 对象定义的配置参数。

例如：
```
{
    "config": {
        "param1": {
            "help": "The first configuration parameter",
            "macro_name": "CUSTOM_MACRO_NAME",
            "value": 0
        },
        "param2": {
            "help": "The second configuration parameter",
            "required": true
        },
        "param3": 10
    }
}
```
您可以通过将其名称指定为键并使用描述对象或值指定其值来定义配置参数。上面的 JSON 片段定义了三个名为param1，param2 和 param3 的配置参数。

上面，使用描述对象定义配置参数 param1 和 param2。描述对象支持以下键：

+ help: 可选的帮助消息，描述参数的用途。
+ value: 一个可选字段，用于定义参数的值。
+ required: 一个可选键，指定参数在编译代码之前是否必须具有值（默认为 false）。使用一个或多个没有值的必需参数编译源树是不可能的。通常，只有在未设置值时，设置为 true 才有用。
+ macro_name: 在此配置参数的编译时定义的宏的可选名称。配置系统自动为配置参数计算出相应的宏名称，但用户可以通过指定 macro_name 来覆盖此自动计算的名称。
您可以使用整数或字符串而不是描述对象（例如上面的 param3）按值定义宏。按值定义参数等效于使用描述对象定义的配置参数，其中键值设置为代替描述对象的值，键帮助未设置，键 macro_name 未设置，键所需设置为 false。

     **注意**: config 中参数的名称不能包含点（.）字符。

配置系统在每个参数的名称后附加前缀，因此库中具有相同名称的参数不会与目标或其他库中的同名参数冲突。前缀是：

|位置	|字首|
|-|:-|
|目标	|target.|
|任何库	|库的名称，在 mbed_lib.json 的名称部分中找到，后跟一个点（.）|
|应用程序	|app.|
## mbed_lib.json 格式规范

mbed_lib.json 是一个 JSON 格式的文档，包含一个根 JSON 对象。此对象中的键是部分。请参阅以下允许的部分及其含义：

|部件	|必要	|含义|
|-|:-:|-|
|name	|是	|库的名称。必须是独特的。可能不是 app 或 target。|
|macros	|否	|要在 mbed_config.h 中定义的宏列表。|
|config	|否	|定义用于此库的配置参数。|
|arget_overrides	|否	|覆盖当前库的目标配置参数和配置参数。|
以下是一个示例库 mylib。
```
{
    "name": "mylib",
    "config": {
        "buffer_size": 1024,
        "timer_period": {
            "help": "The timer period (in us)",
            "macro_name": "INTERNAL_GPTMR_PERIOD",
            "required": true
        },
        "queue_size": {
            "help": "Size of event queue (entries)",
            "value": 10
        }
    },
    "macros": ["MYMOD_MACRO1", "MYMOD_MACRO2=\"TEST\""],
    "target_overrides": {
        "K64F": {
             "timer_period": 100,
             "queue_size": 40
        },
        "NXP": {
             "queue_size": 20,
             "buffer_size": 128,
             "target.features_add": ["IPV4"]
        }
    }
}
```
在这个 JSON 文件中：

+ name 是库的名称。这是一个必填字段。
+ config 定义库的配置参数，如有关定义配置参数的部分所述。
+ macros 是编译包含此库的应用程序时定义的额外 C 预处理器宏的列表。
+ target_overrides 是一个字典，其中包含配置参数的特定于目标的值。
mylib 中定义的所有配置参数都有一个 mylib. 字首。在 mbed_app.json 中，可以使用名称 mylib.buffer_size 访问 buffer_size。

使用 target_overrides 覆盖参数的值，具体取决于当前的编译目标。配置系统将 target_overrides 中的键与目标标签进行匹配。 （您可以在我们的文档中找到有关添加和配置目标的 Mbed 目标的说明。）如果 target_overrides 中的某个键与其中一个目标标签匹配，则参数值会根据键的值而更改。

mbed_lib.json 覆盖未定义的配置参数是错误的。

### 覆盖目标属性

目标配置包含一组可以通过配置操作的属性。您可以覆盖这些属性，就像它们是正常的配置参数一样。属性可以是累积的，在这种情况下，它们是项目列表。您可以通过使用后缀为 _add 的累积属性的名称覆盖配置参数来添加到累积属性，并从具有后缀 _remove 的累积属性中删除。当您覆盖，添加或减去累积属性时，该值必须是要用，替换或删除定义的项列表。例如，使用以下语法将值 IPV4 添加到目标的功能列表：
```
"target.features_add": ["IPV4"]
```
从累积属性中添加和减去相同的值都是错误的。有关可能覆盖的属性列表，请参阅有关添加和配置目标的文档。

## mbed_app.json 规范

mbed_app.json 可以出现在应用程序的根目录中，也可以指定为 mbed 编译和 mbed 导出的 --app-config 参数的参数。与库配置不同，配置系统在 mbed 编译或 mbed 导出期间仅解释一个 mbed_app.json。与 mbed_lib.json 一样，mbed_app.json 是一个包含根 JSON 对象的 JSON 格式文档。此对象中的键是部分。允许的部分及其含义如下：

|部件	|必要	|含义|
|-|:-:|-|
|artifact_name	|否	|要生成的可执行文件的名称。默认为包含目录的名称。|
|macros	|否	|要在 mbed_config.h 中定义的宏列表。|
|config	|否	|定义用于此库的配置参数。|
|target_overrides	|否	|覆盖目标，库和应用程序配置参数。|
应用程序可以自由地覆盖它所依赖的任何库的配置，以及目标中的配置数据，因此它可以完全控制整个构建的配置。例如，依赖于上面的 mylib 的应用程序中的 mbed_app.json 可能如下所示：
```
{
    "artifact_name": "my-application",
    "config": {
        "welcome_string": {
            "help": "The string printed on the display on start-up",
            "value": "\"Hello!\""
        }
    },
    "target_overrides": {
        "*": {
            "mylib.timer_period": 100
        },
        "NCS36510": {
            "target.mac_addr_high": "0x11223344"
        }
    }
}
```
应用程序可以通过指定包括其前缀的配置参数（例如 mylib.timer_period）来覆盖任何配置参数。如果重写的参数没有前缀，则它会覆盖其自己的 config 部分中的参数。

上面的 mbed_app.json 定义了自己的配置参数（welcome_string），并覆盖了 target（target.mac_addr_high）及其 mylib 依赖项（mylib.timer_period）中的配置：

+ 编译 NCS36510 时，app.welcome_string 为 “Hello！”，target.mac_addr_high 为 “0x11223344”（来自 NCS36510 覆盖），mylib.timer_period 为 100（来自 * 覆盖）。
+ 编译 LPC1768 时，app.welcome_string 为 “Hello！”  和 mylib.timer_period 是 100（也来自 * 覆盖）。
+ 最终工件（二进制）名为 my-application.bin，由 artifact_name 部分指定。
应用程序配置覆盖未定义的配置参数是错误的。