## 网络状态
此接口以异步方式通知您有关连接状态的更改。提供一种将回调函数注册到套接字的方法可以实现这一点。每次网络接口的状态发生变化时，都会触发回调。

## 用法

回调需要处理这些可能的网络状态：
```
/** Enum of connection status types
 *
 *  Valid error codes have negative values.
 *
 *  @enum nsapi_connection_status
 */
 typedef enum nsapi_connection_status {
    NSAPI_STATUS_LOCAL_UP,            /*!< local IP address set */
    NSAPI_STATUS_GLOBAL_UP,           /*!< global IP address set */
    NSAPI_STATUS_DISCONNECTED,        /*!< no connection to network */
    NSAPI_STATUS_CONNECTING,          /*!< connecting to network */
    NSAPI_STATUS_ERROR_UNSUPPORTED  = NSAPI_ERROR_UNSUPPORTED
} nsapi_connection_status_t;
```
此 API 需要监视接口。例如，以太网：
```
EthernetInterface eth;
```
您需要提供回调函数本身：
```
void status_callback(nsapi_event_t status, intptr_t param)
{
    printf("Connection status changed!\r\n");
    switch(param) {
        case NSAPI_STATUS_LOCAL_UP:
            printf("Local IP address set!\r\n");
            break;
        case NSAPI_STATUS_GLOBAL_UP:
            printf("Global IP address set!\r\n");
            break;
        case NSAPI_STATUS_DISCONNECTED:
            printf("No connection to network!\r\n");
            break;
        case NSAPI_STATUS_CONNECTING:
            printf("Connecting to network!\r\n");
            break;
        default:
            printf("Not supported");
            break;
    }
}
```
现在，回调函数已注册到接口。
```
    eth.attach(&status_callback);
```
这允许应用程序监视网络接口是否断开连接。

（可选）应用程序可能希望将 connect() 方法设置为非阻塞模式，并等待连接完全建立。
```
    eth.set_blocking(false);
    eth.connect();              // Return immediately
```
默认情况下，connect() 调用将阻塞，直到达到 NSAPI_STATUS_GLOBAL_UP 状态。某些应用程序可能只需要链路连接，因此不需要阻止那么长时间。在那些情况下，监视状态变化是首选行为。

## 示例
注册连接状态更改触发器的状态回调取决于网络接口是否提供此功能。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/TCPSocket_ConnStateCb_Example/file/8a8191e3d305/main.cpp)                                                            
``` 
#include "EthernetInterface.h"
#include "mbed.h"
#include "nsapi_types.h"
 
// Network interface
EthernetInterface eth;
 
void status_callback(nsapi_event_t status, intptr_t param)
{
    printf("Connection status changed!\r\n");
    switch(param) {
        case NSAPI_STATUS_LOCAL_UP:
            printf("Local IP address set!\r\n");
            break;
        case NSAPI_STATUS_GLOBAL_UP:
            printf("Global IP address set!\r\n");
            break;
        case NSAPI_STATUS_DISCONNECTED:
            printf("No connection to network!\r\n");
            break;
        case NSAPI_STATUS_CONNECTING:
            printf("Connecting to network!\r\n");
            break;
        default:
            printf("Not supported");
            break;
    }
}
 
int main()
{
    printf("Status callback example!\r\n");
 
    eth.attach(&status_callback);
    eth.set_blocking(false);
    
    printf("Connecting...\n");
    eth.connect();
    
    printf("Connecting started...\n");
    wait(10);
    
    printf("Disconnect\n");
    eth.disconnect();
    
    printf("Done\n");    
}
```