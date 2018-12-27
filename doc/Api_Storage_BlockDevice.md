## BlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.png">

BlockDevice 类层次结构</div>                                                                 

BlockDevice API 提供了一个用于访问基于块的存储的接口。您可以使用块设备来备份完整的[文件系统](https://os.mbed.com/docs/v5.9/reference/porting-storage.html)或直接写入它。

最常见的基于块的存储类型是不同形式的闪存，但 BlockDevice API 可以支持许多不同形式的存储，例如 SD 卡，旋转磁盘，堆后备存储等。

### 块设备操作

块设备可以执行三个操作：

+ 从存储中读取数据区域。
+ 擦除存储中的数据区域。
+ 编程先前已擦除的数据区域。
对块设备的完全写入包括首先擦除您计划编程的存储器区域，然后将数据编程到存储器区域。这种分离的原因是块设备对于擦除和写入设备上的区域可能具有不同的限制。

### 块设备块

块设备是字节可寻址的，但以 “块” 为单位运行。三种类型的块设备操作有三种类型的块：读取块，擦除块和程序块。

**注意:**  对于许多器件，擦除块可能很大（例如，SPI 闪存为 4 KiB）。因此，我们不鼓励将整个擦除块存储在 RAM 中。相反，我们建议首先擦除块然后以程序块为单位进行编程。

<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/blockdevice_block_size.png"></div>

删除块

擦除块的状态未定义。在对块进行编程之前，不会确定存储在块上的数据。这允许对不同类型的存储提供最广泛的支持。

<div align=center><img src="https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/blockdevice_erase_block.png"></div>

## BlockDevice 类参考
[BlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a397713428dd2b787174b6ca43231c1f9" rel="nofollow" target="_blank">~BlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a2806e4e0e96f1f638249395979f3f3c0" rel="nofollow" target="_blank">init</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#afc937074665c799604f0845da16e4ad2" rel="nofollow" target="_blank">deinit</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af12f76921bb454c7d3b112ee423cce06" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af5009bb16022efe6de2b541cbb849273" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#ab7fad51ad7f5c692d9d788710135f187" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a18c699e790fef797ceb2dfe39f4641a5" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a3c4e12c08231786310538d3d0729ba49" rel="nofollow" target="_blank">trim</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a06b3e976dcfad88235bda83b76b76ef2" rel="nofollow" target="_blank">get_read_size</a> () const =0</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#abf9eea9a6fc692591b01700ff7e80e49" rel="nofollow" target="_blank">get_program_size</a> () const =0</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a376030c17aa25a665195fb82dbdb236b" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a39b82f8470f532bc326da373124dc34a" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0756f8732d4f5fc1627bfbbd2aa51975" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a> () const =0</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#adb348252c273554b08a4826477786ccd" rel="nofollow" target="_blank">is_valid_read</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af341e26902d727513dfe9ff4d6232751" rel="nofollow" target="_blank">is_valid_program</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0a5c01f28bdcd360f56f0f8e636067f2" rel="nofollow" target="_blank">is_valid_erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr></tbody></table>

## BlockDevice 示例
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2013 ARM Limited
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
#include <stdio.h>
#include <algorithm>
 
// Block devices
#include "SPIFBlockDevice.h"
#include "DataFlashBlockDevice.h"
#include "SDBlockDevice.h"
#include "HeapBlockDevice.h"
 
 
// Physical block device, can be any device that supports the BlockDevice API
SPIFBlockDevice bd(
        MBED_CONF_SPIF_DRIVER_SPI_MOSI,
        MBED_CONF_SPIF_DRIVER_SPI_MISO,
        MBED_CONF_SPIF_DRIVER_SPI_CLK,
        MBED_CONF_SPIF_DRIVER_SPI_CS);
 
 
// Entry point for the example
int main() {
    printf("--- Mbed OS block device example ---\n");
 
    // Initialize the block device
    printf("bd.init()\n");
    int err = bd.init();
    printf("bd.init -> %d\n", err);
 
    // Get device geometry
    bd_size_t read_size    = bd.get_read_size();
    bd_size_t program_size = bd.get_program_size();
    bd_size_t erase_size   = bd.get_erase_size();
    bd_size_t size         = bd.size();
 
    printf("--- Block device geometry ---\n");
    printf("read_size:    %lld B\n", read_size);
    printf("program_size: %lld B\n", program_size);
    printf("erase_size:   %lld B\n", erase_size);
    printf("size:         %lld B\n", size);
    printf("---\n");
 
    // Allocate a block with enough space for our data, aligned to the
    // nearest program_size. This is the minimum size necessary to write
    // data to a block.
    size_t buffer_size = sizeof("Hello Storage!") + program_size-1;
    buffer_size = buffer_size - (buffer_size % program_size);
    char *buffer = new char[buffer_size];
 
    // Read what is currently stored on the block device. We haven't written
    // yet so this may be garbage
    printf("bd.read(%p, %d, %d)\n", buffer, 0, buffer_size);
    err = bd.read(buffer, 0, buffer_size);
    printf("bd.read -> %d\n", err);
 
    printf("--- Stored data ---\n");
    for (size_t i = 0; i < buffer_size; i += 16) {
        for (size_t j = 0; j < 16; j++) {
            if (i+j < buffer_size) {
                printf("%02x ", buffer[i+j]);
            } else {
                printf("   ");
            }
        }
 
        printf(" %.*s\n", buffer_size - i, &buffer[i]);
    }
    printf("---\n");
 
    // Update buffer with our string we want to store
    strncpy(buffer, "Hello Storage!", buffer_size);
 
    // Write data to first block, write occurs in two parts,
    // an erase followed by a program
    printf("bd.erase(%d, %lld)\n", 0, erase_size);
    err = bd.erase(0, erase_size);
    printf("bd.erase -> %d\n", err);
 
    printf("bd.program(%p, %d, %d)\n", buffer, 0, buffer_size);
    err = bd.program(buffer, 0, buffer_size);
    printf("bd.program -> %d\n", err);
 
    // Clobber the buffer so we don't get old data
    memset(buffer, 0xcc, buffer_size);
 
    // Read the data from the first block, note that the program_size must be
    // a multiple of the read_size, so we don't have to check for alignment
    printf("bd.read(%p, %d, %d)\n", buffer, 0, buffer_size);
    err = bd.read(buffer, 0, buffer_size);
    printf("bd.read -> %d\n", err);
 
    printf("--- Stored data ---\n");
    for (size_t i = 0; i < buffer_size; i += 16) {
        for (size_t j = 0; j < 16; j++) {
            if (i+j < buffer_size) {
                printf("%02x ", buffer[i+j]);
            } else {
                printf("   ");
            }
        }
 
        printf(" %.*s\n", buffer_size - i, &buffer[i]);
    }
    printf("---\n");
 
    // Deinitialize the block device
    printf("bd.deinit()\n");
    err = bd.deinit();
    printf("bd.deinit -> %d\n", err);
 
    printf("--- done! ---\n");
}
```