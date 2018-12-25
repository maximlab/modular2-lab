## Wait

等待函数提供简单的等待功能。OS 调度程序将当前线程置于等待状态，允许另一个线程执行。更好的是：如果没有其他线程处于就绪状态，它可以让整个微控制器进入休眠状态，从而节省能源。

## 避免操作系统延迟

当你调用 wait 时，你的主板的 CPU 将在 RTOS 中睡眠整整几毫秒，然后根据需要旋转以弥补一毫秒的剩余部分。但是，它会在整个持续时间内阻止平台深度睡眠。

## 等待功能参考

[mbed_wait_api.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__wait__api_8h_source.html)

## 示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/wait_ex_1/file/7d249aa3d880/main.cpp)                                                                                              
```
 
 #include "mbed.h"
 
 DigitalOut heartbeat(LED1);
 
 int main() {
     while (1) {
         heartbeat = 1;
         wait(0.5);
         heartbeat = 0;
         wait(0.5);
     }
 }
``` 
相关内容

[RTOS](https://os.mbed.com/docs/v5.9/reference/rtos.html) 概述。