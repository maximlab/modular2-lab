## ProfilingBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.png">

ProfilingBlockDevice 类层次结构</div>                                                                 

ProfilingBlockDevice 类为现有块设备对象提供装饰器，以记录读取，写入和擦除。

ProfilingBlockDevices 接收指向被分析的块设备的指针，作为唯一可配置的参数。如果要计算存储操作（如编程，读取或写入块设备），则应使用 ProfilingBlockDevice 对象作为存储块的接口而不是底层设备。以下示例突出显示了此用例。

## ProfilingBlockDevice 类参考
[ProfilingBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a33cadd43ee68e04d709249b91d6f0a77" rel="nofollow" target="_blank">ProfilingBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#aca25a9062f219577b48d9f02417f0f11" rel="nofollow" target="_blank">~ProfilingBlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ac87cd5d6501782681fe392f1a585127a" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a8c000b4335813bec91000092eef75c7b" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ae84c99e8c57a554815370988cf9aad3e" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ad7dad55e346e6e55ea0e7211422eef50" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0c7558a5e525fee52792ed7d37e27b85" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0ef0ea3badf30864c503507af01bd884" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0c7558a5e525fee52792ed7d37e27b85" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0e77bbd609d3ee7993125102eb3bdef5" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0c7558a5e525fee52792ed7d37e27b85" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ab62e17d195060049a8747e63d04234ef" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a45eb6efb3781bcbc289172cfc61e0dd3" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a27fe0db31b78d67ac0a85bc4f7614991" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ad4bb5766366091232fd3fcd0bc19e8b1" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a5b264bd8508e36d52c79156943fabc04" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a0c7558a5e525fee52792ed7d37e27b85" rel="nofollow" target="_blank">size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a1c7338a5db929088196e4d1d494c262d" rel="nofollow" target="_blank">reset</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#ab7267f6d95715727908394c74e1156fc" rel="nofollow" target="_blank">get_read_count</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#a60b72a8a9d3738a3d1aedaeb4c42b5db" rel="nofollow" target="_blank">get_program_count</a> () const</td>
		</tr><tr><td style="vertical-align:top;">bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_profiling_block_device.html#abf2d110b2ce78cc417924399f89c675b" rel="nofollow" target="_blank">get_erase_count</a> () const</td>
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

## ProfilingBlockDevice 示例
创建 ProfilingBlockDevice，执行存储操作并报告读取，写入和擦除计数。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/ProfilingBlockDevice_ex_1/file/20bf5212cdd6/main.cpp)               
```
#include "mbed.h"
#include "HeapBlockDevice.h"
#include "ProfilingBlockDevice.h"
 
#define BLOCK_SIZE 512
 
HeapBlockDevice bd(2048, BLOCK_SIZE); // 2048 bytes with a block size of 512 bytes
uint8_t block[BLOCK_SIZE] = "Hello World!\n";
 
int main() {
    ProfilingBlockDevice profiler(&bd);
    profiler.init();
    profiler.erase(0, BLOCK_SIZE);
    profiler.program(block, 0, BLOCK_SIZE);
    profiler.read(block, 0, BLOCK_SIZE);
    
    printf("%s", block);
    printf("read count: %lld\n", profiler.get_read_count());
    printf("program count: %lld\n", profiler.get_program_count());
    printf("erase count: %lld\n", profiler.get_erase_count());
}
```