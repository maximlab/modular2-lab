## LoRaWAN

可以通过 C++ API 或使用 Mbed 配置系统配置 Mbed LoRaWAN 栈的各种参数。

## 使用 Mbed 配置系统

以下是您可以使用 Mbed 配置系统配置的参数：
```
Configuration parameters
------------------------
 
Name: lora.adr-on
    Description: Turns Automatic Data Rate on/off
    Defined by: library:lora                                                                                                        
    Value: 1 (set by library:lora)                                                                                                  
Name: lora.app-port          
    Description: Set the application port                                                                                                       
    Defined by: library:lora                                                                                                        
    Value: 15 (set by library:lora)                                                                                                 
Name: lora.application-eui    
    Description: Set AppEUI (application EUI needed for OTAA)                                                                                                      
    Defined by: library:lora                                                                                                        
    Value: {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00} (set by library:lora)                                                   
Name: lora.application-key   
    Description: Set AppKey (application key needed for OTAA)                                                                                                       
    Defined by: library:lora                                                                                                        
    Value: {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00} (set by library:lora)   
Name: lora.appskey
    Description: Set AppSkey (application session key needed for ABP)                                                                
    Defined by: library:lora                                                                                                        
    Value: {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00} (set by library:lora)   
Name: lora.device-address 
    Description: Set DevAddr (device address needed for ABP)                                                                                                          
    Defined by: library:lora                                                                                                        
    Value: 0x00000000 (set by library:lora)                                                                                         
Name: lora.device-eui    
    Description: Set DevEUI (device EUI needed for OTAA)                                                                                                           
    Defined by: library:lora                                                                                                        
    Value: {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00} (set by library:lora)                                                   
Name: lora.duty-cycle-on  
    Description: Turns duty cycle on/off                                                                                                          
    Defined by: library:lora                                                                                                        
    Value: 1 (set by library:lora)                                                                                                  
Name: lora.lbt-on
    Description: Turns LBT on/off                                                                                                                   
    Defined by: library:lora                                                                                                        
Name: lora.nb-trials       
    Description: Set number of retries for a join request                                                                                                         
    Defined by: library:lora                                                                                                        
    Value: 12 (set by library:lora)                                                                                                 
Name: lora.nwkskey            
    Description: Set NwkSkey (network session key needed for ABP)                                                                                                      
    Defined by: library:lora                                                                                                        
    Value: {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00} (set by library:lora)   
Name: lora.over-the-air-activation   
    Description: Enable or disable OTAA. Value set to false would enable ABP                                                                                               
    Defined by: library:lora                                                                                                        
    Value: 1 (set by library:lora)                                                                                                  
Name: lora.phy       
    Description: Set the region of operation for the device                                                                                                               
    Defined by: library:lora                                                                                                        
    Value: EU868 (set by library:lora)                                                                                                  
Name: lora.public-network   
    Description: Set the public network parameter                                                                                                        
    Defined by: library:lora                                                                                                        
    Value: 1 (set by library:lora)                                                                                                  
Name: lora.tx-max-size   
    Description: Maximum outgoing buffer size                                                                                                           
    Defined by: library:lora                                                                                                        
    Value: 64 (set by library:lora)                                                                  
```
要更改任何这些参数，请编辑应用程序根目录中的 mbed_app.json 文件。使用 lora。作为参数名称的前缀，例如，lora.my-parameter：值。
```
"target_overrides": {
    "*": {
        "lora.device-address":  "0x12345678",
        "lora.over-the-air-activation": true,
        "lora.duty-cycle-on": true
    }
}
```
## 使用 LoRaWANInterface 中的 API

有关如何从 LoRaWANInterface 使用这些 API 的信息，请参阅 [API 参考](https://os.mbed.com/docs/v5.9/reference/lorawan.html)。