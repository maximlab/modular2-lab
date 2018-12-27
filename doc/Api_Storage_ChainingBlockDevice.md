## ChainingBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.png">

ChainingBlockDevice 类层次结构</div>                                                                 

ChainingBlockDevice 类提供了一种将多个块设备链接在一起的方法。然后，您可以与链接块设备进行交互，就好像它们是大小等于每个子层单元总和的单块设备一样。ChainingBlockDevice 与 SlicingBlockDevice 相反。

请注意，每个块设备的块大小必须是其他设备块大小的倍数（512，1024 等）。

构造函数接收块设备指针数组，并提供一个对象，您可以从中将对象块设备作为单个设备进行访问。

## ChainingBlockDevice 类参考
[ChainingBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#afc72d4defca6ad31fa3d521d5d56b5a1" rel="nofollow" target="_blank">ChainingBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> **bds, size_t bd_count)</td>
		</tr><tr><td colspan="2">template&lt;size_t Size&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a465e9d19db289246a5aa23dca36129c8" rel="nofollow" target="_blank">ChainingBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *(&amp;bds)[Size])</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a691ad5c20f92613592e3451b286308ee" rel="nofollow" target="_blank">~ChainingBlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#ad617e329aa17268ee8c75784f74c98ec" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#ac552ff651a1a8173683198043e4a5477" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a8cecee8bbe8912a63724468385d994d9" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#adf6c158ac8341e36c9133fbbb0d59a44" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a628236bba9e151111d2af3ad9747d015" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#acade067e2d25c6e1f94d9ed3723a7e51" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a628236bba9e151111d2af3ad9747d015" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a31142761e93621778c211380bc12570d" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a628236bba9e151111d2af3ad9747d015" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a46ea20de812b6d11903a796b9a6c520d" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a7f02790be1bc46fbc835a134c2dc3f1d" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#acb2a1bf410184dd6148bc8508a770b02" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#aac77ada2af5ba54aae4a225b524d7ef6" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a6c87e02b989d4b0b1ee90a516beba56e" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_chaining_block_device.html#a628236bba9e151111d2af3ad9747d015" rel="nofollow" target="_blank">size</a> () const</td>
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
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a75f6756118f6fbe0de026aa815364da5" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> **&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bds</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2099b6993317d156451d0c3ff29de547" target="_blank"></a> size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bd_count</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a3c50eebfc3a04e858464b0b700d4309f" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_read_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="af24dfdb87bee4bb1016bf17b8d452d7e" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_program_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a50fd7001bbd9d48349a94efe84fdb041" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_erase_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a03b3009f62d128cf0082dce6f0ecb7f5" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a51c5990e0bc42a6d48e657076cc25e1d" target="_blank"></a> int&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_erase_value</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a29b08fcb85c75e03d50fe24a3d361485" target="_blank"></a> uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_init_ref_count</strong></td>
		</tr></tbody></table>

## ChainingBlockDevice 示例
此 ChainingBlockDevice 示例跨多个 HeapBlockDevices 创建 FAT 文件系统。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/ChainingBlockDevice_ex_1/file/8ad9777787ba/main.cpp)                
```
#include "mbed.h"
#include "HeapBlockDevice.h"
#include "ChainingBlockDevice.h"
#include "FATFileSystem.h"
    
int main(void) {
    // Create two smaller block devices with
    // 64 and 32 blocks of size 512 bytes
    HeapBlockDevice mem1(64*512, 512);
    HeapBlockDevice mem2(32*512, 512);
    
    // Create a block device backed by mem1 and mem2
    // contains 96 blocks of size 512 bytes
    BlockDevice *bds[] = {&mem1, &mem2};
    ChainingBlockDevice chainmem(bds);
    
    // Format the new chained block device with a FAT filesystem
    FATFileSystem::format(&chainmem);
    
    // Create the FAT filesystem instance, files can now be written to
    // the FAT filesystem as if to a single 96 x 512 byte storage device
    FATFileSystem fat("fat", &chainmem);
}
```
此 ChainingBlockDevice 示例显示如何从链接的 HeapBlockDevices 组中编程和读取数据。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/ChainingBlockDevice_ex_2/file/70419b9d778a/main.cpp)                
```
#include "mbed.h"
#include "HeapBlockDevice.h"
#include "ChainingBlockDevice.h"
 
#define BLOCKSIZE 512
char buffer1[512];
char buffer2[512];
 
int main(void) {
    // Create two smaller block devices with
    // 64 and 32 blocks of size 512 bytes
    HeapBlockDevice mem1(64*BLOCKSIZE, BLOCKSIZE);
    HeapBlockDevice mem2(32*BLOCKSIZE, BLOCKSIZE);
    
    // Create a block device backed by mem1 and mem2
    // contains 96 blocks of size 512 bytes
    BlockDevice *bds[] = {&mem1, &mem2};
    ChainingBlockDevice chainmem(bds);
    
    // Initialize the block devices
    chainmem.init();
    
    // Erase the block device to prepare for programming. 64 and 32 refer to
    // the respective number of blocks in mem1 and mem2
    chainmem.erase(0, (BLOCKSIZE * (64 + 32)));
    
    // Program strings to the block device at byte-addressable locations that
    // span both sub blocks. The second program will write past the end of the
    // first block
    chainmem.program("data for block", 0, BLOCKSIZE);
    chainmem.program("Some more data", (65 * BLOCKSIZE), BLOCKSIZE);
    
    // Readback the written values
    chainmem.read(&buffer1, 0, BLOCKSIZE);
    chainmem.read(&buffer2, (65 * BLOCKSIZE), BLOCKSIZE);
    printf("Read back: %s, %s\r\n", buffer1, buffer2);
}
```