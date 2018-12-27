## uVisor
**警告:** uVisor 被 ARM 平台安全体系结构（PSA）中定义的安全分区管理器（SPM）取代。uVisor 自 Mbed OS 5.10 起不推荐使用，并被原生 PSA 兼容的 SPM 实施所取代。

uVisor 是一个独立的软件管理程序，可在 ARMCortex®-M3 和 Cortex®-M4 微控制器上创建独立的安全域。它增强了对恶意软件的恢复能力，并保护秘密甚至在同一应用程序的不同模块之间泄露。有关更多信息，请下载[高级概述](http://www.slideshare.net/FoolsDelight/practical-realtime-operating-system-security-for-the-masses)（[下载 PDF](https://github.com/ARMmbed/uvisor/raw/docs/uVisorSecurity-TechCon2016.pdf)）。

关于中断的注意事项：启用uVisor后，所有NVIC API都会重新路由到相应的uVisor vIRQ API，从而虚拟化中断。 uVisor中断模型具有以下功能：

+ uVisor 拥有中断向量表。
+ 所有 ISR 都重新定位到 SRAM。
+ 如果框中的代码通过 IRQ ACL 向 uQisor 注册了 IRQ，则框中的代码只能更改 IRQ 的状态（启用它，更改其优先级等）。
+ 当该框上下文处于活动状态时，您只能修改属于框的 IRQ。

虽然此行为与原始 NVIC 的行为不同，但它是向后兼容的。启用 uVisor 后，旧版代码（例如设备 HAL）仍然有效。

## 用法
1. 在您的应用程序中包含 uVisor 库。
2. 指定强制访问控制列表中的功能。
3. 添加和配置安全盒，特殊隔间，可独家访问外围设备，存储器和中断。
4. 为您的安全盒创建公共入口点。
5. 在启用 uVisor 的情况下编译应用程序。

有关详细的使用指南和最佳实践，请参阅自述文件

## API
[https://github.com/ARMmbed/uvisor/blob/master/docs/lib/API.md](https://github.com/ARMmbed/uvisor/blob/master/docs/lib/API.md)

## 示例
这是一个简单的示例，展示如何编写具有 IRQ 支持的 uVisor 安全线程应用程序。一个 LED 周期性地从公共盒主线程闪烁。安全盒专门拥有第二个 LED，可以按下用户按钮切换。

[main.cpp](https://github.com/ARMmbed/mbed-os-example-uvisor/blob/master/source/main.cpp)

```
/*
 * Copyright (c) 2013-2016, ARM Limited, All Rights Reserved
 * SPDX-License-Identifier: Apache-2.0
 *
 * Licensed under the Apache License, Version 2.0 (the "License"); you may
 * not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#include "uvisor-lib/uvisor-lib.h"
#include "mbed.h"
#include "main-hw.h"
#include "mem_map.h"
 
#warning "Warning: uVisor is superseded by the Secure Partition Manager (SPM) defined in the ARM Platform Security Architecture (PSA). \
          uVisor is deprecated as of Mbed OS 5.10, and being replaced by a native PSA-compliant implementation of SPM."
 
/* Create ACLs for main box. */
MAIN_ACL(g_main_acl);
 
/* Enable uVisor. */
UVISOR_SET_MODE_ACL(UVISOR_ENABLED, g_main_acl);
UVISOR_SET_PAGE_HEAP(8 * 1024, 5);
 
static void example_halt_error(THaltError reason, const THaltInfo *halt_info);
 
UVISOR_PUBLIC_BOX_DEBUG_DRIVER(example_halt_error);
 
static void example_halt_error(THaltError reason, const THaltInfo *halt_info) {
 
	const MemMap * map = NULL;
	if (halt_info->bfar) {
		map = memory_map_name(halt_info->bfar);
	}
 
	printf("\n");
	printf("  Address:           0x%08X\n", halt_info->bfar);
	printf("  Region/Peripheral: %s\n", (map ? map->name : "[not available]"));
	printf("    Base address:    0x%08X\n", (map ? map->base : halt_info->bfar));
	printf("    End address:     0x%08X\n", (map ? map->end : halt_info->bfar));
 
	return;
}
 
/* Targets with an ARMv7-M MPU needs this space adjustment to prevent a runtime
 * memory overflow error. The code below has been output directly by uVisor. */
#if defined(TARGET_EFM32GG_STK3700) || defined(TARGET_DISCO_F429ZI)
uint8_t __attribute__((section(".keep.uvisor.bss.boxes"), aligned(32))) __boxes_overhead[8064];
#endif
 
int main(void)
{
    DigitalOut led(MAIN_LED);
 
    printf("\r\n***** IRQ blinky uVisor example *****\r\n");
 
    size_t count = 0;
 
    while (1) {
        printf("Main loop count: %d\r\n", count++);
        led = !led;
 
        /* Blink once per second. */
        Thread::wait(500);
    }
 
    return 0;
}
```

[main-hw.h](https://github.com/ARMmbed/mbed-os-example-uvisor/blob/master/source/main-hw.h)                                                                                                                                               
```
/*
 * Copyright (c) 2013-2016, ARM Limited, All Rights Reserved
 * SPDX-License-Identifier: Apache-2.0
 *
 * Licensed under the Apache License, Version 2.0 (the "License"); you may
 * not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#ifndef __UVISOR_HELLOWORLD_MAIN_HW_H__
#define __UVISOR_HELLOWORLD_MAIN_HW_H__
 
#if defined(TARGET_K64F)
 
#define MAIN_LED           LED1
#define SECURE_LED         LED2
#define LED_ON             false
#define LED_OFF            true
#define SECURE_SWITCH      SW2
#define SECURE_SWITCH_PULL PullUp
 
#define MAIN_ACL(acl_list_name) \
    static const UvisorBoxAclItem acl_list_name[] = {     \
        {SIM,    sizeof(*SIM),    UVISOR_TACLDEF_PERIPH}, \
        {OSC,    sizeof(*OSC),    UVISOR_TACLDEF_PERIPH}, \
        {MCG,    sizeof(*MCG),    UVISOR_TACLDEF_PERIPH}, \
        {PORTA,  sizeof(*PORTA),  UVISOR_TACLDEF_PERIPH}, \
        {PORTB,  sizeof(*PORTB),  UVISOR_TACLDEF_PERIPH}, \
        {PORTC,  sizeof(*PORTC),  UVISOR_TACLDEF_PERIPH}, \
        {PORTD,  sizeof(*PORTD),  UVISOR_TACLDEF_PERIPH}, \
        {PORTE,  sizeof(*PORTE),  UVISOR_TACLDEF_PERIPH}, \
        {RTC,    sizeof(*RTC),    UVISOR_TACLDEF_PERIPH}, \
        {LPTMR0, sizeof(*LPTMR0), UVISOR_TACLDEF_PERIPH}, \
        {PIT,    sizeof(*PIT),    UVISOR_TACLDEF_PERIPH}, \
        {SMC,    sizeof(*SMC),    UVISOR_TACLDEF_PERIPH}, \
        {UART0,  sizeof(*UART0),  UVISOR_TACLDEF_PERIPH}, \
        {I2C0,   sizeof(*I2C0),   UVISOR_TACLDEF_PERIPH}, \
        {SPI0,   sizeof(*SPI0),   UVISOR_TACLDEF_PERIPH}, \
    }
 
#elif defined(TARGET_EFM32GG_STK3700)
 
#define MAIN_LED           LED1
#define SECURE_LED         LED2
#define LED_ON             true
#define LED_OFF            false
#define SECURE_SWITCH      SW0
#define SECURE_SWITCH_PULL PullUp
 
#define MAIN_ACL(acl_list_name) \
    static const UvisorBoxAclItem acl_list_name[] = {     \
        {CMU,                 sizeof(*CMU),    UVISOR_TACLDEF_PERIPH}, \
        {MSC,                 sizeof(*MSC),    UVISOR_TACLDEF_PERIPH}, \
        {GPIO,                sizeof(*GPIO),   UVISOR_TACLDEF_PERIPH}, \
        {TIMER0,              sizeof(*TIMER0), UVISOR_TACLDEF_PERIPH}, \
        {UART0,               sizeof(*UART0),  UVISOR_TACLDEF_PERIPH}, \
        {(void *) 0x0FE08000, 0x1000,          UVISOR_TACLDEF_PERIPH}, \
        {(void *) 0x42000000, 0x2000000,       UVISOR_TACLDEF_PERIPH}, \
    }
 
#elif defined(TARGET_DISCO_F429ZI)
 
#define MAIN_LED           LED1
#define SECURE_LED         LED2
#define LED_ON             true
#define LED_OFF            false
#define SECURE_SWITCH      USER_BUTTON
#define SECURE_SWITCH_PULL PullDown
 
#define MAIN_ACL(acl_list_name) \
    static const UvisorBoxAclItem acl_list_name[] = {     \
        {GPIOA,               sizeof(*GPIOA),  UVISOR_TACLDEF_PERIPH}, \
        {GPIOB,               sizeof(*GPIOB),  UVISOR_TACLDEF_PERIPH}, \
        {GPIOC,               sizeof(*GPIOC),  UVISOR_TACLDEF_PERIPH}, \
        {GPIOD,               sizeof(*GPIOD),  UVISOR_TACLDEF_PERIPH}, \
        {GPIOE,               sizeof(*GPIOE),  UVISOR_TACLDEF_PERIPH}, \
        {RTC,                 sizeof(*RTC),    UVISOR_TACLDEF_PERIPH}, \
        {TIM5,                sizeof(*TIM5),   UVISOR_TACLDEF_PERIPH}, \
        {USART1,              sizeof(*USART1), UVISOR_TACLDEF_PERIPH}, \
        {I2C1,                sizeof(*I2C1),   UVISOR_TACLDEF_PERIPH}, \
        {SPI1,                sizeof(*SPI1),   UVISOR_TACLDEF_PERIPH}, \
        {RCC,                 sizeof(*RCC),    UVISOR_TACLDEF_PERIPH}, \
        {FLASH,               sizeof(*FLASH),  UVISOR_TACLDEF_PERIPH}, \
        {PWR,                 sizeof(*PWR),    UVISOR_TACLDEF_PERIPH}, \
        {EXTI,                sizeof(*EXTI),   UVISOR_TACLDEF_PERIPH}, \
        {GPIOG,               sizeof(*GPIOG),  UVISOR_TACLDEF_PERIPH}, \
        {SYSCFG,              sizeof(*SYSCFG), UVISOR_TACLDEF_PERIPH}, \
        {(void *) 0x42000000, 0x01000000,      UVISOR_TACLDEF_PERIPH}, \
    }
 
#else /* Target-specific settings */
 
#error "Unsupported target. Checkout the README.md file for the list of supported targets for this app."
 
#endif /* Target-specific settings */
 
#endif /* __UVISOR_HELLOWORLD_MAIN_HW_H__ */
```

[led.cpp](https://github.com/ARMmbed/mbed-os-example-uvisor/blob/master/source/led.cpp)                                                                                                                                                
```
/*
 * Copyright (c) 2013-2016, ARM Limited, All Rights Reserved
 * SPDX-License-Identifier: Apache-2.0
 *
 * Licensed under the Apache License, Version 2.0 (the "License"); you may
 * not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#include "uvisor-lib/uvisor-lib.h"
#include "mbed.h"
#include "main-hw.h"
 
typedef struct {
    InterruptIn * sw;
    DigitalOut * led;
} my_box_context;
 
static const UvisorBoxAclItem acl[] = {
};
 
static void my_box_main(const void *);
 
/* Box configuration
 * We need 1kB of stack both in the main and interrupt threads as both of them
 * use printf. */
UVISOR_BOX_NAMESPACE(NULL);
UVISOR_BOX_HEAPSIZE(3072);
UVISOR_BOX_MAIN(my_box_main, osPriorityNormal, 1024);
UVISOR_BOX_CONFIG(my_box, acl, 1024, my_box_context);
 
#define uvisor_ctx ((my_box_context *) __uvisor_ctx)
 
static void my_box_switch_irq(void)
{
    /* Flip LED state. */
    *uvisor_ctx->led = !*uvisor_ctx->led;
 
    /* Print LED state on serial port. */
    printf("\r\nPressed switch, printing from interrupt - LED now %s.\r\n\r\n",
           (int) (*uvisor_ctx->led) == LED_ON ? "on" : "off");
}
 
static void my_box_main(const void *)
{
    /* Allocate a box-specific LED. */
    if (!(uvisor_ctx->led = new DigitalOut(SECURE_LED))) {
        printf("ERROR: failed to allocate memories for LED\r\n");
    } else {
        /* Turn LED off by default */
        *uvisor_ctx->led = LED_OFF;
 
        /* Allocate a box-specific switch handler. */
        if (!(uvisor_ctx->sw = new InterruptIn(SECURE_SWITCH))) {
            printf("ERROR: failed to allocate memories for switch\r\n");
        } else {
            /* Register handler for switch. */
            uvisor_ctx->sw->mode(SECURE_SWITCH_PULL);
            uvisor_ctx->sw->fall(my_box_switch_irq);
 
            /* No problem to return here as everything is initialized. */
            return;
        }
        delete uvisor_ctx->led;
    }
}
```