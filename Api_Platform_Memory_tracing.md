## 内存跟踪

Mbed OS 提供了一组函数，可用于研究软件的运行时内存分配模式：代码的哪些部分分配和释放内存以及需要多少内存。

您必须定义 MBED_MEM_TRACING_ENABLED 宏以启用内存跟踪。

您可以使用 mbed_mem_trace_set_callback API 来设置内存跟踪的回调。每次调用标准分配函数（例如 malloc，realloc，calloc和 free）时都会调用回调。

有关如何使用运行时内存跟踪来使用优化内存的分步指南，请参阅我们的运行时内存跟踪教程。

## 内存跟踪函数参考

[mbed_mem_trace.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__mem__trace_8h_source.html)

## 内存跟踪示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/memory_tracing_example/file/168ab14e6694/main.cpp)       
```
#include <stdlib.h>
#include "mbed.h"
#include "mbed_mem_trace.h"
 
 
int main() {
    mbed_mem_trace_set_callback(mbed_mem_trace_default_callback);
    while (true) {
        void *p = malloc(50);
        wait(0.5);
        free(p);
    }
}
``` 
相关内容

[运行时内存跟踪教程](https://os.mbed.com/docs/v5.9/tutorials/optimizing.html#runtime-memory-tracing)。