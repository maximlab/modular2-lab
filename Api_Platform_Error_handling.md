## 错误处理

Mbed OS 提供错误代码和错误状态定义以及错误处理 API，用于错误构造，报告和检索先前报告的错误。Mbed OS 还提供函数和宏来生成和定义新的错误状态值，从错误状态值中提取信息并将错误报告给系统。任何软件层（例如应用程序，驱动程序，HAL 和协议栈）都可以使用这些错误处理 API。错误功能还有助于通过 STDOUT 发出错误消息。mbed_error.h 声明了 Mbed OS 提供的错误功能。

从概念上讲，错误处理是 Mbed OS 平台层实现的平台服务。错误处理提供以下内容：

1. 在 mbed_error.h 中提供系统定义的错误代码和状态值
2. 提供用于错误构建，报告和错误历史记录管理的 API。
3. 提供 ISR 安全和线程安全的错误处理 API。
4. 提供扩展错误状态定义的机制。

## 错误状态使用情况

Mbed OS 预定义了一组系统错误，并将错误状态定义为 NEGATIVE 空间中的 32 位有符号整数。mbed_error_status_t 类型表示错误状态值。

您可以使用错误状态：

* 指示函数调用的返回状态。

    + 返回 0（= MBED_SUCCESS）或任何正数都是成功的。
    + 名为 MBED_SUCCESS（= 0）的预定义状态代码可用于指示成功。
* 作为系统错误代码

    + 用于向 OS 错误处理子系统报告错误情况。

## 错误状态类型

Mbed OS 错误状态编码定义了三种类型的错误状态值。请注意，错误状态的类型被编码为 32 位有符号整数。

+ 系统错误 - Mbed-OS 定义的错误代码（请参阅错误代码和错误状态范围）。
+ Posix 错误 - 请参阅 Posix 错误代码支持。
+ 自定义错误 - 请参阅扩展错误代码。

## 错误代码和错误状态范围

对于每种错误状态类型，我们定义了一系列错误代码，这些错误代码构成了 32 位错误状态值的最低有效 16 位。根据错误代码定义，下面是每种错误类型的错误代码范围：

+ Posix 错误代码：1 到 255（有关详细信息，请参阅 Posix 错误代码支持部分）。
+ 系统错误代码：256 到 4095。
+ 自定义错误代码：4096 到 65535。

因此，每种类型的错误状态范围是：

+ Posix 错误状态 - 0xFFFFFFFF 到 0xFFFFFF01 - 这对应于表示为负的 Posix 错误。
+ 系统错误状态 - 0x80XX0100 至 0x80XX0FFF - 这对应于系统错误范围（所有值均为负值）。位 23 - 16 捕获模块类型（标有 XX）。
+ 自定义错误状态 - 0xA0XX1000 到 0xA0XXFFFF - 这对应于自定义错误范围（所有值都为负）。位 23 - 16 捕获模块类型（标有 XX）。

了解术语 “错误代码” 和 “错误状态” 之间的区别非常重要。“错误状态” 是应用程序用于报告错误的 NEGATIVE 空间中的 32 位有符号整数，“错误代码” 是指示错误情况的 32 位错误状态值的最低有效 16 位，例如， 内存不足。所有预定义的错误状态定义均以 MBED_ERROR_ 开头，所有预定义的错误代码定义均以 MBED_ERROR_CODE_ 开头。请注意，在报告或表示系统中的错误时，始终会将错误代码编码为错误状态值。

Mbed OS 系统错误状态值还可以通过在错误状态中编码模块标识符来捕获报告错误的模块，具体取决于错误状态的类型。模块信息作为错误报告的一部分打印到终端。我们提供错误状态值和范围以供参考，但是没有实现应该直接假设或操纵编码中的位字段。使用 Mbed OS 错误处理和报告 API 的实现应该处理错误状态，例如不透明对象，并且应该使用 Mbed OS 提供的宏和函数来操作或解释错误状态值。

## Posix 错误代码支持

Mbed OS 下的许多模块（如文件系统）使用 Posix 错误代码。因此，Mbed OS 错误状态定义也会在新的错误编码方案下捕获 Posix 错误代码。错误代码定义还确保 Posix 错误代码值不与 Mbed 错误代码值重叠。这使得开发人员可以更轻松地将 Posix 错误代码报告给 Mbed OS 错误处理系统。

