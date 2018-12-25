## Flash IAP
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.png">

FlashIAP 类层次结构</div>                                                                         

应用程序编程中的 flash 提供了访问 MCU 内部 flash 的接口。

Flash IAP 设备具有用于不同操作的不同大小的块。它们允许您在定义大小的页面中进行读取和编程，但必须在定义大小的扇区中擦除它们。扇区大小必须是页面大小的倍数。扇区大小可以在设备中不同。

Flash IAP 提供以下功能：

+ 从 flash 设备读取。
+ 将数据编程到 flash 设备页面。
+ 擦除 flash 设备扇区。
+ 获取扇区/flash 或页面大小。
+ 获取 flash 设备的起始地址。

Flash 设备具有一些基于操作的要求和限制。请阅读每项操作的文档。

请注意，Flash IAP 可能会长时间禁用中断。这可能会影响应用程序延迟。

这个类是线程安全的。

## Flash IAP 类参考
查看完整的 C++ API：

[mbed::FlashIAP 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a39fa00030b9c2f503dac92511d87e0cb" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a2508144033abefb374cfb1cd5c240479" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#adcc6fab51a22a7511422b7add6e5f62b" rel="nofollow" target="_blank">read</a> (void *buffer, uint32_t addr, uint32_t size)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a8b135b7ad61c9ec8185f9e1cb8122e7b" rel="nofollow" target="_blank">program</a> (const void *buffer, uint32_t addr, uint32_t size)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a7bef66722193d4c5f214868c505fd3c7" rel="nofollow" target="_blank">erase</a> (uint32_t addr, uint32_t size)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a72f92b4b353a9a434e9317ade0c84a16" rel="nofollow" target="_blank">get_sector_size</a> (uint32_t addr) const</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a3f18e06f2fe5bd00a12cc642143bf5c6" rel="nofollow" target="_blank">get_flash_start</a> () const</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#af3b94e90cbd9e93ac25d4cd48bebf9aa" rel="nofollow" target="_blank">get_flash_size</a> () const</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_flash_i_a_p.html#a27624b32ed2cc77a986d71153a7728d0" rel="nofollow" target="_blank">get_page_size</a> () const</td>
		</tr></tbody></table>

## Flash IAP 示例
有关使用FlashIAP驱动程序的示例，请参阅[引导加载程序示例](https://github.com/ARMmbed/mbed-os-example-bootloader)。
