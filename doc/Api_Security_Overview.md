## 安全概述
Arm Mbed OS 的安全性分为两部分：

+ [通过 Arm Mbed TLS 实现连接安全性](https://os.mbed.com/docs/v5.9/reference/tls.html)。
+ [通过 Arm Mbed uVisor 实现设备安全](https://os.mbed.com/docs/v5.9/reference/uvisor.html)。
**警告:** uVisor 被 ARM 平台安全体系结构（PSA）中定义的安全分区管理器（SPM）取代。uVisor 自 Mbed OS 5.10 起不推荐使用，并被原生 PSA 兼容的 SPM 实现所取代。

这些部分涵盖了在 Mbed OS 环境中使用这些模块。有关这两个模块的通用文档，请参阅：

+ [Mbed TLS 完整文档](https://tls.mbed.org/)。
+ [Mbed uVisor 完整文档](https://docs.mbed.com/docs/uvisor-and-uvisor-lib-documentation/en/latest/)。