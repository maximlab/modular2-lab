## DeviceKey
DeviceKey 是一种从信任密钥的根实现密钥派生的机制。DeviceKey 机制生成安全功能所需的对称密钥。您可以使用这些密钥进行加密，身份验证等。DeviceKey API 允许密钥派生而不暴露实际的信任根，以减少在设备外意外暴露信任根的可能性。

我们已经根据 NIST SP 800-108，“计数器模式下的 KDF” 部分实现了 DeviceKey，其中 AES-CMAC 作为伪随机函数。

## 信任的根源
DeviceKey 用于派生其他密钥的信任密钥的根是使用硬件随机生成器（如果存在）或使用在生产过程中注入设备的密钥生成的。

这个信任根所要求的特征是：

+ 每个设备必须是唯一的。
+ 一定很难猜到。
+ 它必须至少为 128 位。
+ 它必须保密。
DeviceKey 功能使用 NVStore 组件将信任密钥的根保留在内部存储中。内部存储可防止对设备的外部物理攻击。

如果设备中有真正的随机数生成器，则首次使用 DeviceKey 时会生成信任根。如果没有可用的真随机数生成器，则必须在调用密钥派生 API 之前将注入的信任密钥根传递给 DeviceKey。

## 密钥派生 API
generate_derived_key：此 API 根据数据数组生成一个新密钥（调用者提供的盐。单个 salt 值始终生成相同的密钥，因此如果需要新密钥，则必须使用新的 salt 值。盐可以是 有任何值 - 数组，字符串等。

生成的密钥长度可以是 128 位或 256 位。

### 信任注入 API 的根

device_inject_root_of_trust：如果设备不支持真正的随机数生成器（未定义 DEVICE_TRNG），则必须在设备的生命周期内调用此 API，然后才能调用密钥派生。

### 使用 DeviceKey

DeviceKey 是一个单例类，这意味着系统只能有一个实例。

要实例化 DeviceKey，您需要调用其 get_instance 成员函数，如下所示：
```
    DeviceKey &deviceKey = DeviceKey::get_instance();
```
测试 DeviceKey

