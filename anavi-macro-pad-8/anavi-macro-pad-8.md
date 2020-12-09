# ANAVI Macro Pad 8

**Convert Your Raspberry Pi to Powerful Remote Control**

---

# DISCLAIMER

Raspberry Pi and the Raspberry Pi logo are registered trademarks of the Raspberry Pi Foundation. ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of
this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Macro Pad 8 hardware design is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Macro Pad 8. They are considered suitable only for ANAVI Macro Pad 8.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Macro Pad 8 is an open source, custom-programmable, mini 8-key keyboard/keypad. Each key can be reprogrammed to activate a macro or even a dedicated shortcut - all without any coding experience! Powered by the advanced, but easy-to-use Quantum Mechanical Keyboard (QMK) open source firmware.

ANAVI Macro Pad 8 is an entirely open source project that combines open source hardware with free and open source software. It has been certified by [Open Source Hardware Association under UID BG000072](https://certification.oshwa.org/bg000072.html).

Only free and open source software tools like KiCad, OpenSCAD, and Inkscape were used to design ANAVI Macro Pad 8. [Quantum Mechanical Keyboard (QMK)](https://qmk.fm/)  is the default open source firmware. Arduino sketches will be available as examples for people interested in explore embedded development with a mini keyboard. Source code and schematics are [available on GitHub](https://github.com/anavitechnology/). A comprehensive user's manual will be provided.

## Features

ANAVI Macro Pad 8 Raspberry Pi HAT includes:

* **Keyswitches:** Eight Cherry MX-style pads
   * Developer Kit includes eight Gateron red, linear, non-clicky mechanical switches and transparent keycaps with red LED backlighting
* **Peripherals:**
   * S2812B addressable LED strip for bottom-lighting
   * Optional 0.96" mini OLED display
* **MCU:** [Microchip ATmega32U4](https://www.mouser.bg/ProductDetail/Microchip-Technology-Atmel/ATMEGA32U4-AU?qs=SSucg2PyLi7mKWjHIsNJ3w==)
* **Connectivity:** Micro USB
* **Firmware:** Quantum Mechanical Keyboard (QMK) open source firmware and Arduino sketches
* **Compatibility:** Windows, macOS, and Linux support
* **Dimensions:** 135 x 47 mm (5.32 x 1.86 inches)

## Target Market

ANAVI Macro Pad 8 can be customized to fit multiple use cases across various industries: video or audio editing, video conferencing software, entertainment broadcasting, product and graphic design, gaming, engineering, programming, etc. It boosts your daily productivity by providing amazing level of control with gorgeous light effects on your fingertips!

## Board Version

Revision 1.1 of ANAVI Macro Pad 8 was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Macro Pad 8 is shipped in a protective antistatic bag. The board must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Macro Pad 8 the following items are required:

* Computer
* USB to microUSB cable

Getting started with and assembled ANAVI Macro Pad 8 is easy. Just connect it to your Linux, Windows, or macOS computer, and use a browser to configure and load your kewswitch macro or shortcut settings.

ANAVI Macro Pad 8 relies on the Quantum Mechanical Keyboard (QMK) firmware, To configure and modify the keyboard layouts you can use QMK Configurator, an online graphical user interface that generates QMK firmware hex files directly in a web browser or use the source code. Press the RESET button on ANAVI Macro Pad 8 to enter flash mode and upload the new firmware.

Furthermore, ANAVI Macro Pad 8 is powered by a Microchip ATmega32U4 microcontroller, so it is possible to use as an Arduino Leonardo-compatible development board and upload Arduino sketches through Arduino IDE or PlatformIO.

## Supported Peripherals

ANAVI Macro Pad 8 supports I2C mini OLED display. Plug the display before turing on the board.

## Assembly

## Powering ANAVI Macro Pad 8


---

# CHAPTER 3: Software

---

# CHAPTER 4: Hardware Schematics

## Pinout

ANAVI Macro Pad 8 utilize the following pins on ATmega32U4:

| Component    | Pins                            |
| ------------ |:------------------------------- |
| I2C          |                                 |

## I2C

The mini OLED display that can be connected to ANAVI Macro Pad 8 communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Macro Pad 8 includes two 4.7kohm resistors labelled as R13 and R14. If for one reason or another you need to disable the I2C pullup resistors remove R13 and R14.

---

# CHAPTER 5: Frequently Asked Questions (FAQ)

---

# CHAPTER 6: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 09 December 2020  | Initial manual release      | All             | Leon Anavi      |

## ANAVI Macro Pad 8 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.1     | Stable version                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
