## SlicingBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.png">

SlicingBlockDevice 类层次结构</div>                                                                 

SlicingBlockDevice 类提供了一种将块设备分解为子单元的方法，而无需手动跟踪偏移。SlicingBlockDevice 充当 ChainingBlockDevice 类的反义词。

构造函数接收主块设备指针以及您希望对子块进行分区的起始和结束地址。通过不指定结束地址，可以创建一个块设备，该设备从提供的起始地址跨越到底层块设备的末尾。

+ bd - 块设备返回 SlicingBlockDevice。
+ start - 起始块地址映射到块 0。负地址从底层块设备的末尾计算。
+ end - 结束块地址以标记块设备的结束。该块未映射；从底层块设备的末尾计算负地址。

## SlicingBlockDevice 类参考
[SlicingBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a67c8248eae9c7391b495b62fd446703f" rel="nofollow" target="_blank">SlicingBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd, bd_addr_t start, bd_addr_t end=0)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ac805693ef7d927fe619cc38b825101e2" rel="nofollow" target="_blank">~SlicingBlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#af4561151f0f90acab401daa85c854cfb" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ad838527f51b82d7c1857aa14437fb9ab" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ab5869ce690250c95708b5f67327bc228" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a0206c88a0ec3616724715de5025ad30d" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ad78736274e9e60a43e37d64e190ee117" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a7e5ecda5789f5f39e0da30fd24a415b8" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ad78736274e9e60a43e37d64e190ee117" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ae83d7b738561d584b8ca0617898f474b" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ad78736274e9e60a43e37d64e190ee117" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a80cdd01eead4aa0c2b3fa9aca1668e18" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a4dc284e7e78fefca0d5741ed34dde987" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a9084dde3fa1da3d6f9d88b840d05d887" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#a3767a71783f4313ec42d9a41813f8876" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#aeac3ddfec4779b54a9f2367988f7c82a" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_slicing_block_device.html#ad78736274e9e60a43e37d64e190ee117" rel="nofollow" target="_blank">size</a> () const</td>
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
		</tr><tr><td style="vertical-align:top;"><a id="a717bc44d8696e432a2c53d1e40d092d3" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bd</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aea9ba3e7c59e7e23f2b48b78e9aa4b17" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_start_from_end</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a2877e858d24403994426085588efdf0c" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_start</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="abab71bc3bff109c4902b7dfdbea16f86" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_stop_from_end</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="aedb6c89a87d9789b1f2e29ee900a023c" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_stop</strong></td>
		</tr></tbody></table>

## SlicingBlockDevice 示例
此 SlicingBlockDevice 示例将 HeapBlockDevice 分区为三个子单元，并通过底层主块设备和切片子单元显示编程和读回数据段。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/SlicingBlockDevice_ex_1/file/62c01cd06ff7/main.cpp)                 
```
#include "mbed.h"
#include "HeapBlockDevice.h"
#include "SlicingBlockDevice.h"
 
#define BLOCK 512
#define NUMSLICES 3
 
char buff[BLOCK];
 
int main(void) {
    // Create a block device with 64 blocks of size 512
    HeapBlockDevice mem(64*BLOCK, BLOCK);
 
    SlicingBlockDevice slices[NUMSLICES] = {
        // Create a block device that maps to the first 32 blocks
        SlicingBlockDevice(&mem, 0 *BLOCK, 32*BLOCK),
    
        // Create a block device that maps to the middle 32 blocks
        SlicingBlockDevice(&mem, 16*BLOCK, -16*BLOCK),
 
        // Create a block device that maps to the last 32 blocks
        SlicingBlockDevice(&mem, 32*BLOCK)
    };
 
    for (int i = 0; i < NUMSLICES; i++) {
        // Initialize and erase the slice to prepar for programming
        slices[i].init();
        slices[i].erase(0, 32*BLOCK);
        
        // Construct the message for the block and write to the slice
        sprintf((char *)&buff, "test: %d", i);
        slices[i].program(&buff, 0, BLOCK);
    }
 
    for (int i = 0; i < NUMSLICES; i++) {
        // Read back the programmed blocks through the underlying block device
        mem.read(&buff, (i * 16 * BLOCK), BLOCK);
        printf("%s  --> ", buff);
        
        // Read back the programmed blocks through the sliced block device.
        slices[i].read(&buff,0, BLOCK);
        printf("%s\r\n", buff);
    }
}
```