## HeapBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.png">

HeapBlockDevice 类层次结构</div>                                                                 

HeapBlockDevice 类提供了一种模拟块设备以进行软件开发或测试的方法。创建的块是非易失性的；他们不会在电力循环中持续存在。

HeapBlockDevices 在两个构造函数之一中具有以下可配置参数：

## 详细的构造函数
+ size - 块设备的大小（以字节为单位）。
+ read_size - 最小读取大小，以字节为单位。
+ program_size - 最小编程大小，以字节为单位。
+ erase_size - 最小擦除大小，以字节为单位。

或者，您可以创建一个 HeapBlockDevice，它将读取，编程和擦除大小设置为相同的大小，而不是要求在所有值都受公共块大小约束时重复每个参数。

## 缩短构造函数
+ size - 块设备的大小（以字节为单位）。
+ block - 块大小（字节）。您可以使用此选项将最小读取，编程和擦除大小配置为此值。默认值为 512 字节。

您可以在类引用中查看有关可配置设置和函数的更多信息。

## HeapBlockDevice 类参考
[HeapBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a03a71ebc2c79060e4976c30942997a05" rel="nofollow" target="_blank">HeapBlockDevice</a> (bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a>, bd_size_t block=512)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#abb8623644710ccb538bc600adbe271b5" rel="nofollow" target="_blank">HeapBlockDevice</a> (bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a>, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#aafc840564d21349df29357f8c67bc3e2" rel="nofollow" target="_blank">read</a>, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#af14aa59b74b0da03ba2f0c351240bf27" rel="nofollow" target="_blank">program</a>, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a03d47d4650b0c62247e2139f484ebb7c" rel="nofollow" target="_blank">erase</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#adc40250ec26f4a865a7b60205ec95a4f" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a4c1430a3519a1f0b5a69f846c0b004ce" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#aafc840564d21349df29357f8c67bc3e2" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#af14aa59b74b0da03ba2f0c351240bf27" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a03d47d4650b0c62247e2139f484ebb7c" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a353e6a2d498fb02aaca5a403a94a77bf" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#ab797c9a3de9d228b7dc12fd386c98e60" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a4c89861056e81bf8ecb37c400ee83082" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a07ee330928e3e7f96861e3e34257c875" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_heap_block_device.html#a20e46b32fdd928a9e82f5ca1b1f17a12" rel="nofollow" target="_blank">size</a> () const</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a397713428dd2b787174b6ca43231c1f9" rel="nofollow" target="_blank">~BlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af12f76921bb454c7d3b112ee423cce06" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a3c4e12c08231786310538d3d0729ba49" rel="nofollow" target="_blank">trim</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0756f8732d4f5fc1627bfbbd2aa51975" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#adb348252c273554b08a4826477786ccd" rel="nofollow" target="_blank">is_valid_read</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af341e26902d727513dfe9ff4d6232751" rel="nofollow" target="_blank">is_valid_program</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0a5c01f28bdcd360f56f0f8e636067f2" rel="nofollow" target="_blank">is_valid_erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr></tbody></table>

## HeapBlockDevice 示例
创建一个 HeapBlockDevice，对其进行编程，读回块并清理。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/HeapBlockDevice_ex_1/file/5991e7053465/main.cpp)                    
```
#include "mbed.h"
#include "HeapBlockDevice.h"
 
#define BLOCK_SIZE 512
 
HeapBlockDevice bd(2048, BLOCK_SIZE); // 2048 bytes with a block size of 512 bytes
uint8_t block[BLOCK_SIZE] = "Hello World!\n";
 
int main() {
    bd.init();
    bd.erase(0, BLOCK_SIZE);
    bd.program(block, 0, BLOCK_SIZE);
    bd.read(block, 0, BLOCK_SIZE);
    printf("%s", block);
    bd.deinit();
}
```
与 MBRBlockDevice 一起使用的 HeapBlockDevice 展示了分区。

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