为了将 Posix 错误代码表示合并到 Mbed OS 中，为 Posix 错误代码分配了一部分错误空间。由于 Mbed OS 错误代码始终为负数，因此我们在错误代码定义中捕获实际 Posix 错误代码的负数。例如，Mbed OS 错误代码空间中的 Posix 错误代码 EPERM 将表示为实际 EPERM 值的负数。这与使用负值的 Mbed OS 错误编码约定一致，但数值（或绝对）值与 Posix 错误代码相同。 另请注意，由于 Posix 错误代码表示为 Posix 错误代码的负数，因此它们无法像 Mbed OS 系统错误代码中那样捕获模块信息。

虽然出于兼容性原因我们支持 Posix 错误代码，但我们强烈建议所有未来的 Mbed OS 专注实现使用 Mbed OS 错误定义，因此报告的错误与 Mbed OS 中的错误报告和处理实现无缝协作。

## 错误上下文捕获

Mbed OS 中的错误处理系统会自动捕获报告到系统中的每个错误的线程上下文。捕获的上下文包括以下信息：

+ 错误状态代码 - 状态代码。
+ 错误地址 - 捕获设置错误调用的返回地址。
+ 错误值 - 调用者在 MBED_ERROR()/ MBED_WARNING() 调用中设置的特定于上下文的值。
+ 线程 ID - 当前线程的 ID；仅当系统使用 RTOS 支持构建时才会捕获此信息。
+ 线程入口地址 - 当前线程的入口函数；仅当系统使用 RTOS 支持构建时才会捕获此信息。
+ 线程栈大小 - 栈大小；仅当系统使用 RTOS 支持构建时才会捕获此信息。
+ 线程栈 mem - 堆栈顶部；仅当系统使用 RTOS 支持构建时才会捕获此信息。
+ 螺纹电流 SP - SP 值（PSP 或 MSP 基于什么是有效的）；仅当系统使用 RTOS 支持构建时才会捕获此信息。
+ 文件名和行号 - 默认情况下，禁用文件名和行号的捕获。如果需要捕获此信息，则需要将配置选项MBED_CONF_PLATFORM_ERROR_FILENAME_CAPTURE_ENABLED 设置为 true。

在致命错误的情况下，STDOUT 会发出此捕获的上下文。如果出现警告，系统会记录该警告，您可以稍后检索它以进行系统诊断，外部报告和调试。有关错误历史记录功能在 Mbed OS 中的工作方式的信息，请参阅错误历史记录部分。错误处理 API 示例还包含有关如何使用错误检索 API 的更多信息。

## 错误报告

Mbed OS 提供了三种使用错误处理实现报告错误的方法：

1. 使用 error() 函数报告致命错误条件 - 这是用于报告致命错误的旧函数。它已被修改为捕获上下文信息，但它不捕获调用者或模块信息的地址。它也不支持报告特定的错误代码。使用此 API 报告错误的任何实现都使用错误状态MBED_ERROR_UNKNOWN。我们强烈建议所有未来的 Mbed OS 专注实现使用 MBED_ERROR()/MBED_ERROR1() 或 MBED_WARNING()/MBED_WARNING1() 宏来报告错误。
2. 使用 MBED_ERROR()/MBED_ERROR1() 宏（请参阅错误处理 API 示例）报告致命错误，增强功能以捕获报告错误的模块。
3. 使用 MBED_WARNING()/MBED_WARNING1() 宏（请参阅错误处理 API 示例）报告具有增强功能的非致命错误，以捕获报告错误的模块。

使用 MBED_ERROR() 或 MBED_ERROR1() 宏报告错误时，错误将记录在具有上下文的错误历史记录中。错误信息打印到 STDOUT，应用程序终止。

请注意，错误函数仅在调试和开发构建中输出错误消息或文件名。

下面是创建 MBED_ERROR1() 调用的终端输出示例。请注意，默认情况下禁用文件名捕获，即使对于调试和开发版本也是如此。您可以通过将配置选项 MBED_CONF_PLATFORM_ERROR_FILENAME_CAPTURE_ENABLED 设置为 true 来启用文件名捕获。
```
++ MbedOS Error Info ++
Error Status: 0x800b0110 Code: 272 Module: 11
Error Message: I2C driver error
Location: 0x8006367
File:main.cpp+222
Error Value: 0xdeaddead
Current Thread: Id: 0x20002080 Entry: 0x80082a1 StackSize: 0x1000 StackMem: 0x20001080 SP: 0x20001fd0
-- MbedOS Error Info --
```
## 在您的实现中构造错误状态值

Mbed OS 为实现构建错误状态值提供必要的功能和宏。有几种方法可以构造错误状态值。

