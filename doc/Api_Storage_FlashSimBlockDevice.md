## FlashSimBlockDevice
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.png">

FlashSimBlockDevice 类层次结构</div>                                                                 

FlashSimBlockDevice 类是块设备 adpator，其目的是在底层块设备不支持此类行为时模拟闪存组件的行为。这包括以下内容：

+ 支持 erase API（用预定义的擦除值填充擦除单元）。
+ 仅允许对擦除区域或其内容与用户给出的内容相同的区域进行编程。
+ 支持 get\_erase\_value API，返回预定义的擦除值。

构造函数需要以下内容：

+ bd - 块设备支持 FlashSimBlockDevice。
+ erase_value - 擦除操作后给擦除单元的每个字节赋予的值（默认为 0xFF）。

## FlashSimBlockDevice 类参考
[FlashSimBlockDevice 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a2b1e84d9b4a49f981e9a339e91c2d15d" rel="nofollow" target="_blank">FlashSimBlockDevice</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd, uint8_t erase_value=0xFF)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a8c47d93f2790ff20b840d9a682ae04f2" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a4c0aa1279cc08fe5e9fa8cfb67d7a6d7" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#ad1787a2be965d4230d4403806c4676f7" rel="nofollow" target="_blank">sync</a> ()</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a193b4ce164a63cc94a243518863c5e0d" rel="nofollow" target="_blank">read</a> (void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a7ba67745b6c7a28053ffdd34747b6ea3" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#aac956b734fd0e36d432f14ee0e20f497" rel="nofollow" target="_blank">program</a> (const void *buffer, bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a7ba67745b6c7a28053ffdd34747b6ea3" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#ab5ec16f660c6877daba0f4b26297c7ad" rel="nofollow" target="_blank">erase</a> (bd_addr_t addr, bd_size_t <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a7ba67745b6c7a28053ffdd34747b6ea3" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a644710b1a3ec350df4fa3eea60b38e6e" rel="nofollow" target="_blank">get_read_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a15316fc5466933d780b776ecd3880b15" rel="nofollow" target="_blank">get_program_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a169e3875c6afbf046a4154716d04c197" rel="nofollow" target="_blank">get_erase_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a27abb968f9a7b8b51b732086b1246860" rel="nofollow" target="_blank">get_erase_size</a> (bd_addr_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a0953be8a3b4024956073b37973944829" rel="nofollow" target="_blank">get_erase_value</a> () const</td>
		</tr><tr><td style="vertical-align:top;">virtual bd_size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_flash_sim_block_device.html#a7ba67745b6c7a28053ffdd34747b6ea3" rel="nofollow" target="_blank">size</a> () const</td>
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

## FlashSimBlockDevice 示例
此 FlashSimBlockDevice 示例采用 HeapBlockDevice 并将其转换为模拟 Flash BD。
```
    int erase_unit_size = 512;
    HeapBlockDevice heap_bd(4 * erase_unit_size, 1, 4, erase_unit_size);
    FlashSimBlockDevice flash_bd(&heap_bd, blank);
 
    // This initializes the flash simulator block device (as well as the underlying heap block device)
    int err = flash_bd.init();
 
    uint8_t buf[16];
    for (int i = 0; i < sizeof(buf); i++) {
        buf[i] = i;
    }
 
    // This will fail, as erase unit in address 0 has not been erased
    err = flash_bd.program(buf, 0, sizeof(buf));
 
    // Erase the erase unit at address 0
    err = flash_bd.erase(0, erase_unit_size);
 
    // This will succeed now after erasing
    err = flash_bd.program(buf, 0, sizeof(buf));
```