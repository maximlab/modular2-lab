## MbedCRC
MbedCRC 类支持循环冗余校验（CRC）算法。MbedCRC 是一个模板类，其多项式值和多项式宽度作为参数。

您可以使用计算 API 计算所选多项式的 CRC。如果数据在部分中可用，则必须按正确的顺序调用 compute_partial_start，compute_partial 和 compute_partial_stop API 以获取正确的 CRC 值。您可以使用 get_polynomial 和 get_width API 来了解当前对象的多项式和宽度值。

ROM 多项式表用于支持的 8/16 位 CCITT，16 位 IBM 和 32 位 ANSI 多项式。默认情况下，ROM 表用于 CRC 计算。如果 ROM 表不可用，则在运行时逐位计算所有数据输入的 CRC。

对于支持[硬件 CRC](https://os.mbed.com/docs/v5.9/reference/hardware-crc.html) 的平台，MbedCRC API 取代了 CRC 的软件实现，以利用平台提供的硬件加速。

## MbedCRC 类参考
[mbed::MbedCRC< polynomial, width > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html)

<table><tbody><tr><td colspan="2">公共类型</td>
		</tr><tr><td style="vertical-align:top;"><a id="a460b4a23de42769fdfea09bfbdf5f370" target="_blank"></a>enum &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>CrcMode</strong> { <strong>HARDWARE</strong> = 0, <strong>TABLE</strong> = 1, <strong>BITWISE</strong> }</td>
		</tr><tr><td style="vertical-align:top;"><a id="a74a3b0f7cede6da24b596640eda679ea" target="_blank"></a> typedef uint64_t&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>crc_data_size_t</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#a00dd2fd5840f07683b99f5580a87fbe9" rel="nofollow" target="_blank">MbedCRC</a> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#aa16c2dfcfb60d912defec6aefe1d2445" rel="nofollow" target="_blank">compute</a> (void *buffer, crc_data_size_t size, uint32_t *crc)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#a5a16dba5203cafc08456c8201c29ebcd" rel="nofollow" target="_blank">compute_partial</a> (void *buffer, crc_data_size_t size, uint32_t *crc)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#a79f254dcb21ddc55392c7e0414e03903" rel="nofollow" target="_blank">compute_partial_start</a> (uint32_t *crc)</td>
		</tr><tr><td style="vertical-align:top;">int32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#a3b04710727e681b9029d5f321ae63cd0" rel="nofollow" target="_blank">compute_partial_stop</a> (uint32_t *crc)</td>
		</tr><tr><td style="vertical-align:top;">uint32_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#a164d73b75ab7c3d60e518f4a93f281bd" rel="nofollow" target="_blank">get_polynomial</a> (void) const</td>
		</tr><tr><td style="vertical-align:top;">uint8_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_mbed_c_r_c.html#ab804b27ccd1460aaed8f7d94c8f6931b" rel="nofollow" target="_blank">get_width</a> (void) const</td>
		</tr><tr><td colspan="2"><a id="aae2f4bc3ff10267b1e8e079fe81f2b5b" target="_blank"></a> template&lt;&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>MbedCRC</strong> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr><tr><td colspan="2"><a id="a7aab3db6bc864858b7b0b97c236314e5" target="_blank"></a> template&lt;&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>MbedCRC</strong> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr><tr><td colspan="2"><a id="abe056bfdd49cc8ade256ed99b358f2fe" target="_blank"></a> template&lt;&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>MbedCRC</strong> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr><tr><td colspan="2"><a id="ac5b4e9201a534557c1d4b75a29f70d58" target="_blank"></a> template&lt;&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>MbedCRC</strong> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr><tr><td colspan="2"><a id="a5b8ec34a0be1f6699fac17747d07dc08" target="_blank"></a> template&lt;&gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>MbedCRC</strong> (uint32_t initial_xor, uint32_t final_xor, bool reflect_data, bool reflect_remainder)</td>
		</tr></tbody></table>
        
## MbedCRC 示例
### 示例一

下面是计算 32 位 CRC 的 CRC 示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/CRC_example/file/a9d9b5c4a32b/main.cpp)        
```
#include "mbed.h"
 
int main()
{
    MbedCRC<POLY_32BIT_ANSI, 32> ct;
 
    char  test[] = "123456789";
    uint32_t crc = 0;
 
    printf("\nPolynomial = 0x%lx  Width = %d \n", ct.get_polynomial(), ct.get_width());
 
    ct.compute((void *)test, strlen((const char*)test), &crc);
    printf("The CRC of data \"123456789\" is : 0x%lx\n", crc);
    return 0;
 }
``` 
### 示例二

下面是使用 compute_partial API 的 32 位 CRC 示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/CRC_partial_example/file/834c44916a38/main.cpp)
```
#include "mbed.h"
 
int main() {
    MbedCRC<POLY_32BIT_ANSI, 32> ct;
 
    char  test[] = "123456789";
    uint32_t crc;
 
    ct.compute_partial_start(&crc);
    ct.compute_partial((void *)&test, 4, &crc);
    ct.compute_partial((void *)&test[4], 5, &crc);
    ct.compute_partial_stop(&crc);
    
    printf("The CRC of 0x%x \"123456789\" is \"0xCBF43926\" Result: 0x%x\n", 
                            ct.get_polynomial(), crc);
    
    return 0;
}
``` 
### 示例三

以下是 SD 驱动程序的 CRC 示例。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/CRC_eample_sd/file/ee110889fa99/main.cpp)      
```
#include "mbed.h"
 
int crc_sd_7bit()
{
    MbedCRC<POLY_7BIT_SD, 7> ct;
    char test[5];
    uint32_t crc;
 
    test[0] = 0x40;
    test[1] = 0x00;
    test[2] = 0x00;
    test[3] = 0x00;
    test[4] = 0x00;
 
    ct.compute((void *)test, 5, &crc);
    // CRC 7-bit as 8-bit data
    crc = (crc | 0x01) & 0xFF;
    printf("The CRC of 0x%x \"CMD0\" is \"0x95\" Result: 0x%x\n",
           ct.get_polynomial(), crc);
 
    test[0] = 0x48;
    test[1] = 0x00;
    test[2] = 0x00;
    test[3] = 0x01;
    test[4] = 0xAA;
 
    ct.compute((void *)test, 5, &crc);
    // CRC 7-bit as 8-bit data
    crc = (crc | 0x01) & 0xFF;
    printf("The CRC of 0x%x \"CMD8\" is \"0x87\" Result: 0x%x\n",
           ct.get_polynomial(), crc);
 
    test[0] = 0x51;
    test[1] = 0x00;
    test[2] = 0x00;
    test[3] = 0x00;
    test[4] = 0x00;
 
    ct.compute((void *)test, 5, &crc);
    // CRC 7-bit as 8-bit data
    crc = (crc | 0x01) & 0xFF;
    printf("The CRC of 0x%x \"CMD17\" is \"0x55\" Result: 0x%x\n",
           ct.get_polynomial(), crc);
 
    return 0;
}
 
int crc_sd_16bit()
{
    char test[512];
    uint32_t crc;
    MbedCRC<POLY_16BIT_CCITT, 16> sd(0, 0, false, false);
 
    memset(test, 0xFF, 512);
    // 512 bytes with 0xFF data --> CRC16 = 0x7FA1
    sd.compute((void *)test, 512, &crc);
    printf("16BIT SD CRC (512 bytes 0xFF) is \"0x7FA1\" Result: 0x%x\n", crc);
    return 0;
}
 
int main()
{
    crc_sd_16bit();
    crc_sd_7bit();
    return 0;
}
``` 
