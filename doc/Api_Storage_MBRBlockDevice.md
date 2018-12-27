## MBRBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.png">

MBRBlockDevice 类层次结构</div>                                                                 

MBRBlockDevice 类提供了一种管理存储设备上的主引导记录（MBR）的方法，允许您对设备进行分区。如果没有 MBR，您仍然可以使用文件系统格式化存储设备，但包括 MBR 将允许将来的分区修改。

MBRBlockDevices 在构造函数中具有以下可配置参数：

+ bd - 块设备返回 MBRBlockDevice
+ part - 分区使用，1 - 4

您可以在类引用中查看有关可配置设置和函数的更多信息。

## MBRBlockDevice 类参考
[MBRBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#af6a37d19aefba222155663de313cdd25" rel="nofollow" target="_blank">MBRBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd, int part)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a23c6943d60a7be52cc3ec87d4fb557a9" rel="nofollow" target="_blank">~MBRBlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a778021c373b6954c71121cbf19e4e84e" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#afda889d5dbb5d3bed6f0d0222272a174" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#af22fc95d9850a921f4b048996199c84f" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#aabc3027216369068d292425240498848" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a1eee0b0beeb8fdaeda23f4f2b6c53dc6" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a041b5217588929690cab8a869886e6d1" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a1eee0b0beeb8fdaeda23f4f2b6c53dc6" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a2064d7d85063a8cf1d2d710dc0f39043" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a1eee0b0beeb8fdaeda23f4f2b6c53dc6" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a3c78569b8a83087c547b58fad7cd14d6" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a55eeb132ac466effd668a0e95e006c6f" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a2731a5feb3c3576ee1d223fe911ab5b8" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a9ccb92935100aeb838a0758424e07354" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a7ca77b7e1a8d1fdb96f3897bf90ebda0" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a1eee0b0beeb8fdaeda23f4f2b6c53dc6" rel="nofollow" target="_blank">size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_addr_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#ac8e7938d4423529bc9db7a728ca0668b" rel="nofollow" target="_blank">get_partition_start</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_addr_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a75e9f6f09cb00a17781ca746b75e7c76" rel="nofollow" target="_blank">get_partition_stop</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a8e0cbc1d332a7da607d0c961157858f3" rel="nofollow" target="_blank">get_partition_type</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a624d045cbf32cd9128efda29bb1f215d" rel="nofollow" target="_blank">get_partition_number</a> () const</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a397713428dd2b787174b6ca43231c1f9" rel="nofollow" target="_blank">~BlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a3c4e12c08231786310538d3d0729ba49" rel="nofollow" target="_blank">trim</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#adb348252c273554b08a4826477786ccd" rel="nofollow" target="_blank">is_valid_read</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af341e26902d727513dfe9ff4d6232751" rel="nofollow" target="_blank">is_valid_program</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0a5c01f28bdcd360f56f0f8e636067f2" rel="nofollow" target="_blank">is_valid_erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#ace6dd73e8514a0a2afab8f8bc37bada8" rel="nofollow" target="_blank">partition</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd, int part, uint8_t type, bd_addr_t start)</td>
		</tr><tr><td style="vertical-align:top;">static int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_m_b_r_block_device.html#a69bb7b1976b105d9f2f820cdb48d536a" rel="nofollow" target="_blank">partition</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd, int part, uint8_t type, bd_addr_t start, bd_addr_t stop)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="aac32a05aecb553081ef38d7ebfa6a95f" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bd</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aef7bef400055b6bf7ea87f2e4dc5e64c" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_offset</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2a3b46918b6b4c1e14635bf171945826" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2a4db41da5a435a30f6f46d255e92bf1" target="_blank"></a> uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_type</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="af4a73200cd6684679a7b1587e3933a8b" target="_blank"></a> uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_part</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a313fd7a7d840dee793ca061fe0076501" target="_blank"></a> uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_init_ref_count</strong></td>
		</tr></tbody></table>

## MBRBlockDevice 示例
将堆支持的块设备分区为两个分区。此示例还使用 HeapBlockDevice。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/MBRBlockDevice_ex_1/file/daa62d7aa9f9/main.cpp)                                                                                                                                                
```
#include "mbed.h"
#include "HeapBlockDevice.h"
#include "MBRBlockDevice.h"
    
int main(void) {
    // Create a block device with 64 blocks of size 512
    HeapBlockDevice mem(64*512, 512);
    
    // Partition into two partitions with ~half the blocks
    MBRBlockDevice::partition(&mem, 1, 0x83, 0*512, 32*512);
    MBRBlockDevice::partition(&mem, 2, 0x83, 32*512);
    
    // Create a block device that maps to the first 32 blocks (excluding MBR block)
    MBRBlockDevice part1(&mem, 1);
    
    // Create a block device that maps to the last 32 blocks
    MBRBlockDevice part2(&mem, 2);
}
```
对 SD 卡进行分区，并使用 FAT 文件系统格式化新分区。PC 现在可以识别 SD 卡。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/MBRBlockDevice_ex_2/file/a48b7099a59c/main.cpp)                                                                                                                                                
```
#include "mbed.h"
#include "SDBlockDevice.h"
#include "MBRBlockDevice.h"
#include "FATFileSystem.h"
    
// Pin mappings for K64F
PinName s0 = PTE3;  // MOSI
PinName s1 = PTE1;  // MISO
PinName s2 = PTE2;  // SCLK
PinName s3 = PTE4;  // CS
    
int main(void) {
    // Create an SD card
    SDBlockDevice sd(s0, s1, s2, s3);
    
    // Create a partition with 1 GB of space
    MBRBlockDevice::partition(&sd, 1, 0x83, 0, 1024*1024);
    
    // Create the block device that represents the partition
    MBRBlockDevice part1(&sd, 1);
    
    // Format the partition with a FAT filesystem
    FATFileSystem::format(&part1);
    
    // Create the FAT filesystem instance, files can now be written to
    // the FAT filesystem in partition 1
    FATFileSystem fat("fat", &part1);
}
```