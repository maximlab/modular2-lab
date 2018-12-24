## 平台

平台配置允许自定义平台级 OS 选项。这些选项包括 STDIO 的错误处理属性和串行通信配置设置。它们在平台之外工作，因为它们影响系统级 printf 调用，而不是 Serial 对象，但 default-serial-baud-rate 除外。

以下是 mbed compile --config -v 生成的平台配置参数的完整列表。有关如何使用或覆盖这些设置的详细信息，请参阅配置系统文档。
```
Configuration parameters
------------------------
 
Name: platform.default-serial-baud-rate
    Description: Default baud rate for a Serial or RawSerial instance (if not specified in the constructor)
    Defined by: library:platform
    Macro name: MBED_CONF_PLATFORM_DEFAULT_SERIAL_BAUD_RATE
    Value: 9600 (set by library:platform)
Name: platform.error-all-threads-info
    Description: Reports all the threads in the system as part of error report.
    Defined by: library:platform
    No value set
Name: platform.error-filename-capture-enabled
    Description: Enables capture of filename and line number as part of error context capture, this works only for debug and develop builds. On release builds, filename capture is always disabled
    Defined by: library:platform
    No value set
Name: platform.error-hist-enabled
    Description: Enable for error history tracking.
    Defined by: library:platform
    No value set
Name: platform.error-hist-size
    Description: Set the number of most recent errors the system keeps in its history, needs error-hist-enabled set to true for this to work.
    Defined by: library:platform
    Macro name: MBED_CONF_PLATFORM_ERROR_HIST_SIZE
    Value: 4 (set by library:platform)
Name: platform.force-non-copyable-error
    Description: Force compile time error when a NonCopyable object is copied
    Defined by: library:platform
    No value set
Name: platform.max-error-filename-len
    Description: Sets the maximum length of buffer used for capturing the filename in error context. This needs error-filename-capture-enabled feature.
    Defined by: library:platform
    Macro name: MBED_CONF_PLATFORM_MAX_ERROR_FILENAME_LEN
    Value: 16 (set by library:platform)
Name: platform.poll-use-lowpower-timer
    Description: Enable use of low power timer class for poll(). May cause missing events.
    Defined by: library:platform
    No value set
Name: platform.stdio-baud-rate
    Description: Baud rate for stdio
    Defined by: library:platform
    Macro name: MBED_CONF_PLATFORM_STDIO_BAUD_RATE
    Value: 9600 (set by library:platform)
Name: platform.stdio-buffered-serial
    Description: Use UARTSerial driver to obtain buffered serial I/O on stdin/stdout/stderr. If false, unbuffered serial_getc and serial_putc are used directly.
    Defined by: library:platform
    No value set
Name: platform.stdio-convert-newlines
    Description: Enable conversion to standard newlines on stdin/stdout/stderr
    Defined by: library:platform
    No value set
Name: platform.stdio-convert-tty-newlines
    Description: Enable conversion to standard newlines on any tty FILE stream
    Defined by: library:platform
    No value set
Name: platform.stdio-flush-at-exit
    Description: Enable or disable the flush of standard I/O's at exit.
    Defined by: library:platform
    Macro name: MBED_CONF_PLATFORM_STDIO_FLUSH_AT_EXIT
    Value: 1 (set by library:platform)
```