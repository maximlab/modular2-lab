## 存储

此页面描述了 Mbed OS 中存储的构建时可配置参数。不同的存储模块没有标准的共享配置选项。相反，每个模块都有自己的特定于实现的配置选项。

+ LittleFS 配置。
+ NVStore 配置。
以下是 mbed compile --config -v 生成的存储配置参数的完整列表。有关如何使用或覆盖这些设置的详细信息，请参阅配置系统文档。

### LittleFS 配置

LittleFS 提供了几个配置选项，可用于调整不同硬件上的文件系统性能。默认情况下，此文件系统从基础块设备的几何图形中查找最佳配置，但您可以覆盖它以优化特殊情况。例如，如果您的设备具有大量 RAM，则可以增加 read_size 和 prog_size 配置选项，以提高速度。

请注意，LittleFS 有 4 级调试日志记录。默认情况下，除 enable_debug 外，所有日志记录都已启用。将 enable_debug 设置为 true 会使日志输出非常详细，并且输出对于错误报告很有用。
```
Configuration parameters
------------------------
 
Name: littlefs.block_size
    Description: Size of an erasable block. This does not impact ram consumption and may be larger than the physical erase size. However, this should be kept small as each file currently takes up an entire block.
    Defined by: library:littlefs
    Macro name: MBED_LFS_BLOCK_SIZE
    Value: 512 (set by library:littlefs)
Name: littlefs.prog_size
    Description: Minimum size of a block program. This determines the size of program buffers. This may be larger than the physical program size to improve performance by caching more of the block device.
    Defined by: library:littlefs
    Macro name: MBED_LFS_PROG_SIZE
    Value: 64 (set by library:littlefs)
Name: littlefs.read_size
    Description: Minimum size of a block read. This determines the size of read buffers. This may be larger than the physical read size to improve performance by caching more of the block device.
    Defined by: library:littlefs
    Macro name: MBED_LFS_READ_SIZE
    Value: 64 (set by library:littlefs)
Name: littlefs.lookahead
    Description: Number of blocks to lookahead during block allocation. A larger lookahead reduces the number of passes required to allocate a block. The lookahead buffer requires only 1 bit per block so it can be quite large with little ram impact. Should be a multiple of 32.
    Defined by: library:littlefs
    Macro name: MBED_LFS_LOOKAHEAD
    Value: 512 (set by library:littlefs)
Name: littlefs.intrinsics
    Description: Enable intrinsics for bit operations such as ctz, popc, and le32 conversion. Can be disabled to help debug toolchain issues
    Defined by: library:littlefs
    Macro name: MBED_LFS_INTRINSICS
    Value: 1 (set by library:littlefs)
Name: littlefs.enable_assert
    Description: Enables asserts, true = enabled, false = disabled, null = disabled only in release builds
    Defined by: library:littlefs
    No value set
Name: littlefs.enable_debug
    Description: Enables debug logging, true = enabled, false = disabled, null = disabled only in release builds
    Defined by: library:littlefs
    No value set
Name: littlefs.enable_error
    Description: Enables error logging, true = enabled, false = disabled, null = disabled only in release builds
    Defined by: library:littlefs
    No value set
Name: littlefs.enable_info
    Description: Enables info logging, true = enabled, false = disabled, null = disabled only in release builds
    Defined by: library:littlefs
    No value set
Name: littlefs.enable_warn
    Description: Enables warn logging, true = enabled, false = disabled, null = disabled only in release builds
    Defined by: library:littlefs
    No value set
```
### NVStore 配置

NVStore 不需要太多配置。它仅依赖于 area_*_address 和 area_*_size 中指定的内部 flash 区域。此外，您可以使用 max_keys 来管理 NVStore 密钥所需的 RAM 量。请注意，max_keys 默认为 Mbed OS 需要的密钥数。如果应用程序直接使用 NVStore，您只需要修改它。
```
Configuration parameters
------------------------
 
Name: nvstore.area_1_address
    Description: Area 1 address
    Defined by: library:nvstore
    No value set
Name: nvstore.area_1_size
    Description: Area 1 size
    Defined by: library:nvstore
    No value set
Name: nvstore.area_2_address
    Description: Area 2 address
    Defined by: library:nvstore
    No value set
Name: nvstore.area_2_size
    Description: Area 2 size
    Defined by: library:nvstore
    No value set
Name: nvstore.max_keys
    Description: Maximal number of allowed NVStore keys
    Defined by: library:nvstore
    Macro name: NVSTORE_MAX_KEYS
    Value: 16 (set by library:nvstore)
```