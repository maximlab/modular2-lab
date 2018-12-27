## NVStore
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.png">

NVStore 类层次结构</div>                                                                 

NVStore 是一个轻量级模块，出于安全考虑，可以通过内部闪存中的密钥存储数据。对于每个项目键，NVStore 模块提供设置项目数据或获取项目数据的功能。新添加的值将添加到现有数据的末尾，取代之前相同键的值。NVStore 模块可确保在任何操作期间电源故障不会损害现有数据。

## Flash 结构体
NVStore 使用两个 Flash 区域，即活动区域和非活动区域。每个区域必须至少包含一个可擦除单元（扇区）。数据被写入活动区域，直到它变满。如果是，则调用垃圾收集。这将项目从活动区域压缩到非活动区域，并切换区域之间的活动。每个项目都保存在包含标题和数据的条目中，其中标题包含项目键，大小和 CRC。

除非用户特别配置，否则 NVStore 会选择最后两个闪存扇区作为其区域，最小大小为 4KB。这意味着如果扇区较小，NVStore 会为每个区域使用一些连续的扇区。如果自动选择的扇区不适合您的闪存配置，您可以通过为每个板设置 mbed_app.json 中两个区域的地址和大小来覆盖它。

## NVStore 类参考
[NVStore 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a1fb5b9b4922d47aa170ce40744eaea44" rel="nofollow" target="_blank">get_max_keys</a> () const</td>
		</tr><tr><td>&nbsp;</td>
			<td>返回键的数量。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a1fb5b9b4922d47aa170ce40744eaea44" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a4107e7c4ba5fa46c68c5609e9161d5d4" rel="nofollow" target="_blank">set_max_keys</a> (uint16_t num_keys)</td>
		</tr><tr><td>&nbsp;</td>
			<td>设置键数。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a4107e7c4ba5fa46c68c5609e9161d5d4" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">uint16_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#affee5b9d7671df192af13ac84a284ce8" rel="nofollow" target="_blank">get_max_possible_keys</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>返回最大可能的键数（在此闪存配置中）。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#affee5b9d7671df192af13ac84a284ce8" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a9140fe14ca670083ba4c1e616c7bc192" rel="nofollow" target="_blank">get</a> (uint16_t key, uint16_t buf_size, void *buf, uint16_t &amp;actual_size)</td>
		</tr><tr><td>&nbsp;</td>
			<td>返回给定键，在 Flash 上编程的一项数据项。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a9140fe14ca670083ba4c1e616c7bc192" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a0ad70283c11f11a9255e21479c2a2671" rel="nofollow" target="_blank">get_item_size</a> (uint16_t key, uint16_t &amp;actual_size)</td>
		</tr><tr><td>&nbsp;</td>
			<td>给定键，返回 Flash 上编程的数据大小。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a0ad70283c11f11a9255e21479c2a2671" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a2c6d507c55a53db22ae9b3d7f39303bd" rel="nofollow" target="_blank">set</a> (uint16_t key, uint16_t buf_size, const void *buf)</td>
		</tr><tr><td>&nbsp;</td>
			<td>给定密钥，对 Flash 上的一项数据进行编程。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a2c6d507c55a53db22ae9b3d7f39303bd" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a24a6fdbcb4b453db1b2b493d8c230c2f" rel="nofollow" target="_blank">allocate_key</a> (uint16_t &amp;key, uint8_t owner=NVSTORE_UNSPECIFIED_OWNER)</td>
		</tr><tr><td>&nbsp;</td>
			<td>分配一个空闲键（稍后将在设置操作中使用）。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a24a6fdbcb4b453db1b2b493d8c230c2f" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a62e03d28eb58fa055d9d7f0bd46f6baf" rel="nofollow" target="_blank">free_all_keys_by_owner</a> (uint8_t owner)</td>
		</tr><tr><td>&nbsp;</td>
			<td>释放属于特定所有者的所有已分配密钥。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a62e03d28eb58fa055d9d7f0bd46f6baf" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a5db7fccd4633baaecb215fdfc98a2632" rel="nofollow" target="_blank">set_once</a> (uint16_t key, uint16_t buf_size, const void *buf)</td>
		</tr><tr><td>&nbsp;</td>
			<td>在给定密钥的情况下对 Flash 上的一项数据进行编程，不允许对此密钥进行任何后续设置。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a5db7fccd4633baaecb215fdfc98a2632" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#ab6499226c699831a4aee3b8bc0960897" rel="nofollow" target="_blank">remove</a> (uint16_t key)</td>
		</tr><tr><td>&nbsp;</td>
			<td>从闪光灯中删除项目。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#ab6499226c699831a4aee3b8bc0960897" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a8d3c83ac5e41b64ebd29f11b6b0fef0d" rel="nofollow" target="_blank">init</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>初始化 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 组件。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a8d3c83ac5e41b64ebd29f11b6b0fef0d" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#aae18933f5ecfe3949ea2ab40ffaaa3c2" rel="nofollow" target="_blank">deinit</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>取消初始化 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 组件。警告：此功能不是线程安全的，不应与其他 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 功能同时调用。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#aae18933f5ecfe3949ea2ab40ffaaa3c2" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a1143d26af6c2d5c8224c138eaccf2336" rel="nofollow" target="_blank">reset</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>重置 Flash <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 区域。警告：此功能不是线程安全的，不应与其他 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 功能同时调用。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a1143d26af6c2d5c8224c138eaccf2336" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a4527d6fba868d2a21fce0ba95f324de8" rel="nofollow" target="_blank">size</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>返回 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 大小（区域大小）。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a4527d6fba868d2a21fce0ba95f324de8" rel="nofollow" target="_blank">更多...</a></td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a204c8515aff3afae6b69347e46251993" rel="nofollow" target="_blank">get_area_params</a> (uint8_t area, uint32_t &amp;address, size_t &amp;<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#a4527d6fba868d2a21fce0ba95f324de8" rel="nofollow" target="_blank">size</a>)</td>
		</tr><tr><td>&nbsp;</td>
			<td>返回 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> 区域的地址和大小。<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#a204c8515aff3afae6b69347e46251993" rel="nofollow" target="_blank">更多...</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">静态公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html" rel="nofollow" target="_blank">NVStore</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_n_v_store.html#aeb870c670f58208fabb9ad7c536d4cfd" rel="nofollow" target="_blank">get_instance</a> ()</td>
		</tr><tr><td>&nbsp;</td>
			<td>作为单例，返回类的单个实例。此类为单例的原因如下：<a href="https://os.mbed.com/docs/v5.9/reference/nvstore.html#aeb870c670f58208fabb9ad7c536d4cfd" rel="nofollow" target="_blank">更多...</a></td>
		</tr></tbody></table>

## NVStore 示例
[main.cpp](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-nvstore/file/0a3e19b12855/main.cpp)             
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
#include "nvstore.h"
#include <string.h>
#include <stdlib.h>
#include <stdio.h>
 
// Entry point for the example
int main() {
    printf("\n--- Mbed OS NVStore example ---\n");
#if NVSTORE_ENABLED
 
    uint16_t actual_len_bytes = 0;
 
    // NVStore is a sigleton, get its instance
    NVStore &nvstore = NVStore::get_instance();
 
    int rc;
    uint16_t key;
 
    // Values read or written by NVStore need to be aligned to a uint32_t address (even if their sizes
    // aren't)
    uint32_t value;
 
    // Initialize NVstore. Note that it can be skipped, as it is lazily called by all other APIs
    rc = nvstore.init();
    printf("Init NVStore. ");
    printf("Return code is %d\n", rc);
 
    // Show NVStore size, maximum number of keys and area addresses and sizes
    printf("NVStore size is %d\n", nvstore.size());
    printf("NVStore max number of keys is %d (out of %d possible ones in this flash configuration)\n",
            nvstore.get_max_keys(), nvstore.get_max_possible_keys());
    printf("NVStore areas:\n");
    for (uint8_t area = 0; area < NVSTORE_NUM_AREAS; area++) {
        uint32_t area_address;
        size_t area_size;
        nvstore.get_area_params(area, area_address, area_size);
        printf("Area %d: address 0x%08lx, size %d (0x%x)\n", area, area_address, area_size, area_size);
    }
 
    // Clear NVStore data. Should only be done once at factory configuration
    rc = nvstore.reset();
    printf("Reset NVStore. ");
    printf("Return code is %d\n", rc);
 
    // Now set some values to the same key
    key = 1;
 
    value = 1000;
    rc = nvstore.set(key, sizeof(value), &value);
    printf("Set key %d to value %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    value = 2000;
    rc = nvstore.set(key, sizeof(value), &value);
    printf("Set key %d to value %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    value = 3000;
    rc = nvstore.set(key, sizeof(value), &value);
    printf("Set key %d to value %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    // Get the value of this key (should be 3000)
    rc = nvstore.get(key, sizeof(value), &value, actual_len_bytes);
    printf("Get key %d. Value is %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    // Now remove the key
    rc = nvstore.remove(key);
    printf("Delete key %d. ", key);
    printf("Return code is %d\n", rc);
 
    // Get the key again, now it should not exist
    rc = nvstore.get(key, sizeof(value), &value, actual_len_bytes);
    printf("Get key %d. ", key);
    printf("Return code is %d\n", rc);
 
    key = 12;
 
    // Now set another key once (it can't be set again)
    value = 50;
    rc = nvstore.set_once(key, sizeof(value), &value);
    printf("Set key %d once to value %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    // This should fail on key already existing
    value = 100;
    rc = nvstore.set(key, sizeof(value), &value);
    printf("Set key %d to value %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    // Get the value of this key (should be 50)
    rc = nvstore.get(key, sizeof(value), &value, actual_len_bytes);
    printf("Get key %d. Value is %ld. ", key, value);
    printf("Return code is %d\n", rc);
 
    // Get the data size for this key (should be 4)
    rc = nvstore.get_item_size(key, actual_len_bytes);
    printf("Data size for key %d is %d. ", key, actual_len_bytes);
    printf("Return code is %d\n", rc);
#else
    printf("NVStore is disabled for this board\n");
#endif
 
    printf("\n--- Mbed OS NVStore example done. ---\n");
}

```