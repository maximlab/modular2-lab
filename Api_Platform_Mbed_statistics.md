## Mbed 统计

Mbed OS 提供了一组函数，可用于在运行时捕获内存和线程统计信息。mbed_stats.h 声明了这些函数。要启用所有 Mbed OS 统计信息，必须使用 MBED_ALL_STATS_ENABLED 宏构建代码。

## 内存统计

您可以使用内存统计函数在运行时捕获堆使用情况，累积栈使用情况或每个线程的栈使用情况。要启用内存使用情况监视，必须使用以下宏构建 Mbed OS：

+ MBED_HEAP_STATS_ENABLED。
+ MBED_STACK_STATS_ENABLED。

## 线程统计

您可以使用线程统计函数 mbed_stats_thread_get_each 来捕获运行时所有活动线程的线程 ID，状态，优先级，名称和栈信息。 要启用线程监视，必须使用 MBED_THREAD_STATS_ENABLED 宏构建 Mbed OS。

## 系统信息

您可以使用 mbed_stats_sys_get 函数来获取 CPU ID 和编译器信息。您必须使用 MBED_SYS_STATS_ENABLED 宏构建 Mbed OS 以启用获取系统信息。

## CPU 统计信息

您可以使用 mbed_stats_cpu_get 函数来获取正常运行时间，空闲时间和睡眠时间信息。自系统启动以来，可用的计时信息是累积的。您必须使用 MBED_CPU_STATS_ENABLED 宏构建 Mbed OS 以启用获取 CPU 信息。请注意，CPU 统计信息取决于硬件中低功耗定时器的可用性。

## Mbed 统计功能参考

[mbed_stats.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__stats_8h_source.html)

## 内存统计示例

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-platform-utils/file/92b97ba04fd3/main.cpp)                                   
```
/* Example usage for Debug, Assert, Error and MemoryStats 
 * Copyright (c) 2016 ARM Limited
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
#include "platform/mbed_assert.h"
#include "platform/mbed_debug.h"
#include "platform/mbed_error.h"
#include "platform/mbed_stats.h"
 
#define MAX_THREAD_INFO 10
 
mbed_stats_heap_t heap_info;
mbed_stats_stack_t stack_info[ MAX_THREAD_INFO ];
int main()
{
    debug("\nThis message is from debug function");
    debug_if(1,"\nThis message is from debug_if function");
    debug_if(0,"\nSOMETHING WRONG!!! This message from debug_if function shouldn't show on bash");
    
    printf("\nMemoryStats:");
    mbed_stats_heap_get( &heap_info );
    printf("\n\tBytes allocated currently: %d", heap_info.current_size);
    printf("\n\tMax bytes allocated at a given time: %d", heap_info.max_size);
    printf("\n\tCumulative sum of bytes ever allocated: %d", heap_info.total_size);
    printf("\n\tCurrent number of bytes allocated for the heap: %d", heap_info.reserved_size);
    printf("\n\tCurrent number of allocations: %d", heap_info.alloc_cnt);
    printf("\n\tNumber of failed allocations: %d", heap_info.alloc_fail_cnt);
    
    mbed_stats_stack_get( &stack_info[0] );
    printf("\nCumulative Stack Info:");
    printf("\n\tMaximum number of bytes used on the stack: %d", stack_info[0].max_size);
    printf("\n\tCurrent number of bytes allocated for the stack: %d", stack_info[0].reserved_size);
    printf("\n\tNumber of stacks stats accumulated in the structure: %d", stack_info[0].stack_cnt);
    
    mbed_stats_stack_get_each( stack_info, MAX_THREAD_INFO );
    printf("\nThread Stack Info:");
    for(int i=0;i < MAX_THREAD_INFO; i++) {
        if(stack_info[i].thread_id != 0) {
            printf("\n\tThread: %d", i);
            printf("\n\t\tThread Id: 0x%08X", stack_info[i].thread_id);
            printf("\n\t\tMaximum number of bytes used on the stack: %d", stack_info[i].max_size);
            printf("\n\t\tCurrent number of bytes allocated for the stack: %d", stack_info[i].reserved_size);
            printf("\n\t\tNumber of stacks stats accumulated in the structure: %d", stack_info[i].stack_cnt); 
        }        
    }
    
    printf("\nDone...\n\n");
}
``` 
## 线程统计示例

[main.cpp](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-thread-statistics/file/25c062a4a1e6/main.cpp)                             
```
#include "mbed.h"
 
#if !defined(MBED_THREAD_STATS_ENABLED)
#error "Stats not enabled"
#endif
 
#define MAX_THREAD_STATS    0x8
 
int main()
{
    mbed_stats_thread_t *stats = new mbed_stats_thread_t[MAX_THREAD_STATS];
    int count = mbed_stats_thread_get_each(stats, MAX_THREAD_STATS);
    
    for(int i = 0; i < count; i++) {
        printf("ID: 0x%x \n", stats[i].id);
        printf("Name: %s \n", stats[i].name);
        printf("State: %d \n", stats[i].state);
        printf("Priority: %d \n", stats[i].priority);
        printf("Stack Size: %d \n", stats[i].stack_size);
        printf("Stack Space: %d \n", stats[i].stack_space);
        printf("\n");
    }
    return 0;
}
``` 
## 系统信息示例

