# ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1

**Small, programmable, open source input devices with clickable rotary encoders**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with ANAVI Technology products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1 hardware designs are licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by ANAVI Technology in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. ANAVI Technology shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by ANAVI Technology to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Macro Pad 10. They are considered suitable only for ANAVI Macro Pad 8.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Macro Pad 10 offers a rotary encoder with clickable switch and nine hot-swappable Gateron red mechanical switches with translucent keycaps. The black, gold-plated PCB features yellow backlighting under each key, RGB LED on the front and four WS2812B LEDs for under-lighting. The hot-swappable sockets allow you to change the mechanical switches easily, with no soldering required.

ANAVI Knobs 3 offers three rotary encoders with clickable switches and a RGB LED. The black, gold-plated PCB also features an I²C slot for adding peripherals such as a mini OLED display.

ANAVI Knob 1 is a tiny input device with a single rotary encoder with a clickable switch and a RGB LED. You can turn it left, you can turn it right, and you can click it. It is fully programmable and there is an I²C slot you can use to add peripherals.

## Features

### ANAVI Macro Pad 10

A kit with ANAVI Macro Pad 10 includes:

* **Inputs**: Rotary encoder with clickable switch and nine hot-swappable Cherry MX-style switches
* **Keys**: Nine Gateron red, linear, non-clicky mechanical switches and transparent keycaps with yellow LED backlighting
* **Peripherals:** RGB LED on top, WS2812B addressable LED strip for bottom-lighting
* **MCU**: Raspberry Pi RP2040
* **Connectivity**: USB-C
* **Firmware**: KMK firmware
* **Compatibility**: Windows, macOS, and Linux support
* **Dimensions**: 73.0 x 91.0 mm (2.87 x 3.58 inches)

### ANAVI Knobs 3

A kit with ANAVI Knobs 3 includes:

* **Inputs**: Three rotary encoders with clickable switches
* **Peripherals:** RGB LED, I²C slot
* **MCU**: Raspberry Pi RP2040
* **Connectivity**: USB-C
* **Firmware**: KMK firmware
* **Compatibility**: Windows, macOS, and Linux support
* **Dimensions**: 35.0 x 90.0 mm (1.38 x 3.54 inches)

### ANAVI Knob 1

A kit with ANAVI Knob 1 includes:

* **Inputs**: Rotary encoder with clickable switch
* **Peripherals:** RGB LED, I²C slot
* **MCU**: Raspberry Pi RP2040
* **Connectivity**: USB-C
* **Firmware**: KMK firmware
* **Compatibility**: Windows, macOS, and Linux support
* **Dimensions**: 35.0 x 49.0 mm (1.38 x 1.93 inches)

## Target Market

ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1 can be customized to fit multiple use cases across various industries: video or audio editing, video conferencing software, entertainment broadcasting, product and graphic design, gaming, engineering, programming, etc. It boosts your daily productivity by providing amazing level of control with gorgeous light effects on your fingertips!

## Board Version

Revision 1.1 of ANAVI Macro Pad 10 and revisions 1.0 of ANAVI Knobs 3 and ANAVI Knob 1 were used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1 are shipped in protective bags. The board must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Macro Pad 10, ANAVI Knobs 3 or ANAVI Knob 1 the following items are required:

* Personal Computer with MS Windows, Mac OS or GNU/Linux distribution
* USB to USB-C cable

Getting started with and assembled ANAVI Macro Pad 10, ANAVI Knobs 3 or ANAVI Knob 1 is easy. Just connect it to your GNU/Linux, Windows, or macOS computer, and use a browser to configure and load your keyswitch macro or shortcut settings.

