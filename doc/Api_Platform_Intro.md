## 平台概述

平台模块的作用是在不同的标准库和工具链之上提供通用 MCU 管理基础架构，一些通用数据结构和一致的用户体验。此页面包含有关这些主题的参考资料。

## 通用 MCU 管理基础设施

Mbed OS 通过使用多个范围锁和多个全局 API 简化了 MCU 管理。

锁，DeepSleepLock 和 CriticalSectionLock 使用 RAII 创建一个范围，在该范围内保持适当的锁；这些锁获取操作是它们的构造函数，它们的释放操作是它们的析构函数。这使用核心 C++ 语言特性，对象生存期和范围退出解构，以消除大多数资源泄漏并降低程序复杂性。DeepSleepLock 可防止 MCU 在其处于活动状态时进行深度睡眠，而 CriticalSectionLock 可防止 MCU 处于活动状态时进行抢占。由于这些关键部分或深度睡眠锁定的获取不会失败，因此这两个类都不会引发异常。

Mbed OS 还为睡眠和抢占全局资源提供全局 API。PowerManagement 模块包括现在进入休眠状态的功能，等待模块包括现在抢占的功能。

+ Wait: 一种提供简单等待功能的 API。如果当前线程被阻止，这些等待功能与 RTOS 集成以安排另一个线程。如果所有线程都被阻塞，则空闲线程将通过使 MCU 进入休眠状态来节省电量。
+ CriticalSectionLock: 一个对象，它建立临界区的开头，并在当前作用域退出时使用 RAII 来禁用和恢复中断状态。
+ Power management: 用于控制睡眠模式的 API。此 API 的用户配置 MCU 在空闲时进入的睡眠状态，此时所有内容都被阻止。
+ DeepSleepLock: 阻止范围内睡眠的类。例如，使用此类可防止配置的睡眠模式干扰快速或低延迟通信通道。
## 常见的数据结构

Mbed OS 提供 CircularBuffer 和 ATCmdParser，因为它们是嵌入式系统中常用的实用程序。

+ CircularBuffer: 提供 API 以便以中断安全方式从缓冲区推送和弹出数据的类。
+ ATCmdParser: Mbed OS 兼容的 AT 命令解析器和序列化器。

## C++ 工程扩展

Mbed OS 包含一些为嵌入式系统开发量身定制的便捷类。这些是 Callback，Error 和 NonCopyable 类。

+ Callback: 在自己的上下文中执行用户代码的 API。许多其他 Mbed OS API 通过回调执行构建在 Callback API 上。
+ Time: C 编程语言的标准库中的一组函数，实现日期和时间操作操作。
+ Error: 生成致命运行时错误的函数。
+ NonCopyable: 将类标记为不支持复制操作的 API。如果复制对象，则会产生编译时错误。

## 回调

回调是用户提供的功能，用户可以将其传递给 API。回调允许 API 在其自己的上下文中执行用户代码。

例如，以下代码允许用户在串行线路接收数据时提供自定义响应：
```
// Create a serial object
Serial serial(USBTX, USBRX);
 
// A function that echoes any received data back
 void echo() {
    while (serial.readable()) {
         serial.putc(serial.getc());
    }
 }
 
 int main(void) {
     // Call our function echo whenever the serial line receives data
     serial.attach(&echo, Serial::RxIrq);
 }
```
Callback 类管理 C/C++ 函数指针，所以你不必这样做。如果您问自己为什么要使用 Callback 类，则应阅读状态的重要性部分。

### 你为什么要使用 Callbacks？

API 开发人员很难支持所有标准 C++ 函数类型。API 开发人员必须考虑状态，C++ 函数对象，const 正确性和 volatile 异常。

状态很重要，因此 API 开发人员必须支持带有状态的 C 风格函数指针或 C++ 成员函数指针。无状态回调也很常见，但是将无状态回调作为成员函数函数传递需要编写大量的样板代码并实例化一个空类。此外，API 开发人员还必须支持标准函数指针。

