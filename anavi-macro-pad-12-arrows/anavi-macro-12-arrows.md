# ANAVI Macro Pad 12 and ANAVI Arrows

**Compact, open-source, hot-swappable mechanical keyboards featuring back-lighting, under-lighting and an OLED display**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with ANAVI Technology products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Macro Pad 12 and ANAVI Arrows hardware designs are licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by ANAVI Technology in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. ANAVI Technology shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by ANAVI Technology to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Macro Pad 12 and ANAVI Arrows. They are considered suitable only for ANAVI Macro Pad 12 and ANAVI Arrows.

---

# CHAPTER 1: Overview

## Introduction

Unleash your typing potential with our new small, fully programmable, open source mechanical keyboards with hot-swappable sockets: **ANAVI Macro Pad 12** and **ANAVI Arrows**. Both are powered by the Raspberry Pi RP2040 microcontroller at the heart of the [Seeed XIAO RP2040](https://www.seeedstudio.com/XIAO-RP2040-v1-0-p-5026.html), which provides support for USB Type-C. Each kit includes a mini yellow-blue OLED display for the dedicated I2C connector. Out of the box the keyboards are powered by the open source KMK firmware, written in CircuitPython.

ANAVI Macro Pad 12 keyboard offers twelve fully programmable, hot-swappable, Gateron red mechanical switches with translucent keycaps. The black, gold-plated PCB features yellow back-lighting under each key, RGB LED on front and six WS2812B LEDs for under lighting effects. The hot-swappable sockets allow you to change the mechanical switches easily, with no soldering required. The device has a I²C slot for adding peripherals, such as a mini OLED display, which is included in the kit.

ANAVI Arrows offers single rotary encoder with a clickable switch and a RGB LED and four Gateron red, linear, non-clicky mechanical switches with transparent keycaps and yellow LED back-lighting. You can easily turn the rotary encoder left or right, and you also can click it! It is fully programmable! ANAVI Arrows is black, gold-plated PCB features with yellow back-lighting under each key and with four WS2812B LEDs for under lighting effect. It also has a I²C slot for adding peripherals, such as mini OLED display, which is included in the kit.

## Features

### ANAVI Macro Pad 12

A kit with ANAVI Macro Pad 12 includes:

* **Keys**: Twelve Gateron red, linear, non-clicky hot-swap mechanical switches and transparent keycaps with yellow LED backlighting
* **Peripherals:** RGB LED on top, six WS2812B addressable LED strip for bottom-lighting, I²C slot for mini OLED display or other peripherals
* **MCU**: Raspberry Pi RP2040
* **Connectivity**: USB-C
* **Firmware**: KMK firmware
* **Compatibility**: Windows, macOS, and Linux support
* **Dimensions**: 73.0 x 116.7 mm (2.87 x 4.60 inches)

### ANAVI Arrows

A kit with ANAVI Arrows includes:

**Keys**: Four Gateron red, linear, non-clicky hot-swap mechanical switches and transparent keycaps with yellow LED back-lighting
* **Inputs**: One rotary encoder with clickable switch
* **Peripherals:** RGB LED on front and four addressable WS2812B LED strip for bottom-lighting, I²C slot for mini OLED display or other peripherals
* **MCU**: Raspberry Pi RP2040
* **Connectivity**: USB-C
* **Firmware**: KMK firmware
* **Compatibility**: Windows, macOS, and Linux support
* **Dimensions**: 80.0 x 63.2 mm (3.15 x 2.49 inches)

## Mini OLED Display

Each kit of ANAVI Macro Pad 12 and ANAVI Arrows contains a mini yellow-blue I2C OLED display. I2C, short for Inter-Integrated Circuit, is a widely used serial communication protocol. There is a dedicated connector on the printed circuit board of each keyboard to plug the mini OLED display. Eventually, it is technically possible to add other I2C devices, for example a gesture sensor, to the same connector. The open source firmware KMK has support for OLED display.

## Target Market

ANAVI Macro Pad 12 and ANAVI Arrows can be customized to fit multiple use cases across various industries: video or audio editing, video conferencing software, entertainment broadcasting, product and graphic design, gaming, engineering, programming, etc. It boosts your daily productivity by providing amazing level of control with gorgeous light effects on your fingertips!

## Board Version

Revision 1.0 of ANAVI Macro Pad 12 and revisions 1.0 of ANAVI Arrows were used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Macro Pad 12 and ANAVI Arrows are shipped in protective bags. The board must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Macro Pad 12 or ANAVI Arrows the following items are required:

* Personal Computer with MS Windows, Mac OS or GNU/Linux distribution
* USB to USB-C cable

Getting started with and assembled ANAVI Macro Pad 12 or ANAVI Arrows is easy. Just connect it to your GNU/Linux, Windows, or macOS computer, and use a browser to configure and load your keyswitch macro or shortcut settings.

By default ANAVI Macro Pad 12 and ANAVI Arrows come with the open source [KMK firmware: Clackety Keyboards Powered by CircuitPython](http://kmkfw.io/). Furthermore they also support the open source the [Quantum Mechanical Keyboard (QMK) firmware](https://docs.qmk.fm/#/), To configure and modify the keyboard layouts you can use QMK Configurator, an online graphical user interface that generates QMK firmware hex files directly in a web browser or use the source code. Press the RESET button on ANAVI Macro Pad 12 or ANAVI Arrows to enter flash mode and upload the new firmware.

ANAVI Macro Pad 12 and ANAVI Arrows are powered by [Seeed Studio XIAO RP2040](https://www.seeedstudio.com/XIAO-RP2040-v1-0-p-5026.html) with Raspberry Pi RP2040 MCU.

## Supported Peripherals

Each kit of ANAVI Macro Pad 12 and ANAVI Arrows contains a mini yellow-blue I2C OLED display. I2C, short for Inter-Integrated Circuit, is a widely used serial communication protocol. There is a dedicated connector on the printed circuit board of each keyboard to plug the mini OLED display. Eventually, it is technically possible to add other I2C devices, for example a gesture sensor, to the same connector. The open source firmware KMK has support for OLED display.

## Assembly

### ANAVI Macro Pad 12 and ANAVI Arrows

Follow the steps below to assemble ANAVI Macro Pad 12 and ANAVI Arrows. Although you can do it with your bare hands, simple tools like a screwdriver, tweezers and a keycap puller might be useful.

* Stickers

*This step is optional.* Each kit includes a set of stickers, which can be add to the translucent keycaps. You can do it with your bare hands or eventually with the help of tweezers.

You can place a sticker on the top or on the side of the keycap. If you like retro electronics you may find some similarities in this approach to the famous keyboard of the best selling personal computer of the 20th century Commodore 64.

ANAVI Macro Pad 12 and ANAVI Arrows are powered by the popular open source firmware QMK which allows you to create various layouts. You can make a keymap with 2 or more layouts. A sticker on the side of the keycap might be useful as a visual aid to indicate the additional function of the key.

* Peel Off Protective Films from the Acrylic Enclosure

Peel off the protective films from both sides of the three laser cut transparent acrylic parts. The removal of the protective films is quite annoying but once you get rid of them, the acrylic enclosure will be crystal clear and fully transparent.

* Assemble the Acrylic Enclosure

Assemble the acrylic enclosures. In the cardboard box you also will find four M3 screws and eight M3 nuts. Although you can assemble them with your bare hands a screw driver might be handy.

First place 4 screws up through the solid acrylic bottom plate. Fasten the screws to the bottom plate with 4 M3 nuts.

Next, place the ANAVI Macro Pad 12 or ANAVI Arrows PCB on top of of the bottom plate with the XIAO-RP2040 and knob facing away from the bottom plate passing the screws through the 4 mounting holes in the PCB.

Add the U-shaped acrylic spacer plate on top of the PCB with the cutout leaving room for the USB port on the XIAO-RP2040.

Place the top acrylic part and gently fasten it with the 4 M3 nuts.

Finally add the foam protective pads to the screws on the bottom.

* Keycaps

Place all keycaps on the mechanical switches of ANAVI Macro Pad 12 or ANAVI Arrows. You can easily do this with your bare hands. It takes just a few seconds.

A keycap puller might be useful if you make a mistake and want to pull off a keycap and place it on another location.

* Mini OLED Display

The open source QMK firmware for ANAVI Macro Pad 12 and ANAVI Arrows supports mini OLED display connected over the communication bus I2C.

It is recommended to use yellow-blue 0.96" I2C OLED display. It comes with 4 jumper wires which might be useful for debugging purposes or if you plan to make a custom 3D printed case. However for the default acrylic enclosure the wires are not needed.

Peel off the protected film and place the mini OLED display as shown in  ANAVI Macro Pad 12 and ANAVI Arrows videos. Pay attention to the labels that indicated the pin connectors of the display. They must match the labels on the keyboard.

* Turn On ANAVI Macro Pad 12

Gently use a USB to USB-C cable to connect ANAVI Macro Pad 12 or ANAVI Arrows to a personal computer. Please be careful with the USB-C connector, because a harsh bending of the USB cable may damage the USB-C connector.

Thanks to the KMK firmware, ANAVI Macro Pad 12 or ANAVI Arrows will be detected as human interface device and should work out of the box. Furthermore with KMK you have the freedom to fully customize each key.

Please note that a USB to USB-C cable is **not** included in any of the kits. Re-use a cable from an old electronic device or purchase a cable according to your taste. Make sure that the cable supports both power and data transfer over USB.

---

# CHAPTER 3: Software

Out of the box ANAVI Macro Pad 12 and ANAVI Arrows come with the open source firmware KMK written in CircuitPython.

## KMK firmware

[![Watch the video](https://img.youtube.com/vi/clngc4eI7y8/maxresdefault.jpg)](https://youtu.be/clngc4eI7y8)

[KMK](http://kmkfw.io/) is a free and open source firmware for mechanical keyboards written in CircuitPython.

[CircuitPython](https://circuitpython.org/) is an open-source programming language that runs on microcontrollers used in various embedded applications, including mechanical keyboards like ANAVI Macro Pad 12 and ANAVI Arrows. It is derived from the Python programming language and tailored to the needs of constrained embedded devices with a microcontroller. One of the key advantages of CircuitPython is its simplicity and ease of use, especially for beginners who lack extensive programming experience.

The KMK source code can be accessed on [GitHub](https://github.com/KMKfw/kmk_firmware), where it is released under the GPLv3 license. The development of KMK started in 2018. KMK source code employs the Python code formatter known as Black and utilizes single quotes in its coding style.

KMK is designed to be compatible with microcontrollers that have a minimum of 256KB of flash storage, support HID over USB and/or Bluetooth, and can run CircuitPython version 7.0 or newer. With its impressive hardware capabilities, the Raspberry Pi RP2040 microcontroller is a perfect fit for CircuitPython and KMK. ANAVI Macro Pad 12 and ANAVI Arrows are designed around [Seeed Studio’s XIAO module with RP2040](https://www.seeedstudio.com/XIAO-RP2040-v1-0-p-5026.html).

KMK provides numerous amazing key features, including:

* **Key Mapping:** Customize key assignments to suit individual preferences
* **Macros:** Create and assign macros for automating tasks or executing commands
* **Layers:** Define multiple virtual layers for accessing different functions or modes
* **LED Control:** Customize backlighting and LED behavior
* **Rotary Encoder:** Rotary encoders for various functions like volume control or scrolling.
* **Mini OLED Display:** Compatibility with mini OLED displays, allowing users to display custom information or visuals on their keyboards.

## QMK firmware

*This step is optional and is provided in case you want to use QMK firmware.*

Out of the box ANAVI Macro Pad 12 and ANAVI Arrows all come with [the popular open source firmware KMK](https://github.com/KMKfw/kmk_firmware). Alternatively, [QMK firmware](https://qmk.fm/) is also supported. Several different keymaps are available.

## Compile QMK for ANAVI Macro Pad 12

After installing QMK software on your computer, from the command line you can compile QMK firmware with the `default` keymap for ANAVI Macro Pad 12 or ANAVI Arrows using the following command:

```
qmk compile -kb anavi/macropad12 -km default
```

## Flash QMK on ANAVI Macro Pad 12

Follow the steps below to flash the compiled QMK firmware to ANAVI Macro Pad 12:

* Connect ANAVI Macro Pad 12 or ANAVI Arrows to your personal computer with USB to USB-C cable and upload the firmware

---

# CHAPTER 4: Hardware Schematics

## Pinout

### ANAVI Macro Pad 12

ANAVI Macro Pad 12 utilizes the following pins on [Seeed Studio XIAO RP2040](https://wiki.seeedstudio.com/XIAO-RP2040/):

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | D4 (SDA), D5 (SCL)                     |
| Mechanical switches | D1, D2, D3, D6, D7, D8, D9             |
| LEDs (backlit)      | D0                                     |
| WS2812B LED strip   | D10                                    |


### ANAVI Arrows

ANAVI Arrows utilizes the following pins on [Seeed Studio XIAO RP2040](https://wiki.seeedstudio.com/XIAO-RP2040/):

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | D4 (SDA), D5 (SCL)                     |
| Mechanical switches | D1, D2, D3, D6                         |
| Rotary encoder      | D7, D8, D9                             |
| LEDs (backlit)      | D0                                     |
| WS2812B LED strip   | D10                                    |

## I2C

A mini OLED display that can be connected to ANAVI Macro Pad 12 or ANAVI Arrows communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labeled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Macro Pad 8 includes two 4.7kohm resistors labeled as R13 and R14. If for one reason or another you need to disable the I2C pullup resistors remove R13 and R14.

---

# CHAPTER 5: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author             |
| ----------------- |:---------------------------:| :---------------| :------------------|
| 05 June 2023      | Initial manual release      | All             | Desislava Angelova |
| 03 November 2023  | KMK, QMK and schematics     | All             | Leon Anavi |

## ANAVI Macro Pad 12 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0    | Stable version                                               |

## ANAVI Arrows Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable version                                               |


## See Also

For more information please visit [anavi.technology](https://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