[main.cpp](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-sys-info/file/db1600a88ae1/main.cpp)                                      
```                                              
#include "mbed.h"
 
#if !defined(MBED_SYS_STATS_ENABLED)
#error [NOT_SUPPORTED] test not supported
#endif
 
int main()
{
    mbed_stats_sys_t stats;
    mbed_stats_sys_get(&stats);
 
    printf("Mbed OS Version: 0x%x \n", stats.os_version);
 
    /* CPUID Register information
    [31:24]Implementer      0x41 = ARM
    [23:20]Variant          Major revision 0x0  =  Revision 0
    [19:16]Architecture     0xC  = Baseline Architecture
                            0xF  = Constant (Mainline Architecture?)
    [15:4]PartNO            0xC20 =  Cortex-M0
                            0xC60 = Cortex-M0+
                            0xC23 = Cortex-M3
                            0xC24 = Cortex-M4
                            0xC27 = Cortex-M7
                            0xD20 = Cortex-M23
                            0xD21 = Cortex-M33
    [3:0]Revision           Minor revision: 0x1 = Patch 1.
    */
    printf("CPU ID: 0x%x \n", stats.cpu_id);
 
    printf("Compiler ID: %d \n", stats.compiler_id);
 
    /* Compiler versions:
       ARM: PVVbbbb (P = Major; VV = Minor; bbbb = build number)
       GCC: VVRRPP  (VV = Version; RR = Revision; PP = Patch)
       IAR: VRRRPPP (V = Version; RRR = Revision; PPP = Patch)
    */
    printf("Compiler Version: %d \n", stats.compiler_version);
 
    return 0;
}
``` 
## CPU 统计示例

[main.cpp](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-cpu-stats/file/3114f82feb68/main.cpp)                                                                                   
```
#include "mbed.h"
 
#if !defined(MBED_CPU_STATS_ENABLED) || !defined(DEVICE_LPTICKER) || !defined(DEVICE_SLEEP)
#error [NOT_SUPPORTED] test not supported
#endif
 
DigitalOut led1(LED1);
 
#define MAX_THREAD_STACK        384
#define SAMPLE_TIME             1000
#define LOOP_TIME               3000
 
uint64_t prev_idle_time = 0;
int32_t wait_time = 5000;
 
void busy_thread()
{
    volatile uint64_t i = ~0;
 
    while(i--) {
        led1 = !led1;
        wait_us(wait_time);
    }
}
 
void print_stats()
{
    mbed_stats_cpu_t stats;
    mbed_stats_cpu_get(&stats);
 
    printf("%-20lld", stats.uptime);
    printf("%-20lld", stats.idle_time);
    printf("%-20lld", stats.sleep_time);
    printf("%-20lld\n", stats.deep_sleep_time);
}
 
int main()
{
    // Request the shared queue
    EventQueue *stats_queue = mbed_event_queue();
    Thread *thread;
    int id;
 
    id = stats_queue->call_every(SAMPLE_TIME, print_stats);
    printf("%-20s%-20s%-20s%-20s\n", "Uptime", "Idle Time", "Sleep time", "DeepSleep time");
 
    thread = new Thread(osPriorityNormal, MAX_THREAD_STACK);
    thread->start(busy_thread);
 
    // Steadily increase the system load
    for (int count = 1; ; count++) {
        Thread::wait(LOOP_TIME);
        if (wait_time <= 0) {
            break;
        }
        wait_time -= 1000;
    }
    thread->terminate();
    stats_queue->cancel(id);
    return 0;
}
``` 
## CPU 使用示例

[main.cpp](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-cpu-usage/file/f21ba16b103f/main.cpp)                                      
```
#include "mbed.h"
 
#if !defined(MBED_CPU_STATS_ENABLED) || !defined(DEVICE_LPTICKER) || !defined(DEVICE_SLEEP)
#error [NOT_SUPPORTED] test not supported
#endif
 
DigitalOut led1(LED1);
 
#define MAX_THREAD_STACK        384
#define SAMPLE_TIME             2000    // msec
#define LOOP_TIME               3000    // msec
 
uint64_t prev_idle_time = 0;
int32_t wait_time = 5000;      // usec
 
void busy_thread()
{
    volatile uint64_t i = ~0;
 
    while(i--) {
        led1 = !led1;
        wait_us(wait_time);
    }
}
 
void calc_cpu_usage()
{
    mbed_stats_cpu_t stats;
    mbed_stats_cpu_get(&stats);
 
    uint64_t diff = (stats.idle_time - prev_idle_time);
    uint8_t idle = (diff * 100) / (SAMPLE_TIME*1000);    // usec;
    uint8_t usage = 100 - ((diff * 100) / (SAMPLE_TIME*1000));    // usec;;
    prev_idle_time = stats.idle_time;
 
    printf("Idle: %d Usage: %d \n", idle, usage);
}
 
int main()
{
    // Request the shared queue
    EventQueue *stats_queue = mbed_event_queue();
    Thread *thread;
    int id;
 
    id = stats_queue->call_every(SAMPLE_TIME, calc_cpu_usage);
    thread = new Thread(osPriorityNormal, MAX_THREAD_STACK);
    thread->start(busy_thread);
 
    // Steadily increase the system load
    for (int count = 1; ; count++) {
        Thread::wait(LOOP_TIME);
        if (wait_time <= 0) {
            break;
        }
        wait_time -= 1000;  // usec
    }
    thread->terminate();
    stats_queue->cancel(id);
    return 0;
}
```