By default ANAVI Macro Pad 10, ANAVI Knobs 3 or ANAVI Knob 1 come with the open source [KMK firmware: Clackety Keyboards Powered by CircuitPython](http://kmkfw.io/). Furthermore they also support the open source the [Quantum Mechanical Keyboard (QMK) firmware](https://docs.qmk.fm/#/), To configure and modify the keyboard layouts you can use QMK Configurator, an online graphical user interface that generates QMK firmware hex files directly in a web browser or use the source code. Press the RESET button on ANAVI Macro Pad 8 to enter flash mode and upload the new firmware.

ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1 are powered by [Seeed Studio XIAO RP2040](https://www.seeedstudio.com/XIAO-RP2040-v1-0-p-5026.html) with Raspberry Pi RP2040 MCU.

## Supported Peripherals

ANAVI Knobs 3 and ANAVI Knob 1 support I2C peripheral devices such as a mini OLED display. Configure the firmware to use the peripherals. Plug the display before turning on the board.

## Assembly

### ANAVI Macro Pad 10, ANAVI Knobs 3, ANAVI Knob 1

Follow the steps below to assemble ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1. Although you can do it with your bare hands, simple tools like a screwdriver, tweezers and a keycap puller might be useful.

* Stickers

*This step is optional.* Each kit includes a set of stickers. Feel free to add them to the translucent keycaps included in ANAVI Macro Pad 10 developer kit. You can do it with your bare hands or eventually with the help of tweezers.

You can place a sticker on the top or on the side of the keycap. If you like retro electronics you may find some similarities in this approach to the famous keyboard of the best selling personal computer of the 20th century Commodore 64.

ANAVI Macro Pad 10 is powered by the popular open source firmware QMK which allows you to create various layouts. You can make a keymap with 2 or more layouts. A sticker on the side of the keycap might be useful as a visual aid to indicate the additional function of the key.

* Peel Off Protective Films from the Acrylic Enclosure

Peel off the protective films from both sides of the two laser cut transparent acrylic parts. The removal of the protective films is quite annoying but once you get rid of them, the acrylic enclosure will be crystal clear and fully transparent.

* Assemble the Acrylic Enclosure

Assemble the acrylic enclosures. In the cardboard box you also will find M3 black plastic screws, nuts and standoffs. Although you can assemble them with your bare hands a screw driver might be handy.

First place 4 of the stand-offs with screws to the bottom acrylic part. After that, place ANAVI Macro Pad 10 on top of them. The printed circuit board has 4 mounting holes for this purpose.

Add the rest of stand-offs on top of the ANAVI Macro Pad 10 to secure the printed circuit board to the bottom part as shown in the video. Place the top acrylic part and fasten it with the 4 M3 nuts. Finally add the silicon protective pads to the screws on the bottom.

* Keycaps

Place all keycaps on the mechanical switches of ANAVI Macro Pad 10. You can easily do this with your bare hands. It takes just a few seconds.

A keycap puller might be useful if you make a mistake and want to pull off a keycap and place it on another location.

* Mini OLED Display

*This step is optional and only for ANAVI Knobs 3 or ANAVI Knob 1* The open source QMK firmware for ANAVI Knobs 3 and ANAVI Knob 1 supports mini OLED display connected over the communication bus I2C.

It is recommended to use yellow-blue 0.96" I2C OLED display. It comes with 4 jumper wires which might be useful for debugging purposes or if you plan to make a custom 3D printed case. However for the default acrylic enclosure the wires are not needed.

Peel off the protected film and place the mini OLED display as shown in the video to ANAVI Macro Pad 10. Pay attention to the labels that indicated the pin connectors of the display. They must match the labels on the keyboard.

* Turn On ANAVI Macro Pad 10

Gently use a USB to USB-C cable to connect ANAVI Macro Pad 10 to a personal computer. Please be careful with the microUSB connector, because a harsh bending of the USB cable may damage the microUSB connector.

Thanks to the QMK firmware, ANAVI Macro Pad 10 will be detected as human interface device and should work out of the box. Furthermore with QMK you have the freedom to fully customize each key.

Please note that a USB to microUSB cable is **not** included in any of the kits. Reuse a cable from an old electronic device or purchase a cable according to your taste. Make sure that the cable supports both power and data transfer over USB.

---

# CHAPTER 3: Software

Out of the box ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1 all come with [the popular open source firmware KMK](https://github.com/KMKfw/kmk_firmware). Alternatively, [QMK firmware](https://qmk.fm/) is also supported. Several different keymaps are available.

## Compile QMK for ANAVI Macro Pad 10

After installing QMK software on your computer, from the command line you can compile QMK firmware with the `default` keymap for ANAVI Macro Pad 10, ANAVI Knobs 3, ANAVI Knob 1 using the following command:

```
qmk compile -kb anavi/macropad10 -km default
```

## Flash QMK on ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1

Follow the steps below to flash the compiled QMK firmware to ANAVI Macro Pad 10, ANAVI Knobs 3 and ANAVI Knob 1:

* Connect ANAVI Macro Pad 10, ANAVI Knobs 3 or ANAVI Knob 1 to your personal computer with USB to USB-C cable and upload the firmware

---

# CHAPTER 4: Hardware Schematics

## Pinout

### ANAVI Macro Pad 10

ANAVI Macro Pad 10 utilizes the following pins on Raspberry Pi RP2040:

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | PD0, PD1                               |
| Mechanical switches | PD4, PF6, PB5, PE6, PF5, PF7, PB4, PC6 |
| LEDs (backlit)      | PD7                                    |
| WS2812B LED strip   | PF4                                    |

### ANAVI Knobs 3

ANAVI Knobs 3 utilizes the following pins on Raspberry Pi RP2040:

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | PD0, PD1                               |
| Rotary Encoders     | PD4, PF6, PB5, PE6, PF5, PF7, PB4, PC6 |

### ANAVI Knob 1

ANAVI Knob 1 utilizes the following pins on Raspberry Pi RP2040:

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | PD0, PD1                               |
| Rotary Encoders     | PD4, PF6, PB5, PE6, PF5, PF7, PB4, PC6 |

## I2C

A mini OLED display that can be connected to ANAVI Knob 1 or ANAVI Knobs 3 communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labeled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Macro Pad 8 includes two 4.7kohm resistors labeled as R13 and R14. If for one reason or another you need to disable the I2C pullup resistors remove R13 and R14.

---

# CHAPTER 5: Frequently Asked Questions (FAQ) and Troubleshooting

* How to fix `The firmware is too large! 28866/28672 (194 bytes over)`?

The easiest way to reduce the size of QMK firmware with your custom new keymap for ANAVI Macro Pad 10 is to cut some of the RGB lighting animations and effects.

For example, in your custom keymap you can create `config.h` in the keymap directory that overwrites the main `config.h` with a reduced number of supported RGB lighting animations and effects:

```
#pragma once

#undef RGBLIGHT_ANIMATIONS
#define RGBLIGHT_EFFECT_BREATHING
#define RGBLIGHT_EFFECT_CHRISTMAS
#define RGBLIGHT_EFFECT_RAINBOW_MOOD
#define RGBLIGHT_EFFECT_SNAKE
```
---

# CHAPTER 6: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 21 October  2022  | Initial manual release      | All             | Leon Anavi      |

## ANAVI Macro Pad 10 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.1     | Stable version                                               |

## ANAVI Knob 1 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable version                                               |

## ANAVI Knobs 3 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable version                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