如果您知道报告错误的模块，则可以使用 MBED_MAKE_ERROR() 宏来构造包含模块信息的错误状态。例如，如果要从串行驱动程序报告不受支持的配置错误，可以按如下方式构造错误状态，以捕获模块信息以及特定的错误代码。下面的示例构造一个错误状态值，误代码设置为来自串行驱动程序的 MBED_ERROR_CODE_CONFIG_UNSUPPORTED，由设置为 MBED_MODULE_DRIVER_SERIAL 的模块信息指示。

mbed_error_status_t error = MBED_MAKE_ERROR(MBED_MODULE_DRIVER_SERIAL, MBED_ERROR_CODE_CONFIG_UNSUPPORTED)

可能存在这样的情况：模块可能已调用从其他模块（例如协议栈）导出的 API，但已收到错误状态作为回报。在这些情况下，调用模块不知道哪个较低层引发了错误，但您可能仍想报告错误。在这些情况下，模块可以使用预定义的错误状态，例如 MBED_ERROR_CONFIG_UNSUPPORTED，模块值已设置为 MBED_MODULE_UNKNOWN。

这相当于使用 MODULE_UNKNOWN 定义错误状态。但是，使用预定义值（例如 MBED_ERROR_CONFIG_UNSUPPORTED）可以更方便，更轻松地读取实现。

mbed_error_status_t error = MBED_MAKE_ERROR(MBED_MODULE_UNKNOWN, MBED_ERROR_CODE_CONFIG_UNSUPPORTED)

## 错误历史记录

Mbed OS 中的错误处理实现会跟踪系统中以前的错误。此功能称为错误历史记录，可使用配置值 MBED_CONF_PLATFORM_ERROR_HIST_ENABLED 进行配置。

