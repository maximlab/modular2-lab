## 断言

Mbed OS 提供了一组宏，用于计算表达式并在表达式求值为 false 时输出错误消息。有两种类型的宏，一种用于在运行时评估表达式，另一种用于编译时评估。mbed_assert.h 定义了这些宏。

## 断言宏参考

[mbed_assert.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__assert_8h_source.html)

## 断言示例

您可以使用 MBED_ASSERT 宏来对表达式进行运行时评估。如果评估失败，则会以下面的格式向 STDIO 输出错误消息。
```
mbed assertation failed: <EVALUATED EXPRESSION>, file: <FILE NAME>, line <LINE NUMBER IN FILE>
```
请注意，MBED_ASSERT 宏在调试和开发构建配置文件中可用，但在发布版本配置文件中不可用。

下面的函数使用 MBED_ASSERT 来验证指向 serial_t 对象的指针。
```
uint8_t serial_tx_active(serial_t *obj) {
    MBED_ASSERT(obj);
    ...
}
```
您可以使用 MBED_STATIC_ASSERT 宏进行表达式的编译时评估。如果评估失败，则会打印传入的错误消息，并且编译失败。

以下函数使用 MBED_STATIC_ASSERT 来验证 equeue_timer 结构的大小。
```
void equeue_tick_init() {
    MBED_STATIC_ASSERT(sizeof(equeue_timer) >= sizeof(Timer),"The equeue_timer buffer must fit the class Timer");
    ...
}
```
相关内容

[构建配置文档](https://os.mbed.com/docs/v5.9/tools/build-profiles.html)。