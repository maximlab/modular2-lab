## 驱动

驱动程序配置允许自定义 OS 驱动程序层。本节中的选项与硬件 IO 有关。您可以在平台配置页面中找到 printf 的其他串行设置。 除 default-serial-baud-rate 外，这些设置不会影响 Serial 对象。

以下是 mbed compile --config -v 生成的驱动程序配置参数的完整列表。有关如何使用或覆盖这些设置的详细信息，请参阅配置系统文档。
```
Configuration parameters
------------------------
 
Name: drivers.uart-serial-rxbuf-size
    Description: Default RX buffer size for a UARTSerial instance (unit Bytes))
    Defined by: library:drivers
    Macro name: MBED_CONF_DRIVERS_UART_SERIAL_RXBUF_SIZE
    Value: 256 (set by library:drivers)
Name: drivers.uart-serial-txbuf-size
    Description: Default TX buffer size for a UARTSerial instance (unit Bytes))
    Defined by: library:drivers
    Macro name: MBED_CONF_DRIVERS_UART_SERIAL_TXBUF_SIZE
```