MBED_CONF_PLATFORM_ERROR_HIST_SIZE 配置系统在其错误历史记录中保留的先前错误的数量。您可以通过将配置选项 MBED_CONF_PLATFORM_ERROR_HIST_ENABLED 设置为 true 来启用错误历史记录。默认情况下，它会跟踪过去的四个错误（如果已启用）。无论是否启用错误历史记录，系统始终会记录系统中发生的第一个和最后一个错误。我们提供 API 以从错误历史记录以及第一个和最后一个错误中检索错误或警告。（有关 API 使用示例，请参阅[错误处理 API 示例部分](https://os.mbed.com/docs/v5.9/reference/error-handling.html#error-handling-api-examples)。）在大多数情况下，调用 MBED_ERROR()/MBED_ERROR1() 会暂停系统。因此，错误历史记录 API 将检索警告，除非您从[错误钩子](https://os.mbed.com/docs/v5.9/reference/error-handling.html#error-hook-for-applications)函数调用这些 API。

请参阅以下链接以了解有关错误历史记录的 API 的更多信息：

[mbed_error.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__error_8h_source.html)

## 扩展错误代码

Mbed OS 应用程序和系统开发人员可能需要定义特定于其应用程序的错误代码。但是，这些错误代码可能不适用于要定义为系统错误代码的更广泛的系统。在这些情况下，应用程序可以使用 MBED_DEFINE_CUSTOM_ERROR() 宏预定义自定义错误代码。MBED_DEFINE_CUSTOM_ERROR() 宏专门定义错误状态值，其类型将是错误状态类型和错误代码范围部分中提到的自定义错误。如果要定义自定义错误代码，我们建议在自定义错误代码定义下的 mbed_error.h 中捕获这些定义。

## 应用程序的错误钩子

当使用 MBED_ERROR() 或 MBED_WARNING() 报告错误时，某些应用程序可能希望执行自定义错误处理。应用程序可以通过使用 mbed_set_error_hook() API 向 Mbed OS 错误处理系统注册错误钩子函数来实现此目的。只要系统处理 MBED_ERROR() 或 MBED_WARNING() 调用，就会使用错误上下文信息调用此函数。应该为重入实现此函数，因为多个线程可能会调用 MBED_ERROR() 或 MBED_WARNING()，这可能导致并行调用错误钩子。

## 错误处理函数参考

以下链接提供了 Mbed OS 为错误定义和处理提供的所有 API 的文档：

[mbed_error.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__error_8h_source.html)

## 错误处理 API 示例

#### 使用 error() 函数

下面的代码使用错误函数来打印致命错误，指示内存不足的情况。
```
void *operator new(std::size_t count) {
    void *buffer = malloc(count);
    if (NULL == buffer) {
        error("Operator new out of memory\r\n");
    }
    return buffer;
}
```
#### 将 MBED_ERROR() 宏与模块信息一起使用

下面的代码使用 MBED_ERROR 宏来打印致命错误，指示模块名称指定为 MODULE_APPLICATION 的无效参数：
```
void receive_data(unsigned char *buffer) {
    if (NULL == buffer) {
        MBED_ERROR( MBED_MAKE_ERROR(MBED_MODULE_APPLICATION, MBED_ERROR_CODE_INVALID_ARGUMENT), "Buffer pointer is Null" );
    }
    // read the data into given buffer
    
}
```
#### 将 MBED_WARNING() 宏与模块信息一起使用并返回 Mbed 错误状态

下面的代码使用 MBED_WARNING 宏来报告无效的配置尝试，模块名称指定为 MBED_MODULE_PLATFORM：
```
mbed_error_status_t configure(int config_value) {
    if (config_value > 10) {
        //Log the fact that a invalid configuration attempt was made and return with error code
        MBED_WARNING( MBED_MAKE_ERROR(MBED_MODULE_PLATFORM, MBED_ERROR_CODE_UNSUPPORTED), "Invalid config parameter" );
        return MBED_ERROR_CODE_UNSUPPORTED;
    }
    
    //configure whatever
 
    return MBED_SUCCESS;
}
```
#### 使用 MBED_ERROR1() 宏

MBED_ERROR1 宏类似于 MBED_ERROR 宏，但它可以采用额外的特定于上下文的参数。错误处理系统还将此值记录为上下文捕获的一部分。下面的代码使用 MBED_ERROR1 宏来打印致命错误，指示内存不足的情况，并将特定于上下文的值作为 MBED_ERROR1 宏的最后一个参数：
```
void receive_data(unsigned char *buffer) {
    if (NULL == buffer) {
        MBED_ERROR1(MBED_MAKE_ERROR(MBED_MODULE_APPLICATION, MBED_ERROR_CODE_INVALID_ARGUMENT), "Buffer pointer is Null", 1024/* Size of allocation which failed */ );
    }
    // read the data into given buffer
    
}
```
#### 使用 MBED_WARNING1() 宏

MBED_WARNING1 宏类似于 MBED_WARNING 宏，但它可以采用其他特定于上下文的参数。错误处理系统还将此值记录为上下文捕获的一部分。下面的代码使用 MBED_WARNING1 宏来报告具有上下文特定值的警告作为 MBED_WARNING1 宏的最后一个参数：
```
mbed_error_status_t configure(int config_value) {
    if (config_value > 10) {
        //Log the fact that a invalid configuration attempt was made and return with error code
        MBED_WARNING1(MBED_MAKE_ERROR(MBED_MODULE_PLATFORM, MBED_ERROR_CODE_UNSUPPORTED), "Invalid config parameter", config_value /* Invalid config value */ );
        return MBED_ERROR_CODE_UNSUPPORTED;
    }
    
    //configure whatever
 
    return MBED_SUCCESS;
}
```
#### 使用没有模块信息的 MBED_WARNING() 宏

下面的代码使用 MBED_WARNING 宏来报告无模块名称的无效配置尝试：
```
mbed_error_status_t configure(int config_value) {
    if (config_value > 10) {
        //Log the fact that a invalid configuration attempt was made and return with error code
        MBED_WARNING1(MBED_ERROR_UNSUPPORTED, "Invalid config value", 0 );
        return MBED_ERROR_UNSUPPORTED;
    }
    
    //configure whatever
 
    return MBED_SUCCESS;
}
```
#### 使用 mbed_get_first_error() 和 mbed_get_first_error_info() 函数检索系统中记录的第一个错误或第一个警告

下面的代码使用 mbed_get_first_error() 和 mbed_get_first_error_info() 函数来检索使用 MBED_WARNING()/MBED_ERROR() 调用记录在系统中的第一个错误或第一个警告：
```
void get_first_error_info() {
    mbed_error_status_t first_error_status = mbed_get_first_error();
    printf("\nFirst error code = %d", MBED_GET_ERROR_CODE(first_error_status))
 
    //Now retrieve more information associated with this error
    mbed_error_ctx first_error_ctx;
    mbed_error_status_t first_error = mbed_get_first_error_info(&first_error_ctx);
}
```
#### 使用 mbed_get_last_error() 和 mbed_get_last_error_info() 函数检索系统中记录的最后一条错误或上一条警告

使用函数 mbed_get_last_error() 和 mbed_get_last_error_info() 来检索使用 MBED_WARNING()/MBED_ERROR() 调用记录在系统中的最后一个错误或上一个警告。请注意，这些调用类似于 mbed_get_first_error() 和 mbed_get_first_error_info() 调用，除了它们在这种情况下检索上一个错误或最后一个警告：
```
void get_last_error_info() {
    mbed_error_status_t last_error_status = mbed_get_last_error();
    printf("\nLast error code = %d", MBED_GET_ERROR_CODE(last_error_status))
 
    //Now retrieve more information associated with this error
    mbed_error_ctx last_error_ctx;
    mbed_error_status_t last_error = mbed_get_last_error_info(&last_error_ctx);
}
```
#### 使用 mbed_get_error_hist_info() 和 mbed_get_error_hist_count() 从错误历史记录中检索错误或警告信息

您可以使用函数 mbed_get_error_hist_info() 从错误历史记录中检索错误或警告信息：
```
void get_error_info_from_hist() {
    //Retrieve error information from error history
    mbed_error_ctx hist_error_ctx;
 
    int num_entries_in_hist = mbed_get_error_hist_count();
    for(int i=0; i<num_entries_in_hist; i++) {
        //Reads the error context information for a specific error from error history, specified by an index(first arg to mbed_get_error_hist_info).
        //index of the error context entry in the history to be retrieved.
        //The number of entries in the error history is configured during build and the max index depends on max depth of error history.
        //index = 0 points to the oldest entry in the history, and index = (max history depth - 1) points to the latest entry in the error history.
        mbed_get_error_hist_info( i, &hist_error_ctx );
        printf("\nError code[%d] = %d", i, MBED_GET_ERROR_CODE(last_error_status))
    }
}
```
#### 使用 mbed_clear_all_errors() 清除错误历史记录

您可以使用函数 mbed_clear_all_errors() 清除错误历史记录中所有当前记录的错误。如果您已经备份了所有当前记录的错误（例如，备份到文件系统或云）并希望捕获新错误，则可以使用此方法：
```
void save_all_errors() {
    //Save the errors first
    save_all_errors();
 
    //We have sent all the current errors to Mbed Cloud. So clear the history so that you can capture next set of warnings or errors.
    mbed_clear_all_errors();
}
```
## 错误处理示例

下面的示例应用程序演示了错误处理 API 的用法。

[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-error-handling/file/34cf6e69b337/main.cpp)                                                                                                 
```
/* mbed Microcontroller Library
 * Copyright (c) 2018 ARM Limited
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
 
#ifdef MBED_TEST_SIM_BLOCKDEVICE
 
// test configuration
#ifndef MBED_TEST_FILESYSTEM
#define MBED_TEST_FILESYSTEM LittleFileSystem
#endif
 
#ifndef MBED_TEST_FILESYSTEM_DECL
#define MBED_TEST_FILESYSTEM_DECL MBED_TEST_FILESYSTEM fs("fs")
#endif
 
#ifndef MBED_TEST_BLOCK_COUNT
#define MBED_TEST_BLOCK_COUNT 64
#endif
 
#ifndef MBED_TEST_SIM_BLOCKDEVICE_DECL
#define MBED_TEST_SIM_BLOCKDEVICE_DECL MBED_TEST_SIM_BLOCKDEVICE fd(MBED_TEST_BLOCK_COUNT*512, 1, 1, 512)
#endif
 
// declarations
#define STRINGIZE(x) STRINGIZE2(x)
#define STRINGIZE2(x) #x
#define INCLUDE(x) STRINGIZE(x.h)
 
#include INCLUDE(MBED_TEST_FILESYSTEM)
#include INCLUDE(MBED_TEST_SIM_BLOCKDEVICE)
 
MBED_TEST_FILESYSTEM_DECL;
MBED_TEST_SIM_BLOCKDEVICE_DECL;
 
/** Test save error log
 */
mbed_error_status_t save_error_history()
{
    mbed_error_status_t status = MBED_SUCCESS;
    
    //Log some errors
    MBED_WARNING1(MBED_ERROR_TIME_OUT, "Timeout error", 1 );
    MBED_WARNING1(MBED_ERROR_ALREADY_IN_USE, "Already in use error", 2 );
    MBED_WARNING1(MBED_ERROR_UNSUPPORTED, "Not supported error", 3 );
    MBED_WARNING1(MBED_ERROR_ACCESS_DENIED, "Access denied error", 4 );
    MBED_WARNING1(MBED_ERROR_ITEM_NOT_FOUND, "Not found error", 5 );
    
    int error = 0;
    
    error = MBED_TEST_FILESYSTEM::format(&fd);
    if(error < 0) {
        printf("save_error_history: Failed formatting");
        status = MBED_ERROR_FAILED_OPERATION;
    } else {
        error = fs.mount(&fd);
        if(error < 0) {
            printf("save_error_history: Failed mounting fs");
            status = MBED_ERROR_FAILED_OPERATION;
        } else {
            if(MBED_SUCCESS != mbed_save_error_hist("/fs/errors.txt")) {
                printf("save_error_history: Failed saving error history");
                status = MBED_ERROR_FAILED_OPERATION;
            } else {
                FILE *error_file = fopen("/fs/errors.txt", "r");
                if(error_file == NULL) {
                    printf("save_error_history: Unable to find error log in fs");
                } else {
                    char buff[64] = {0};
                    while (!feof(error_file)){
                      int size = fread(&buff[0], 1, 15, error_file);
                      fwrite(&buff[0], 1, size, stdout);
                    }
                    fclose(error_file);
                }
            }
            
            error = fs.unmount();
            if(error < 0) {
                printf("save_error_history: Failed unmounting fs");
                status = MBED_ERROR_FAILED_OPERATION;
            }
        }
    }
    
    return status;
}
 
#endif
 
static Semaphore    callback_sem;
void my_error_hook(const mbed_error_ctx *error_ctx)
{
    //Fire the semaphore
    callback_sem.release();
}
 
int main()
{
    mbed_error_ctx error_ctx = {0};
    
    printf("\nError Handling and Error Coding Demo...");    
    
    //Use mbed_clear_all_errors to clear the currently logged warnings/errors and reset error count to 0
    mbed_clear_all_errors();
    
    //Use MBED_WARNING macros to log an error which is not catastrophic/fatal. This would log an error but would not halt the system. 
    //The erroring module is set to MBED_MODULE_APPLICATION and error code is set to MBED_ERROR_CODE_INVALID_ARGUMENT
    MBED_WARNING1(MBED_MAKE_ERROR(MBED_MODULE_APPLICATION, MBED_ERROR_CODE_INVALID_ARGUMENT), "System type error", 0x1234 );
    
    //Here the erroring module is set to MBED_MODULE_PLATFORM and error code is set to MBED_ERROR_CODE_ALREADY_IN_USE
    MBED_WARNING1(MBED_MAKE_ERROR(MBED_MODULE_PLATFORM, MBED_ERROR_CODE_ALREADY_IN_USE), "Already in use error", 0xABCD );
    
    //Now that we logged the error retrieve them and ensure they are logged correctly
    //Use mbed_get_last_error_info API to retrieve the very first error we logged. In this case
    //it would be MBED_ERROR_INVALID_ARGUMENT since we cleared all the previous in the start of this app
    mbed_error_status_t status = mbed_get_first_error_info( &error_ctx );
    if(error_ctx.error_value != 0x1234) {
        printf("\nERROR: Invalid Error Value Detected");
        return -1;
    }
    if(MBED_GET_ERROR_MODULE(error_ctx.error_status) != MBED_MODULE_APPLICATION) {
        printf("\nERROR: Invalid Error Module Detected");
        return -1;
    }
    if(MBED_GET_ERROR_CODE(error_ctx.error_status) != MBED_ERROR_CODE_INVALID_ARGUMENT) {
        printf("\nERROR: Invalid Error Code Detected");
        return -1;
    }
    
    //Use mbed_get_last_error_info API to retrieve the very first error we logged. In this case
    //it would be MBED_ERROR_ALREADY_IN_USE since we cleared all the previous in the start of this app
    status = mbed_get_last_error_info( &error_ctx );
    if(status !=MBED_SUCCESS || error_ctx.error_value != 0xABCD) {
        printf("\nERROR: Invalid Error Value Detected");
        return -1;
    }
    if(MBED_GET_ERROR_MODULE(error_ctx.error_status) != MBED_MODULE_PLATFORM) {
        printf("\nERROR: Invalid Error Module Detected");
        return -1;
    }
    if(MBED_GET_ERROR_CODE(error_ctx.error_status) != MBED_ERROR_CODE_ALREADY_IN_USE) {
        printf("\nERROR: Invalid Error Code Detected");
        return -1;
    }
    
    printf("\nError Status and Context capture successful");
 
#if MBED_CONF_PLATFORM_ERROR_HIST_ENABLED    
    //Add 4 error entries
    MBED_WARNING1(MBED_ERROR_TIME_OUT, "Timeout error", 100 );
    MBED_WARNING1(MBED_ERROR_FAILED_OPERATION, "Already in use error", 101 );
    MBED_WARNING1(MBED_ERROR_UNSUPPORTED, "Not supported", 102 );
    MBED_WARNING1(MBED_ERROR_ACCESS_DENIED, "Access denied", 103 );
        
    //Retrieve the logged errors from error history
    status = mbed_get_error_hist_info( 0, &error_ctx );
    if(status !=MBED_SUCCESS || error_ctx.error_status != MBED_ERROR_TIME_OUT) {
        printf("\nERROR: Invalid Error Status Detected for mbed_get_error_hist_info, expected MBED_ERROR_TIME_OUT");
        return -1;
    }
    
    status = mbed_get_error_hist_info( 1, &error_ctx );
    if(status !=MBED_SUCCESS || error_ctx.error_status != MBED_ERROR_FAILED_OPERATION) {
        printf("\nERROR: Invalid Error Status Detected for mbed_get_error_hist_info, expected MBED_ERROR_FAILED_OPERATION");
        return -1;
    }
    
    status = mbed_get_error_hist_info( 2, &error_ctx );
    if(status !=MBED_SUCCESS || error_ctx.error_status != MBED_ERROR_UNSUPPORTED) {
        printf("\nERROR: Invalid Error Status Detected for mbed_get_error_hist_info, expected MBED_ERROR_UNSUPPORTED");
        return -1;
    }
    
    status = mbed_get_error_hist_info( 3, &error_ctx );
    if(status !=MBED_SUCCESS || status !=MBED_SUCCESS || error_ctx.error_status != MBED_ERROR_ACCESS_DENIED) {
        printf("\nERROR: Invalid Error Status Detected for mbed_get_error_hist_info, expected MBED_ERROR_ACCESS_DENIED");
        return -1;
    }
    
    printf("\nError history capture successful");
    
#ifdef MBED_TEST_SIM_BLOCKDEVICE    
    if( MBED_SUCCESS != save_error_history()) {
        printf("\nERROR: Saving Error history failed");
        return -1;
    }
    
    printf("\nSaving error history to filesystem successful");
#endif //#ifdef MBED_TEST_SIM_BLOCKDEVICE
#endif //#if MBED_CONF_PLATFORM_ERROR_HIST_ENABLED
    //Use error hook functionality
    if(MBED_SUCCESS != mbed_set_error_hook(my_error_hook)) {
        printf("\nERROR: Registering error hook failed");
        return -1;
    }
    
    MBED_WARNING1(MBED_ERROR_INVALID_ARGUMENT, "Test for error hook", 1234);
    int32_t sem_status = callback_sem.wait(5000);
    
    if(sem_status <= 0) {
        printf("\nERROR: Error hook failed");
        return -1;
    }
    
    printf("\nError hook successful\n");
    
    //Wait 1 secs to flush all the printfs out
    wait(1.0);
    
    MBED_ERROR1(MBED_MAKE_ERROR(MBED_MODULE_DRIVER_I2C, MBED_ERROR_OPERATION_PROHIBITED), "I2C driver error", 0xDEADDEAD );
}
``` 
## Mbed OS 定义的错误代码和描述列表

以下是预定义的 Mbed 系统错误代码及其说明：
```
MBED_ERROR_CODE_UNKNOWN                    Unknown error
MBED_ERROR_CODE_INVALID_ARGUMENT           Invalid Argument
MBED_ERROR_CODE_INVALID_DATA               Invalid data
MBED_ERROR_CODE_INVALID_FORMAT             Invalid format
MBED_ERROR_CODE_INVALID_INDEX              Invalid Index
MBED_ERROR_CODE_INVALID_SIZE               Inavlid Size 
MBED_ERROR_CODE_INVALID_OPERATION          Invalid Operation 
MBED_ERROR_CODE_NOT_FOUND                  Not Found 
MBED_ERROR_CODE_ACCESS_DENIED              Access Denied 
MBED_ERROR_CODE_NOT_SUPPORTED              Not supported 
MBED_ERROR_CODE_BUFFER_FULL                Buffer Full 
MBED_ERROR_CODE_MEDIA_FULL                 Media/Disk Full 
MBED_ERROR_CODE_ALREADY_IN_USE             Already in use 
MBED_ERROR_CODE_TIMEOUT                    Timeout error 
MBED_ERROR_CODE_NOT_READY                  Not Ready 
MBED_ERROR_CODE_FAILED_OPERATION           Requested Operation failed 
MBED_ERROR_CODE_OPERATION_PROHIBITED       Operation prohibited 
MBED_ERROR_CODE_OPERATION_ABORTED          Operation failed 
MBED_ERROR_CODE_WRITE_PROTECTED            Attempt to write to write-protected resource 
MBED_ERROR_CODE_NO_RESPONSE                No response 
MBED_ERROR_CODE_SEMAPHORE_LOCK_FAILED      Sempahore lock failed 
MBED_ERROR_CODE_MUTEX_LOCK_FAILED          Mutex lock failed 
MBED_ERROR_CODE_SEMAPHORE_UNLOCK_FAILED    Sempahore unlock failed 
MBED_ERROR_CODE_MUTEX_UNLOCK_FAILED        Mutex unlock failed 
MBED_ERROR_CODE_CRC_ERROR                  CRC error or mismatch 
MBED_ERROR_CODE_OPEN_FAILED                Open failed 
MBED_ERROR_CODE_CLOSE_FAILED               Close failed 
MBED_ERROR_CODE_READ_FAILED                Read failed 
MBED_ERROR_CODE_WRITE_FAILED               Write failed 
MBED_ERROR_CODE_INITIALIZATION_FAILED      Initialization failed 
MBED_ERROR_CODE_BOOT_FAILURE               Boot failure 
MBED_ERROR_CODE_OUT_OF_MEMORY              Out of memory 
MBED_ERROR_CODE_OUT_OF_RESOURCES           Out of resources 
MBED_ERROR_CODE_ALLOC_FAILED               Alloc failed 
MBED_ERROR_CODE_FREE_FAILED                Free failed 
MBED_ERROR_CODE_OVERFLOW                   Overflow error 
MBED_ERROR_CODE_UNDERFLOW                  Underflow error 
MBED_ERROR_CODE_STACK_OVERFLOW             Stack overflow error 
MBED_ERROR_CODE_ISR_QUEUE_OVERFLOW         ISR queue overflow 
MBED_ERROR_CODE_TIMER_QUEUE_OVERFLOW       Timer Queue overflow 
MBED_ERROR_CODE_CLIB_SPACE_UNAVAILABLE     Standard library error - Space unavailable 
MBED_ERROR_CODE_CLIB_EXCEPTION             Standard library error - Exception 
MBED_ERROR_CODE_CLIB_MUTEX_INIT_FAILURE    Standard library error - Mutex Init failure 
MBED_ERROR_CODE_CREATE_FAILED              Create failed 
MBED_ERROR_CODE_DELETE_FAILED              Delete failed 
MBED_ERROR_CODE_THREAD_CREATE_FAILED       Thread Create failed 
MBED_ERROR_CODE_THREAD_DELETE_FAILED       Thread Delete failed 
MBED_ERROR_CODE_PROHIBITED_IN_ISR_CONTEXT  Operation Prohibited in ISR context 
MBED_ERROR_CODE_PINMAP_INVALID             Pinmap Invalid 
MBED_ERROR_CODE_RTOS_EVENT                 Unknown Rtos Error 
MBED_ERROR_CODE_RTOS_THREAD_EVENT          Rtos Thread Error 
MBED_ERROR_CODE_RTOS_MUTEX_EVENT           Rtos Mutex Error 
MBED_ERROR_CODE_RTOS_SEMAPHORE_EVENT       Rtos Semaphore Error 
MBED_ERROR_CODE_RTOS_MEMORY_POOL_EVENT     Rtos Memory Pool Error 
MBED_ERROR_CODE_RTOS_TIMER_EVENT           Rtos Timer Error 
MBED_ERROR_CODE_RTOS_EVENT_FLAGS_EVENT     Rtos Event flags Error 
MBED_ERROR_CODE_RTOS_MESSAGE_QUEUE_EVENT   Rtos Message queue Error 
MBED_ERROR_CODE_DEVICE_BUSY                Device Busy 
MBED_ERROR_CODE_CONFIG_UNSUPPORTED         Configuration not supported 
MBED_ERROR_CODE_CONFIG_MISMATCH            Configuration mismatch 
MBED_ERROR_CODE_ALREADY_INITIALIZED        Already initialzied 
MBED_ERROR_CODE_HARDFAULT_EXCEPTION        HardFault exception 
MBED_ERROR_CODE_MEMMANAGE_EXCEPTION        MemManage exception 
MBED_ERROR_CODE_BUSFAULT_EXCEPTION         BusFault exception 
MBED_ERROR_CODE_USAGEFAULT_EXCEPTION       UsageFault exception
```
请注意，系统定义的错误代码将来可能会扩展，因为新的错误方案被识别并合并到 Mbed OS 错误处理系统中。

对于上述每个错误代码，为了方便而预先定义了模块信息设置为 MBED_MODULE_UNKNOWN 的相应系统错误状态值，以及在模块信息未知时报告错误的实现（例如，来自模块未知的异常处理程序）。

有关错误代码定义的其他信息，请参阅以下 Doxygen 文件：

[mbed_error.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__error_8h_source.html)

相关内容

调试和开发[构建配置文件](https://os.mbed.com/docs/v5.9/tools/build-profiles.html)。