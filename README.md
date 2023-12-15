# KIT_XMC72_EVK_MUR_43439M2 BSP

## Overview

The KIT_XMC72_EVK_MUR_43439M2, and a 272-pin evaluation board, is based on the XMC7000 family of devices. XMC7000 MCU is designed for industrial applications. The evaluation board carries a XMC7000D microcontroller, a M.2 interface connector for interfacing radio modules based on AIROC™ Wi-Fi and Bluetooth® combos, SMIF dual header compatible with Digilent Pmod for interfacing HYPERBUS™ memories (currently not supported), and headers compatible with Arduino for interfacing Arduino shields. In addition, the board features an on-board programmer/debugger (KitProg3), a 512-Mbit QSPI NOR flash, CAN FD transceiver, Gigabit Ethernet PHY transceiver with RJ45 connector interface, a micro-B connector for USB device interface, three user LEDs, one potentiometer, and two push buttons. The board supports operating voltages from 3.3 V to 5.0 V for XMC7000D device.

**Note:**
KIT_XMC72_EVK_MUR_43439M2 is the board support package for the XMC7200 evaluation kit in combination with the 1YN radio module and supports XMC7000 MCU examples and Wi-Fi connectivity examples.

**The 1YN radio module supports Wi-Fi/Bluetooth® connectivity. However, currently KIT_XMC72_EVK_MUR_43439M2 doesn't support the Bluetooth® functionality and the WLAN functionality in low power mode. For more details, refer to the**
[kit release notes](https://www.infineon.com/dgdl/Infineon-KIT_XMC72_EVK-XMC7200-evaluation-kit-release-notes-UserManual-v04_00-EN.pdf?fileId=8ac78c8c8412f8d301842e69fcde7b8a)



To use code from the BSP, simply include a reference to `cybsp.h`.

## Features

### Kit Features:

* XMC7200D-E272K8384 8MB Flash 272-pin BGA device
* Programming interface (Arm® Standard JTAG, Cortex® Debug + ETM with Arm® ETM Mictor)
* Reset control with manual reset switch and voltage supervision
* Gigabit Ethernet interface
* CAN FD interface
* M.2 interface connector to connect radio modules based on AIROC™ Wi-Fi & Bluetooth® combos 
* 512-Mbit external Quad SPI NOR Flash that provides a fast, expandable memory for data and code
* KitProg3 on-board SWD programmer/debugger, USB-UART and USB-I2C bridge functionality
* A micro-B connector for USB device interface
* Selectable input supply voltages of 3.3 V and 5.0 V for the XMC7000D device
* Three user LEDs, two user buttons, and a reset button for the XMC7000D device
* A potentiometer which can be used to simulate analog sensor output
* A mode button and a mode LED for KitProg3

### Kit Contents:

* XMC7200 evaluation board
* Embedded Artists 1YN Wi-Fi/Bluetooth® M.2 radio module
* USB Type-A to Micro-B cable
* 12V/3A DC power adapter with additional blades
* Six jumper wires
* Quick start guide

## BSP Configuration

The BSP has a few hooks that allow its behavior to be configured. Some of these items are enabled by default while others must be explicitly enabled. Items enabled by default are specified in the KIT_XMC72_EVK_MUR_43439M2.mk file. The items that are enabled can be changed by creating a custom BSP or by editing the application makefile.

Components:
* Device specific category reference (e.g.: CAT1) - This component, enabled by default, pulls in any device specific code for this board.

Defines:
* CYBSP_WIFI_CAPABLE - This define, disabled by default, causes the BSP to initialize the interface to an onboard wireless chip if it has one.
* CY_USING_HAL - This define, enabled by default, specifies that the HAL is intended to be used by the application. This will cause the BSP to include the applicable header file and to initialize the system level drivers.
* CYBSP_CUSTOM_SYSCLK_PM_CALLBACK - This define, disabled by default, causes the BSP to skip registering its default SysClk Power Management callback, if any, and instead to invoke the application-defined function `cybsp_register_custom_sysclk_pm_callback` to register an application-specific callback.

### Clock Configuration

| Clock    | Source    | Output Frequency |
|----------|-----------|------------------|
| FLL      | IMO       | 50.0 MHz         |
| PLL      | IMO       | 100.0 MHz        |
| CLK_HF0  | CLK_PATH0 | 50 MHz           |
| CLK_HF1  | CLK_PATH1 | 340 MHz          |
| CLK_HF2  | CLK_PATH2 | 196 MHz          |
| CLK_HF3  | CLK_PATH3 | 144 MHz          |
| CLK_HF4  | CLK_PATH4 | 100 MHz          |
| CLK_HF5  | CLK_PATH5 | 8 MHz            |
| CLK_HF6  | CLK_PATH5 | 8 MHz            |
| CLK_HF7  | CLK_PATH5 | 8 MHz            |

### Power Configuration

* System Idle Power Mode: Deep Sleep
* VDDA Voltage: 3300 mV
* VDDD Voltage: 3300 mV

See the [BSP Setttings][settings] for additional board specific configuration settings.

## API Reference Manual

The KIT_XMC72_EVK_MUR_43439M2 Board Support Package provides a set of APIs to configure, initialize and use the board resources.

See the [BSP API Reference Manual][api] for the complete list of the provided interfaces.

## More information
* [KIT_XMC72_EVK_MUR_43439M2 BSP API Reference Manual][api]
* [KIT_XMC72_EVK_MUR_43439M2 Documentation](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc72_evk/)
* [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)
* [Infineon GitHub](https://github.com/infineon)
* [ModusToolbox™](https://www.cypress.com/products/modustoolbox-software-environment)

[api]: https://infineon.github.io/TARGET_KIT_XMC72_EVK_MUR_43439M2/html/modules.html
[settings]: https://infineon.github.io/TARGET_KIT_XMC72_EVK_MUR_43439M2/html/md_bsp_settings.html

---
© Cypress Semiconductor Corporation (an Infineon company) or an affiliate of Cypress Semiconductor Corporation, 2019-2022.