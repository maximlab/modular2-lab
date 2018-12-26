## Kernel 接口函数
内核命名空间实现了读取 RTOS 信息的功能。目前它实现了一个函数来读取当前的 RTOS 内核毫秒刻度计数。

## Kernel 名称空间参考
[rtos::Kernel 名称空间参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/namespacertos_1_1_kernel.html)

## get_ms_count() 示例
内核实现了一个名为 get_ms_count() 的函数来读取当前 RTOS 内核的毫秒刻度计数。下面的代码片段演示了如何使用 get_ms_count() 函数来计算已用时间：
```
void send_data()
{
    // 64-bit time doesn't wrap for half a billion years, at least
    uint64_t now = Kernel::get_ms_count();
    //do some operations
    // ...
 
    uint64_t later = Kernel::get_ms_count();
 
    //calculate millisecs elapsed
    uint64_t elapsed_ms = later - now;
}
```