## 存储概述
Arm Mbed OS 中的存储 API 包括：

+ [文件系统](https://os.mbed.com/docs/v5.9/reference/storage.html#declaring-a-file-system)： 在块设备上使用文件系统的通用接口。
+ [块设备](https://os.mbed.com/docs/v5.9/reference/storage.html#declaring-a-block-device)： 基于块的存储设备的通用接口。

## 声明文件系统
[FileSystem](https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html) 类为文件系统操作提供核心 API。您必须提供一个块设备来备份文件系统，该文件系统为文件系统提供原始存储。声明具有名称的文件系统时，可以通过 open 和 fopen 函数或 File 类的 open 函数打开文件系统上的文件。

### 文件系统

+ [LittleFileSystem](https://os.mbed.com/docs/v5.9/reference/littlefilesystem.html) - 小文件系统（LittleFS）是我们为嵌入式系统设计的故障安全文件系统，特别适用于使用闪存存储的微控制器。

    * 有限的 RAM/ROM - 此文件系统使用有限的内存。它避免了递归并将动态内存限制为可配置缓冲区。

    * 功率损耗弹性 - 我们为可能存在随机电源故障的操作系统设计了此功能。它具有强大的写时复制保证，并使磁盘上的存储保持有效状态。

    * 磨损均衡 - 由于最常见的嵌入式存储形式是易受攻击的闪存，因此该文件系统为无法适应全闪存转换层的系统提供了一种动态耗损均衡。

+ [FATFileSystem](https://os.mbed.com/docs/v5.9/reference/fatfilesystem.html) - FAT 文件系统是一个已建立的面向磁盘的文件系统，您可以在大多数操作系统上找到它，包括Windows，Linux，Mac OS X 和 Mbed OS。

    * 便携 - 由于支持跨操作系统，FAT 文件系统可以从嵌入式系统和 PC 访问存储。

    * 嵌入式 - FAT 文件系统建立在 ChanFS 项目之上，针对嵌入式系统进行了优化。

+ LocalFileSystem - LocalFileSystem 是一个共生文件系统，如果接口芯片具有内置存储器，则连接到 Mbed 板的接口芯片。LocalFileSystem 上可用的功能取决于主板的接口芯片。注意: LocalFileSystem 仅适用于 LPC1768 和 LPC11U24。

**注意:** 一些文件系统可以提供格式化功能，用于在底层块设备上干净地初始化文件系统，或者在第一次使用之前需要外部工具来设置文件系统。

### LittleFileSystem

微控制器和闪存存储对嵌入式存储提出了三个挑战：[功耗](https://os.mbed.com/docs/v5.9/reference/storage.html#power-loss-resilience)，[磨损](https://os.mbed.com/docs/v5.9/reference/storage.html#wear-leveling)以及[有限的 RAM 和 ROM](https://os.mbed.com/docs/v5.9/reference/storage.html#bounded-ram-and-rom)。该文件系统为所有这三个问题提供了解决方案。

### 功率损耗弹性

微控制器级嵌入式系统通常没有关闭例程，依靠断电来关闭，特别是缺少用于恢复的用户界面。如果文件系统不能恢复功耗，那么您可以依靠运气来避免文件系统损坏。持久存储和不可预测的功率损耗的组合会产生难以察觉的错误并破坏不幸用户的体验。

我们构建了这个文件系统，其结构可以抵御掉电。它使用校验和来限制物理存储如何对功率损耗做出反应的假设。它提供写时复制保证，并使磁盘上的存储保持有效状态。

### 磨损均衡

Flash 存储面临着挑战：磨损。Flash 是一种破坏性的存储形式，并且不断地将数据重写到块中会导致该块磨损并变得不可写。 不考虑磨损的文件系统可以快速烧掉存储频繁更新的元数据的块，并导致系统过早死亡。

我们在构建此文件系统时考虑了磨损，并且文件系统的底层结构会在底层存储在其整个生命周期中发生错误时进行反应性变异。 这导致动态磨损均衡的形式，其将物理存储的寿命成比例地延长到存储的大小。使用此文件系统，您可以通过增加存储大小来延长存储的生命周期，这比升级存储的擦除周期更便宜。

### 有限的 RAM 和 ROM

文件系统通常以可用资源规模对微控制器来说是外来的操作系统为目标。嵌入式 Linux 文件系统的一个普遍趋势是 RAM 的使用与存储的大小成线性关系，这使得在系统中合理化 RAM 使用变得困难。

我们优化了这个文件系统，以便使用有限的 RAM 和 ROM。它避免了递归并将动态内存限制为可配置缓冲区。在操作期间，它不会将整个存储块存储在 RAM 中。结果是小的 RAM 使用量与底层存储的几何形状无关。

### 范围

小文件系统中的 “小” 来自于既保持资源使用率低又保持范围自包含的重点。除了上述三个目标问题之外，该软件模块中还存在严重的膨胀限制。相反，我们将其他功能推送到 BlockDevice API 中用于驱动 Mbed OS 存储栈的单独层。这为 Mbed OS 提供了一种工具，可以随着物联网设备使用的技术的发展而保持灵活性。

### FATFileSystem

FAT 文件系统是一个已建立的面向磁盘的文件系统，您可以在 Mbed OS，Windows，Linux 和 Mac OS X 上找到它。由于其年龄和普及性，FAT 文件系统已成为便携式存储的标准，如 flash 驱动器和 SD 卡。

### 便携

FAT 文件系统的主要特点是它的可移植性。通过支持 PC 操作系统，FAT 文件系统允许您从 PC 的嵌入式系统访问存储。这为用户提供了一种获取设备信息的方法。

### 嵌入式

Mbed OS FAT 文件系统构建在 ChanFS 项目上。它针对嵌入式系统进行了优化，是最小的 FAT 文件系统实现之一。

### C++ 类

FileSystem 类提供核心用户 C++ API。Mbed OS 提供了表示 C++ API 中的文件和目录的 File 和 Dir 类。

## 声明一个块设备
BlockDevice 类为原始存储提供底层 API，可用于备份文件系统。BlockDevice API 是一个标准的面向块的接口，围绕三种操作模式构建：读取，擦除和编程。但是，此 API 背后的规则足够灵活，可以支持各种不同的存储类型。

Mbed OS 为更常见的存储介质提供标准实现，您可以扩展 BlockDevice 类以支持不支持的存储。此外，Mbed OS 包含一些实用程序块设备，例如 SlicingBlockDevice 和 ChainingBlockDevice，可以更好地控制存储分配。可以堆叠这些实用程序块设备以通过相对简单的组件提供相对复杂的存储架构。

### 块设备

Mbed OS 有几种常见存储形式的块设备实现：

+ SPIFBlockDevice - 支持 SFDP 的基于 NOR 的 SPI 闪存设备的设备驱动程序。基于 NOR 的 SPI 闪存支持字节大小的读写操作，擦除大小约为 4k 字节。擦除将块设置为全 1，连续写入清除设置位。

+ DataFlashBlockDevice - 支持 DataFlash 协议的基于 NOR 的 SPI 闪存设备的设备驱动程序，例如 Adesto AT45DB 系列设备。DataFlash 是一种内存协议，它将闪存与 SRAM 缓冲区结合在一起，用于编程接口。DataFlash 支持字节大小的读写操作，擦除大小约为 528 字节或有时为 1056 字节。DataFlash 为纠错码（ECC）提供了 16 个字节的擦除大小，因此闪存转换层（FTL）仍然可以提供 512 字节的擦除大小。

+ SDBlockDevice - SD 卡和 eMMC 内存芯片的设备驱动程序。SD 卡或 eMMC 芯片在 NAND 闪存之上提供完整的 FTL 层。 这使得存储非常适合需要大约 1GB 内存的系统。此外，SD 卡是一种流行的便携式存储形式。如果要存储可以从 PC 访问的数据，它们非常有用。

+ [HeapBlockDevice](https://os.mbed.com/docs/v5.9/reference/heapblockdevice.html) - 使用堆模拟 RAM 中存储的设备。不要使用堆块设备持久存储数据，因为断电会导致数据完全丢失。相反，当存储设备不可用时，使用它来测试应用程序。

+ FlashIAPBlockDevice - 用于 [FlashIAP 驱动程序](https://os.mbed.com/docs/v5.9/reference/flash-iap.html)的块设备适配器，为 MCU 的内部闪存提供应用程序编程（IAP）接口。

### 实用程序块设备

此外，Mbed OS 包含多个实用程序块设备，可以更好地控制存储分配。

+ [SlicingBlockDevice](https://os.mbed.com/docs/v5.9/reference/slicingblockdevice.html) - 使用切片块设备，您可以将存储分区为可以单独使用的较小块设备。

+ [ChainingBlockDevice](https://os.mbed.com/docs/v5.9/reference/chainingblockdevice.html) - 使用链接块设备，您可以将多个块设备链接在一起并扩展可用的存储量。

+ [MBRBlockDevice](https://os.mbed.com/docs/v5.9/reference/mbrblockdevice.html) - Mbed OS 支持使用主引导记录（MBR）在磁盘上存储分区。MBRBlockDevice 提供此功能，并支持在运行时创建分区或使用与应用程序外部分开配置的预格式化分区。

+ ReadOnlyBlockDevice - 使用只读块设备，可以将块设备包装在只读层中，确保块设备的用户不会修改存储。

+ ProfilingBlockDevice - 使用性能分析块设备，您可以分析块设备上发生的擦除，编程和读取操作的数量。

+ ObservingBlockDevice - 观察块设备授予用户在块设备操作上注册回调的能力。您可以使用它来检查块设备的状态，记录不同的度量标准或执行其他操作。

+ ExhaustibleBlockDevice - 用于评估文件系统如何响应磨损，可耗尽的块设备模拟另一种存储形式的磨损。您可以根据需要将其配置为过期块。

+ [FlashSimBlockDevice](https://github.com/ARMmbed/mbed-os-5-docs/blob/5.9/docs/reference/api/storage/FlashSimBlockDevice.md) - 如果底层块设备不支持此类行为，则模拟闪存组件的行为。

+ [BufferedBlockDevice](https://github.com/ARMmbed/mbed-os-5-docs/blob/5.9/docs/reference/api/storage/BufferedBlockDevice.md) - 为块设备上的读取块和程序块提供缓冲区，将底层块设备的读取和程序大小减少到 1B。