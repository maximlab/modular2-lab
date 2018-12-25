## RTOS

### 线程内存模型

Mbed OS 中的所有线程共享一个全局堆。默认情况下，mbed OS 为全局堆中的线程栈动态分配内存。用户生成的线程栈可以从其他内存区域分配。全局堆的大小取决于编译器。使用 IAR 进行编译时，堆大小是静态的，并且对于 Mbed OS 中的每个目标，堆大小是不同的。您可以在嵌套在目标目录中的 IAR 链接器配置文件中找到它。例如，您可以找到 K66F 的链接器配置文件。 对于 GCC 和 ARM 编译器，堆大小是基于 RAM 使用的动态。

### 默认线程

默认情况下，启动后会运行四个线程：ISR/调度程序线程，空闲线程，计时器线程和主应用程序线程。组合起来，空闲线程，计时器线程和 ISR/调度程序线程消耗 2千字节的 RAM。 用户无法修改这些。您可以使用 Mbed 配置系统扩展或减小主应用程序线程堆栈的大小。

以下是由 mbed compile --config -v 生成的 RTOS 配置参数的完整列表。有关如何使用或覆盖这些设置的详细信息，请参阅配置系统文档。

## RTOS 配置参数
```
Configuration parameters
------------------------
 
Name: rtos.present
    Defined by: library:rtos
    Macro name: MBED_CONF_RTOS_PRESENT
    Value: 1 (set by library:rtos)
```
## EventQueue 配置参数
```
Name: events.present
    Defined by: library:events
    Macro name: MBED_CONF_EVENTS_PRESENT
    Value: 1 (set by library:events)
Name: events.shared-dispatch-from-application
    Description: No thread created for shared event queue - application will call dispatch from another thread (eg dispatch_forever at end of main)
    Defined by: library:events
    No value set
Name: events.shared-eventsize
    Description: Event buffer size (bytes) for shared event queue
    Defined by: library:events
    Macro name: MBED_CONF_EVENTS_SHARED_EVENTSIZE
    Value: 256 (set by library:events)
Name: events.shared-highprio-eventsize
    Description: Event buffer size (bytes) for shared high-priority event queue
    Defined by: library:events
    Macro name: MBED_CONF_EVENTS_SHARED_HIGHPRIO_EVENTSIZE
    Value: 256 (set by library:events)
Name: events.shared-highprio-stacksize
    Description: Stack size (bytes) for shared high-priority event queue thread
    Defined by: library:events
    Macro name: MBED_CONF_EVENTS_SHARED_HIGHPRIO_STACKSIZE
    Value: 1024 (set by library:events)
Name: events.shared-stacksize
    Description: Stack size (bytes) for shared event queue thread
    Defined by: library:events
    Macro name: MBED_CONF_EVENTS_SHARED_STACKSIZE
    Value: 1024 (set by library:events)
Name: events.use-lowpower-timer-ticker
    Description: Enable use of low power timer and ticker classes in non-RTOS builds. May reduce the accuracy of the event queue. In RTOS builds, the RTOS tick count is used, and this configuration option has no effect.
    Defined by: library:events
    No value set
```