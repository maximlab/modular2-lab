## Event
Event 类提供 API 来配置事件延迟和周期时间。您可以使用 post API 将事件发布到基础 EventQueue，您可以使用 cancel 取消最近发布的事件。

Event 类是线程安全的。post 和 cancel API 是 IRQ 安全的。

## Event 类参考
[Event.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/_event_8h_source.html)

## EventQueue 示例：将事件发布到队列
下面的代码演示了如何实例化，配置和发布事件。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-events/file/86c4bf2d90fa/main.cpp)       

```
#include "mbed.h"
// Creates an event bound to the specified event queue
EventQueue queue;
void handler(int count);
Event<void(int)> event(&queue, handler);
 
void handler(int count) {
    printf("Event = %d \n", count);
    return;
}
 
void post_events(void) {
 
    // Events can be posted multiple times and enqueue gracefully until
    // the dispatch function is called.
    event.post(1);
    event.post(2);
    event.post(3);    
}
 
int main() {
 
    Thread event_thread;
        
    // The event can be manually configured for special timing requirements
    // specified in milliseconds
    event.delay(100);       // Starting delay - 100 msec
    event.period(200);      // Delay between each evet - 200msec
    
    event_thread.start(callback(post_events));
    
    // Posted events are dispatched in the context of the queue's
    // dispatch function
    queue.dispatch(400);        // Dispatch time - 400msec
    // 400 msec - Only 2 set of events will be dispatched as period is 200 msec
    
    event_thread.join();
}
```