使用 mbed 命令运行 DeviceKey 功能测试，如下所示：
```
    mbed test -n features-device_key-tests-device_key-functionality
```
## DeviceKey API 类参考
[mbed::DeviceKey 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_device_key.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_device_key.html#aa34f89f3fabebfd17c384ea937daabdd" rel="nofollow" target="_blank">generate_derived_key</a> (const unsigned char *isalt, size_t isalt_size, unsigned char *output, uint16_t ikey_type)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_device_key.html#ae7f199bf7c3f0af4ecc8719debfb4f72" rel="nofollow" target="_blank">device_inject_root_of_trust</a> (uint32_t *value, size_t isize)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_device_key.html" rel="nofollow" target="_blank">DeviceKey</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_device_key.html#a65dcaa52dea9e894e9bb4c37ad027a3c" rel="nofollow" target="_blank">get_instance</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>作为单例，返回类的单个实例。此类为单例的原因如下：<a href="https://os.mbed.com/docs/v5.9/reference/devicekey.html#a65dcaa52dea9e894e9bb4c37ad027a3c" rel="nofollow" target="_blank">更多...</a></td>
		</tr></tbody></table>

## DeviceKey 示例
```
/*
* Copyright (c) 2018 ARM Limited. All rights reserved.
* SPDX-License-Identifier: Apache-2.0
* Licensed under the Apache License, Version 2.0 (the License); you may
* not use this file except in compliance with the License.
* You may obtain a copy of the License at
*
* http://www.apache.org/licenses/LICENSE-2.0
*
* Unless required by applicable law or agreed to in writing, software
* distributed under the License is distributed on an AS IS BASIS, WITHOUT
* WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
* See the License for the specific language governing permissions and
* limitations under the License.
*/
 
#include "mbed.h"
#include "DeviceKey.h"
 
//print a unsigned char buffer in hex format
void print_buffer(unsigned char *buf, size_t size)
{
    for (size_t i = 0; i < size; i++) {
        printf("%02X", buf[i]);
    }
}
 
//Injection of a dummy key when there is no TRNG
int inject_rot_key()
{
    uint32_t key[DEVICE_KEY_16BYTE / sizeof(uint32_t)];
 
    memset(key, 0, DEVICE_KEY_16BYTE);
    memcpy(key, "ABCDEF1234567890", DEVICE_KEY_16BYTE);
    int size = DEVICE_KEY_16BYTE;
    DeviceKey& devkey = DeviceKey::get_instance();
    return devkey.device_inject_root_of_trust(key, size);
}
 
// Entry point for the example
int main()
{
    unsigned char derive_key1 [DEVICE_KEY_32BYTE];
    unsigned char derive_key2 [DEVICE_KEY_32BYTE];
    unsigned char salt1[] = "SALT1 ----- SALT1 ------ SALT1";
    unsigned char salt2[] = "SALT2 ----- SALT2 ------ SALT2";
    int ret = DEVICEKEY_SUCCESS;
 
    printf("\n--- Mbed OS DeviceKey example ---\n");
 
    //DeviceKey is a singleton
    DeviceKey& devkey = DeviceKey::get_instance();
 
#if not defined(DEVICE_TRNG)
 
    //If TRNG is not available it is a must to inject the ROT before the first call to derive key method.
    printf("\n--- No TRNG support for this device. injecting ROT. ---\n");
    ret = inject_rot_key();
    if (DEVICEKEY_SUCCESS != ret && DEVICEKEY_ALREADY_EXIST != ret) {
        printf("\n--- Error, injection of ROT key has failed with status %d ---\n", ret);
        return -1;
    }
 
    if ( DEVICEKEY_ALREADY_EXIST == ret ) {
        printf("\n--- ROT Key already exists in the persistent memory. ---\n", ret);
    } else {
        printf("\n--- ROT Key injected and stored in persistent memory. ---\n", ret);
    }
 
#endif
 
    printf("\n--- Using the following salt for key derivation: %s ---\n", salt1);
 
    //16 byte key derivation.
    printf("--- First call to derive key, requesting derived key of 16 byte ---\n");
    ret = devkey.generate_derived_key(salt1, sizeof(salt1), derive_key1, DEVICE_KEY_16BYTE);
    if (DEVICEKEY_SUCCESS != ret) {
        printf("\n--- Error, derive key failed with error code %d ---\n", ret);
        return -1;
    }
 
    printf("--- Derived key1 is: \n");
    print_buffer(derive_key1, DEVICE_KEY_16BYTE);
    printf("\n");
 
    //16 byte key derivation with the same salt should result with the same derived key.
    printf("\n--- Second call to derive key with the same salt. ---\n");
    ret = devkey.generate_derived_key(salt1, sizeof(salt1), derive_key2, DEVICE_KEY_16BYTE);
    if (DEVICEKEY_SUCCESS != ret) {
        printf("\n--- Error, derive key failed with error code %d ---\n", ret);
        return -1;
    }
 
    printf("--- Derived key2 should be equal to key1 from the first call. key2 is: \n");
    print_buffer(derive_key2, DEVICE_KEY_16BYTE);
    printf("\n");
 
    if (memcmp(derive_key1, derive_key2, DEVICE_KEY_16BYTE) != 0) {
        printf("--- Error, first key and second key do not match ---\n");
        return -1;
    } else {
        printf("--- Keys match ---\n");
    }
 
    printf("\n--- Using the following salt for key derivation %s ---\n", salt2);
 
    //16 byte key derivation with the different salt should result with new derived key.
    ret = devkey.generate_derived_key(salt2, sizeof(salt2), derive_key1, DEVICE_KEY_16BYTE);
    if (DEVICEKEY_SUCCESS != ret) {
        printf("\n--- Error, derive key failed with error code %d ---\n", ret);
        return -1;
    }
 
    printf("--- Third call to derive key with the different salt should result with a new derived key1: \n");
    print_buffer(derive_key1, DEVICE_KEY_16BYTE);
    printf("\n");
 
    if (memcmp(derive_key1, derive_key2, DEVICE_KEY_16BYTE) == 0) {
        printf("--- Error, first key and second key do not match ---\n");
        return -1;
    } else {
        printf("--- Keys not match ---\n");
    }
 
    //32 byte key derivation.
    printf("\n--- 32 byte key derivation example. ---\n");
    ret = devkey.generate_derived_key(salt2, sizeof(salt2), derive_key2, DEVICE_KEY_32BYTE);
    if (DEVICEKEY_SUCCESS != ret) {
        printf("\n--- Error, derive key failed with error code %d ---\n", ret);
        return -1;
    }
 
    printf("--- 32 byte derived key is: \n");
    print_buffer(derive_key2, DEVICE_KEY_32BYTE);
    printf("\n");
 
    printf("\n--- Mbed OS DeviceKey example done. ---\n");
 
    return 0;
}
```