另一种常见的设计模式是函数对象，这是一个覆盖函数调用操作符的类。用户可以将函数对象作为 C++ 成员函数指针传递，C++ 需要大量的重载来支持所有标准函数类型。期望新的库作者将所有这些重载添加到可以接收回调的每个函数中是不合理的。

一个有用的 C++ 特性是编译时 const 正确性检查，当回调与状态组合时会增加 API 复杂性。为了允许用户充分利用 const 正确性检查，C++ API 必须支持成员函数指针的 const 和非 const 版本。

另一个有用的 C++ 特性是 volatile-correctness。当需要 volatile 正确性时，我们希望用户在非易失性类中隐藏 volatile 成员。

C++ 提供了将这种复杂性委托给单个类的工具。这个类是 Callback 类。C++ 11 引入的 std :: function 类的用户应熟悉 Callback 类，并且可用于旧版本的 C++。

### 状态的重要性

回调可能有两个重要的信息，即要执行的代码和与回调相关的状态。

常见的 API 设计错误是使用不允许用户将状态附加到回调的回调类型。最常见的例子是一个简单的 C 函数指针：
```
class ADC {
public:
    // Here, the adc_callback_t type is a function that takes in data
    typedef void (*adc_callback_t)(float data);
 
 
    // In this example, the ADC read function calls the user-provided callback
    // when data is available.
    void attach(adc_callback_t cb);
};
```
此 API 对于简单应用程序已足够，但在有多个可用 ADC 模块时会崩溃。当用户尝试为多个回调重用相同的过程时，此问题变得尤为明显。

例如，考虑将低通滤波器应用于两个不同的 ADC 模块：
```
// Here is a small running-average low-pass filter.
float low_pass_result;
void low_pass_step(float data) {
     low_pass_result = low_pass_result*0.99 + data*0.01;
}
 
// Our two adc modules
ADC adc1;
ADC adc2;
 
int main() {
    adc1.attach(low_pass_step);
 
    // Problem! Now both low pass filters share the same state!
    adc2.attach(low_pass_step);
}
```
没有状态，回调构成不佳。在C中，通过向函数指针添加 “state” 参数，并在注册回调时传递 opaque “state” 来解决此问题。

这是使用状态的附加参数的低通示例。
```
class ADC {
   public:
   // Here, the adc_callback_t type is a function that takes in data, as well as a pointer for state
    template <typename T>
    typedef void (*adc_callback_t)(T *state, float data);
 
 
    // In this example, the ADC read function calls the user-provided callback
    // when data is available.
    template <typename T>
    void attach(adc_callback_t<T> cb, T *state);
};
 
// Here is a small running-average low-pass filter.
void low_pass_step(float *result, float data) {
     *result = *result*0.99 + data*0.01;
}
 
// Our two adc modules
ADC adc1;
ADC adc2;
 
// Our two low-pass filter results
float low_pass_result1;
float low_pass_result2;
 
int main() {
    adc1.attach(low_pass_step, &low_pass_result1);
 
    // Register a second low pass filter, no more issues!
    adc2.attach(low_pass_step, &low_pass_result2);
}
```
C++ 的核心功能之一是在类中封装这个 “状态”，修改状态的操作在类中表示为成员函数。成员函数指针与标准函数指针不兼容。 Callback 类允许API作者实现接受回调的单个接口，并且用户可以提供 C 函数和状态或 C++ 成员函数和对象，而无需 API 作者的特殊考虑。

这是使用回调类重写的低通滤波器示例：
```
class ADC {
public:
    // In this example, the ADC read function calls the user-provided callback
    // when data is available.
    void attach(Callback<void(float)> cb);
};
 
class LowPass {
   float result;
 
public:
    // Move the low pass filter implementation to the ADC module
    void step(float data) {
        result = result*0.99 + data*0.01;
    }
};
 
 
// Our two adc modules
ADC adc1;
ADC adc2;
 
// Our two low-pass filters
LowPass low_pass1;
LowPass low_pass2;
 
int main() {
    adc1.attach(callback(&low_pass1, &LowPass::step));
    adc2.attach(callback(&low_pass2, &LowPass::step));
}
```