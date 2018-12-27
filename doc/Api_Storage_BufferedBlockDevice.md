## BufferedBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.png">

BufferedBlockDevice 类层次结构</div>                                                                 

BufferedBlockDevice 类是块设备 adpator，其目的是将底层块设备的读取和程序大小减少到 1。大的读取和/或程序大小可能使块设备用户的生活变得困难，因此 BufferedBlockDevice 将两个大小减小到最小值，对底层 BD 的读写操作使用内部缓冲区。调用同步 API 可确保将写入刷新到底层 BD。

构造函数只需要底层块设备指针。

+ bd - 块设备支持 BufferedBlockDevice。

## BufferedBlockDevice 类参考
[BufferedBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a6c90813f0dd32eb9427770bf91133823" rel="nofollow" target="_blank">BufferedBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd)</td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a57530b25198222816288c71b216f3761" rel="nofollow" target="_blank">~BufferedBlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a3a670a9ccb99832697c82f8c6fc53723" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a370c7b39c9689fb2013107d0f84cfca5" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#af289792b36a5288ccbc6165c21ad9616" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#aa383c67926c4bc0e181f561e7616e482" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a38f4c3c7a5278c71761aca0a1296278c" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a77d28188d7730246cf5e04f75929ec9a" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a38f4c3c7a5278c71761aca0a1296278c" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a248ae3c72bae60de99c1b637f96ba05b" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a38f4c3c7a5278c71761aca0a1296278c" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a0c7b7ede8a770b7fb456a51c87f5ebda" rel="nofollow" target="_blank">trim</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a38f4c3c7a5278c71761aca0a1296278c" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a642e2ee52fae017f3a42135d0ffc328c" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a6d7ff6a5e2032057818410eaca8ad852" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a2194903c2c78c2fa3ddacc4ac62e72b9" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a62daa66a69f72501a424e3170e81182d" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#ae8d40ff95827b62eec60c4bbcab00c02" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#a38f4c3c7a5278c71761aca0a1296278c" rel="nofollow" target="_blank">size</a> () const</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a397713428dd2b787174b6ca43231c1f9" rel="nofollow" target="_blank">~BlockDevice</a> ()</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#adb348252c273554b08a4826477786ccd" rel="nofollow" target="_blank">is_valid_read</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#af341e26902d727513dfe9ff4d6232751" rel="nofollow" target="_blank">is_valid_program</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr><tr><td style="vertical-align:top;">bool&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#a0a5c01f28bdcd360f56f0f8e636067f2" rel="nofollow" target="_blank">is_valid_erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html#aadd381b4f44d82d402c84eb07bd2ba1b" rel="nofollow" target="_blank">size</a>) const</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_buffered_block_device.html#ab3cce2cc37af6bb96cb4105487c6bb18" rel="nofollow" target="_blank">flush</a> ()</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="a5b7dc1ba8fd0012fd879d7e1920e3322" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bd</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a7d71c3930f02435857237900d6762b9c" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_bd_program_size</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a75f00029990f3c4f89cdcb6edba767cf" target="_blank"></a> bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_curr_aligned_addr</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="abcb02ea36b0da67723c265fcdf7bcafc" target="_blank"></a> bool&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_flushed</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a140ab03f5ca384ecdfbac6a79c15b3d6" target="_blank"></a> uint8_t *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_cache</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a4833047c557d3d53ccb96af1e1635369" target="_blank"></a> uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_init_ref_count</strong></td>
		</tr></tbody></table>

## BufferedBlockDevice 示例
这个 BufferedBlockDevice 示例采用 HeapBlockDevice，其读取大小为 256 字节，程序大小为 512 字节，并显示了如何使用 BufferedBlockDevice 读取或编程具有更小读取/程序大小的块设备。
```
     HeapBlockDevice heap_bd(1024, 256, 512, 512);
    BufferedBlockDevice buf_bd(&heap_bd);
 
    // This initializes the buffered block device (as well as the underlying heap block device)
    int err = buf_bd.init();
 
    uint8_t buf[8];
    for (int i = 0; i < sizeof(buf); i++) {
         buf[i] = i;
    }
 
    // Now we can program an 8 byte buffer (couldn't do that in underlying BD, having 512-byte program size)
    err = buf_bd.program(buf, 0, sizeof(buf));
 
    // Now we can also read one byte
    err = buf_bd.read(buf, 0, 1);
 
    // Ensure programmed data is flushed to the underlying block device
    err = buf_bd.sync();
```