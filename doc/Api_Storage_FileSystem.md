## FileSystem
文件系统 API 提供用于在[基于块的存储设备](https://os.mbed.com/docs/v5.9/reference/blockdevice-port.html)上实现文件系统的公共接口。文件系统 API 是基于类的接口，但实现文件系统 API 提供了 C 用户熟悉的标准 POSIX 文件 API。

FileSystem 的主要目的是实例化。FileSystem 的构造函数可以接受指定为字符串的 BlockDevice 和挂载点，以及其他特定于实现的配置选项。然后，当与 POSIX API 一起使用时，挂载点可以充当 Mbed OS 中任何路径中的第一个目录。这使您可以访问文件系统内的文件。如果您只需要将 FileSystem 用作 C++ 对象，则挂载点可以为 NULL。

FileSystem 的 file 和 dir 函数受到保护，因为您不应直接使用 FileSystem file 和 dir 函数。它们只是实现者的便利。相反，[File](https://os.mbed.com/docs/v5.9/reference/file.html) 和 [Dir](https://os.mbed.com/docs/v5.9/reference/dir.html) 类提供对 C++ 类中的文件和目录操作的访问，这些操作遵循 [RAII](https://os.mbed.com/docs/v5.9/introduction/glossary.html#r) 和其他 C++ 约定。

## 文件系统类参考
[mbed::FileSystem 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#aa17f1029c8ac6c598d259c6b932f49d7" rel="nofollow" target="_blank">FileSystem</a> (const char *name=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a9933e8de2575c134ac5f160031163fc1" rel="nofollow" target="_blank">mount</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a5a2e5083617e795cdf7c94fd3a0d5015" rel="nofollow" target="_blank">unmount</a> ()=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a19b7c0f4bca1b5356b2f02e459237533" rel="nofollow" target="_blank">reformat</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/class_block_device.html" rel="nofollow" target="_blank">BlockDevice</a> *bd=NULL)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ab4dfb7026de84272e863064df3ff0c58" rel="nofollow" target="_blank">remove</a> (const char *path)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a30ec5e2cecc15381af09b50f8ff859a9" rel="nofollow" target="_blank">rename</a> (const char *path, const char *newpath)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ac37eb376c2ca809c4ba03a8db33ab9cc" rel="nofollow" target="_blank">stat</a> (const char *path, struct <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structstat.html" rel="nofollow" target="_blank">stat</a> *st)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#abb69b6a14c5147756c65d747ecdc87a2" rel="nofollow" target="_blank">mkdir</a> (const char *path, mode_t mode)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ae31f4e6bbef5396dcbbad64a55ef63d3" rel="nofollow" target="_blank">statvfs</a> (const char *path, struct <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structstatvfs.html" rel="nofollow" target="_blank">statvfs</a> *buf)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_like.html" rel="nofollow" target="_blank">mbed::FileSystemLike</a></td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_like.html#a8d22ee33da6cb4122bf9e92e90ea3bca" rel="nofollow" target="_blank">FileSystemLike</a> (const char *name=NULL)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html" rel="nofollow" target="_blank">FileHandle</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_like.html#a29837fc13cf1b544c2d735369de9f600" rel="nofollow" target="_blank">open</a> (const char *path, int flags)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_dir_handle.html" rel="nofollow" target="_blank">DirHandle</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_like.html#a4b83f5f22890428d95dd24c1dcbc387f" rel="nofollow" target="_blank">opendir</a> (const char *path)</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_handle.html" rel="nofollow" target="_blank">mbed::FileSystemHandle</a></td>
		</tr><tr><td style="vertical-align:top;">virtual&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system_handle.html#ab74b65acb7605c21079d797aaef359a4" rel="nofollow" target="_blank">~FileSystemHandle</a> ()</td>
		</tr><tr><td colspan="2">&nbsp;公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">mbed::FileBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a8b19f5dfe489eaa641c32a5096c71af1" target="_blank"></a> &nbsp;</td>
			<td style="vertical-align:bottom;"><strong>FileBase</strong> (const char *name, PathType t)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a22078733b15abf28045948d24555ceaf" target="_blank"></a> const char *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getName</strong> (void)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a59dd77df265c99a2fa0f7c209d0dba18" target="_blank"></a> PathType&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>getPathType</strong> (void)</td>
		</tr></tbody></table>
 <table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a6eecb378bbf54fc9e686a74825fa1d82" rel="nofollow" target="_blank">file_open</a> (fs_file_t *file, const char *path, int flags)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a318c9434c48d315a70fbd93956ab3f33" rel="nofollow" target="_blank">file_close</a> (fs_file_t file)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual ssize_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ae9d7326c020637ade523abeaa98b0447" rel="nofollow" target="_blank">file_read</a> (fs_file_t file, void *buffer, size_t size)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual ssize_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a80e6613d60228ad262e3f43d58a8a83f" rel="nofollow" target="_blank">file_write</a> (fs_file_t file, const void *buffer, size_t size)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#af259d1d38e1ea36920acbe7ce473de90" rel="nofollow" target="_blank">file_sync</a> (fs_file_t file)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a23be48b8959e8f2e86d6cad8646cf189" rel="nofollow" target="_blank">file_isatty</a> (fs_file_t file)</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a9a655c3107e0c80d17e0baca2598c0eb" rel="nofollow" target="_blank">file_seek</a> (fs_file_t file, off_t offset, int whence)=0</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a5a23bc38a89f54440637a72962ad7a98" rel="nofollow" target="_blank">file_tell</a> (fs_file_t file)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a7c0d21068b90bfdbc042b234cfb00b45" rel="nofollow" target="_blank">file_rewind</a> (fs_file_t file)</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a66f020f51b28222ab20b87a677203584" rel="nofollow" target="_blank">file_size</a> (fs_file_t file)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a1ce81bee0678b3f9fc89705b6284e98a" rel="nofollow" target="_blank">dir_open</a> (fs_dir_t *dir, const char *path)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a8fbdb82bfe95cadd378df80fd68c4545" rel="nofollow" target="_blank">dir_close</a> (fs_dir_t dir)</td>
		</tr><tr><td style="vertical-align:top;">virtual ssize_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a5e10db23f87cac5f53592535e5b45707" rel="nofollow" target="_blank">dir_read</a> (fs_dir_t dir, struct <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structdirent.html" rel="nofollow" target="_blank">dirent</a> *ent)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ad1ba403660ffc82af21bf041505fdf68" rel="nofollow" target="_blank">dir_seek</a> (fs_dir_t dir, off_t offset)</td>
		</tr><tr><td style="vertical-align:top;">virtual off_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a88c763813fd5835662c95f8a170c29fb" rel="nofollow" target="_blank">dir_tell</a> (fs_dir_t dir)</td>
		</tr><tr><td style="vertical-align:top;">virtual void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a4c7536e6da01a448f4158e1074c4cf5e" rel="nofollow" target="_blank">dir_rewind</a> (fs_dir_t dir)</td>
		</tr><tr><td style="vertical-align:top;">virtual size_t&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a45636d2821cbd10d9c70e01bcea55c88" rel="nofollow" target="_blank">dir_size</a> (fs_dir_t dir)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#a6517866e33b90412b0cce1b2f10474c3" rel="nofollow" target="_blank">open</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_handle.html" rel="nofollow" target="_blank">FileHandle</a> **file, const char *path, int flags)</td>
		</tr><tr><td style="vertical-align:top;">virtual int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_system.html#ab493b844d2aa0b4f23e8b303b905c57f" rel="nofollow" target="_blank">open</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_dir_handle.html" rel="nofollow" target="_blank">DirHandle</a> **dir, const char *path)</td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2"><a name="friends" target="_blank"></a> 友元</td>
		</tr><tr><td style="vertical-align:top;"><a id="a68d15876ad188b7628261b12d0eac8aa" target="_blank"></a> class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>File</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a9c037aa57ccb12f75092ea55062c933e" target="_blank"></a> class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Dir</strong></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">其他继承成员</td>
		</tr><tr><td colspan="2">&nbsp;静态公共成员函数继承自 <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">mbed::FileBase</a></td>
		</tr><tr><td style="vertical-align:top;"><a id="a227997f93c4171392e6aa3868c705a36" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">FileBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>lookup</strong> (const char *name, unsigned int len)</td>
		</tr><tr><td style="vertical-align:top;"><a id="a7fb679a04a646da30923820a7c505a19" target="_blank"></a> static <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_file_base.html" rel="nofollow" target="_blank">FileBase</a> *&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>get</strong> (int n)</td>
		</tr></tbody></table>

## 文件系统示例
[main.cpp](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-filesystem/file/adaa6c01d727/main.cpp)           
```
/* mbed Microcontroller Library
 * Copyright (c) 2006-2013 ARM Limited
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#include "mbed.h"
#include <stdio.h>
#include <errno.h>
 
// Block devices
#include "SPIFBlockDevice.h"
#include "DataFlashBlockDevice.h"
#include "SDBlockDevice.h"
#include "HeapBlockDevice.h"
 
// File systems
#include "LittleFileSystem.h"
#include "FATFileSystem.h"
 
 
// Physical block device, can be any device that supports the BlockDevice API
SPIFBlockDevice bd(
        MBED_CONF_SPIF_DRIVER_SPI_MOSI,
        MBED_CONF_SPIF_DRIVER_SPI_MISO,
        MBED_CONF_SPIF_DRIVER_SPI_CLK,
        MBED_CONF_SPIF_DRIVER_SPI_CS);
 
// File system declaration
LittleFileSystem fs("fs");
 
 
// Set up the button to trigger an erase
InterruptIn irq(BUTTON1);
void erase() {
    printf("Initializing the block device... ");
    fflush(stdout);
    int err = bd.init();
    printf("%s\n", (err ? "Fail :(" : "OK"));
    if (err) {
        error("error: %s (%d)\n", strerror(-err), err);
    }
 
    printf("Erasing the block device... ");
    fflush(stdout);
    err = bd.erase(0, bd.size());
    printf("%s\n", (err ? "Fail :(" : "OK"));
    if (err) {
        error("error: %s (%d)\n", strerror(-err), err);
    }
 
    printf("Deinitializing the block device... ");
    fflush(stdout);
    err = bd.deinit();
    printf("%s\n", (err ? "Fail :(" : "OK"));
    if (err) {
        error("error: %s (%d)\n", strerror(-err), err);
    }
}
 
 
// Entry point for the example
int main() {
    printf("--- Mbed OS filesystem example ---\n");
 
    // Setup the erase event on button press, use the event queue
    // to avoid running in interrupt context
    irq.fall(mbed_event_queue()->event(erase));
 
    // Try to mount the filesystem
    printf("Mounting the filesystem... ");
    fflush(stdout);
    int err = fs.mount(&bd);
    printf("%s\n", (err ? "Fail :(" : "OK"));
    if (err) {
        // Reformat if we can't mount the filesystem
        // this should only happen on the first boot
        printf("No filesystem found, formatting... ");
        fflush(stdout);
        err = fs.reformat(&bd);
        printf("%s\n", (err ? "Fail :(" : "OK"));
        if (err) {
            error("error: %s (%d)\n", strerror(-err), err);
        }
    }
 
    // Open the numbers file
    printf("Opening \"/fs/numbers.txt\"... ");
    fflush(stdout);
    FILE *f = fopen("/fs/numbers.txt", "r+");
    printf("%s\n", (!f ? "Fail :(" : "OK"));
    if (!f) {
        // Create the numbers file if it doesn't exist
        printf("No file found, creating a new file... ");
        fflush(stdout);
        f = fopen("/fs/numbers.txt", "w+");
        printf("%s\n", (!f ? "Fail :(" : "OK"));
        if (!f) {
            error("error: %s (%d)\n", strerror(errno), -errno);
        }
 
        for (int i = 0; i < 10; i++) {
            printf("\rWriting numbers (%d/%d)... ", i, 10);
            fflush(stdout);
            err = fprintf(f, "    %d\n", i);
            if (err < 0) {
                printf("Fail :(\n");
                error("error: %s (%d)\n", strerror(errno), -errno);
            }
        }
        printf("\rWriting numbers (%d/%d)... OK\n", 10, 10);
 
        printf("Seeking file... ");
        fflush(stdout);
        err = fseek(f, 0, SEEK_SET);
        printf("%s\n", (err < 0 ? "Fail :(" : "OK"));
        if (err < 0) {
            error("error: %s (%d)\n", strerror(errno), -errno);
        }
    }
 
    // Go through and increment the numbers
    for (int i = 0; i < 10; i++) {
        printf("\rIncrementing numbers (%d/%d)... ", i, 10);
        fflush(stdout);
 
        // Get current stream position
        long pos = ftell(f);
 
        // Parse out the number and increment
        int32_t number;
        fscanf(f, "%d", &number);
        number += 1;
 
        // Seek to beginning of number
        fseek(f, pos, SEEK_SET);
    
        // Store number
        fprintf(f, "    %d\n", number);
 
        // Flush between write and read on same file
        fflush(f);
    }
    printf("\rIncrementing numbers (%d/%d)... OK\n", 10, 10);
 
    // Close the file which also flushes any cached writes
    printf("Closing \"/fs/numbers.txt\"... ");
    fflush(stdout);
    err = fclose(f);
    printf("%s\n", (err < 0 ? "Fail :(" : "OK"));
    if (err < 0) {
        error("error: %s (%d)\n", strerror(errno), -errno);
    }
    
    // Display the root directory
    printf("Opening the root directory... ");
    fflush(stdout);
    DIR *d = opendir("/fs/");
    printf("%s\n", (!d ? "Fail :(" : "OK"));
    if (!d) {
        error("error: %s (%d)\n", strerror(errno), -errno);
    }
 
    printf("root directory:\n");
    while (true) {
        struct dirent *e = readdir(d);
        if (!e) {
            break;
        }
 
        printf("    %s\n", e->d_name);
    }
 
    printf("Closing the root directory... ");
    fflush(stdout);
    err = closedir(d);
    printf("%s\n", (err < 0 ? "Fail :(" : "OK"));
    if (err < 0) {
        error("error: %s (%d)\n", strerror(errno), -errno);
    }
 
    // Display the numbers file
    printf("Opening \"/fs/numbers.txt\"... ");
    fflush(stdout);
    f = fopen("/fs/numbers.txt", "r");
    printf("%s\n", (!f ? "Fail :(" : "OK"));
    if (!f) {
        error("error: %s (%d)\n", strerror(errno), -errno);
    }
 
    printf("numbers:\n");
    while (!feof(f)) {
        int c = fgetc(f);
        printf("%c", c);
    }
 
    printf("\rClosing \"/fs/numbers.txt\"... ");
    fflush(stdout);
    err = fclose(f);
    printf("%s\n", (err < 0 ? "Fail :(" : "OK"));
    if (err < 0) {
        error("error: %s (%d)\n", strerror(errno), -errno);
    }
 
    // Tidy up
    printf("Unmounting... ");
    fflush(stdout);
    err = fs.unmount();
    printf("%s\n", (err < 0 ? "Fail :(" : "OK"));
    if (err < 0) {
        error("error: %s (%d)\n", strerror(-err), err);
    }
        
    printf("Mbed OS filesystem example done!\n");
}
``` 
 
## 扇区要求
### LittleFS 要求：

+ 4 blocks root dir。
+ 2 blocks per dir。
+ 1 block per file。

### FATFS 要求:

+ Hard minimum: 256 blocks。
+ 128 blocks for FAT table。
+ 1 block per dir。
+ 1 block per file。