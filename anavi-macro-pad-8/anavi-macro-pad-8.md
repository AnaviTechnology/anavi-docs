# ANAVI Macro Pad 8

**Convert Your Raspberry Pi to Powerful Remote Control**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with ANAVI Technology products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Macro Pad 8 hardware design is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by ANAVI Technology in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. ANAVI Technology shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by ANAVI Technology to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

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

### ANAVI Macro Pad 8 Maker Kit

**NOTE:** The **maker** kit is for advanced users and requires soldering skills. If you have a developer kit chip this chapter.

The maker kit provides the printed circuit board and an addressable LED strip. There are also some nice stickers. Other accessories have to be purchased separately. You can use any mechanical switches compatible with Cherry MX plate footprint and 3mm LEDs.

**NOTE:** With the maker kit you can also perform [a hot-swap upgrade of ANAVI Macro 8](https://www.youtube.com/watch?v=lnFSAm9R4j0). It requires a very specific procedure explained in [this video](https://www.youtube.com/watch?v=lnFSAm9R4j0). If you have in mind a hot-swap upgrade do not solder anything and have a look at [the video](https://www.youtube.com/watch?v=lnFSAm9R4j0).

For soldering and a standard assembly of the **maker kit** several tools are required: a soldering iron, a screwdriver, scissors, tweezers and a keycap puller might be also useful. It is also a good idea to stay safe and get a smoke absorber while soldering, for example [ANAVI Fume Extractor](https://anavi.technology/#products).

Please have [a look at the video](https://www.youtube.com/watch?v=AlH5sLEsoNc) and follow the steps below to assemble ANAVI Macro Pad 8 **Maker** Kit.

* Solder mechanical switches to the printed circuit board

Any mechanical switches compatible with Cherry MX plate footprint are suitable for ANAVI Macro Pad 8. The developer kit comes with Gateron red mechanical switches. The maker kits allows you to choose another brand, type and color.

Choosing the most appropriate switch for your needs is a matter of personal preference. There are many different brands and colors. For example, the blue mechanical switches are more noisy which could be sometimes fun but also annoying during daily work. The red switches are fast and not very noisy therefore they are often proffered by gamers.

There are two pins on each mechanical switch that must be soldered to the printed circuit board. That makes 16 pins in total for the 8 keys on ANAVI Macro Pad 8. The position of the each of the pins is very specific and you can easily recognize it. One of the pins for the signal coming from the Microchip ATmega32U4 microcontroller, the other pin is for ground.

* Solder 3mm LED

This step is actually optional depending on the the type of the mechanical switch. Some mechanical switches may not have a hole in the plastic enclosure for a 3mm LED. For example, the Gateron red switches have a dedicated place specially for 3mm LEDs.

Each 3mm LED for through-hole soldering has 2 legs. The longer leg is the positive terminal, also known as anode. The shorter leg is negative and also known as cathode.

The shorter leg that indicates the negative terminal must go into the square hole of the PCB. ANAVI Macro Pad 8 has 8 mechanical switches therefore 8 LEDs are required. If you want you can use different color of the LEDs. You can even mix colors.

* Solder WS2812B addressable LED strip to the back of the printed circuit board.

Using scissors cut a little bit from both ends of the LED strip to make sure it will stretched when placed on the board. However it is tricky, be careful and make sure enough from the pads are available to make a good contact after soldering them.

It is very important to properly set the direction of the WS2812B LED strip. On the LED strip you will notice small arrows indicating the direction. They should point from the microUSB connector towards the other end of the PCB as shown [in the video](https://www.youtube.com/watch?v=AlH5sLEsoNc).

**NOTE:** It is very important to soldering the addressable WS2812B LED strip in the correct direction as shown [in the video](https://www.youtube.com/watch?v=AlH5sLEsoNc). A mistake can severely damage the keyboard.

Once you are ready with these 3 steps your ANAVI Macro Pad 8 should looks just like a developer kit having all accessories soldered. Therefore the next steps are the same as for both the developer and the maker kit.

### ANAVI Macro Pad 8 Developer Kit

Please have [a look at the video](https://www.youtube.com/watch?v=AlH5sLEsoNc) and follow the steps below to assemble ANAVI Macro Pad 8 **Developer** Kit. Although you can do it with your bare hands, simple tools like a screwdriver, tweezers and a keycap puller might be useful.

* Stickers

*This step is optional.* Each kit includes a set of stickers. Feel free to add them to the translucent keycaps included in ANAVI Macro Pad 8 developer kit. You can do it with your bare hand or eventually with the help of tweezers.

You can place a sticker on the top or on the side of the keycap. If you like retro electronics you may find some similarities in this approach to the famous keyboard of the best selling personal computer of the 20th century Commodore 64.

ANAVI Macro Pad 8 is powered by the popular open source firmware QMK which allows you to create various layouts. You can make a keymap with 2 or more layouts. A sticker on the side of the keycap might be useful as a visual aid to indicate the additional function of the key.

* Keycaps

Place all keycaps on the 8 mechanical switches of ANAVI Macro Pad 8. You can easily do this with your bare hands. It takes just a few seconds.

As you can see [in the video](https://www.youtube.com/watch?v=AlH5sLEsoNc), a keycap puller might be useful if you make a mistake and want to pull off a keycap and place it on another location.

* Peel Off Protective Films from the Acrylic Enclosure

Peel off the protective films from both sides of the two laser cut transparent acrylic parts. The removal of the protective films is quite annoying but once you get rid of them, the acrylic enclosure will be crystal clear and fully transparent.

* Assemble the Acrylic Enclosure

Assemble the acrylic enclosures. In the cardboard box you also will find M3 black plastic screws, nuts and standoffs. Although you can assemble them with your bare hands a screw driver might be handy.

First place 4 of the stand-offs with screws to the bottom acrylic part. After that, place ANAVI Macro Pad 8 on top of them. The printed circuit board has 4 mounting holes for this purpose.

Add the rest of stand-offs on top of the ANAVI Macro Pad 8 to secure the printed circuit board to the bottom part as shown in the video. Place the top acrylic part and fasten it with the 4 M3 nuts. Finally add the silicon protective pads to the screws on the bottom.

* Mini OLED Display

*This step is optional.* The default open source QMK firmware for ANAVI Macro Pad 8 support mini OLED display connected over the communication bus I2C.

By default. the mini display is in yellow-blue 0.96" I2C OLED. It comes with 4 jumper wires which might be useful for debugging purposes or if you plan to make a custom 3D printed case. However for the default acrylic enclosure the wires are not needed.

Peel off the protected film and place the mini OLED display as shown in the video to ANAVI Macro Pad 8. Pay attention to the labels that indicated the pin connectors of the display. They must match the labels on the keyboard.

* Turn On ANAVI Macro Pad 8

Gently use a USB to microUSB cable to connect ANAVI Macro Pad 8 to a personal computer. Please be careful with the microUSB connector, because a harsh bending of the USB cable may damage the microUSB connector.

Thanks to the QMK firmware, ANAVI Macro Pad 8 will be detected as human interface device and should work out of the box. Furthermore with QMK you have the freedom to fully customize each key.

Please note that a USB to microUSB cable is **not** included in any of the kits. Reuse a cable from an old electronic device or purchase a cable according to your taste. Make sure that the cable supports both power and data transfer over USB.

---

# CHAPTER 3: Software

Out of the box ANAVI Macro Pad 8 comes with [the popular open source firmware QMK](https://github.com/qmk/qmk_firmware/tree/master/keyboards/anavi/macropad8). Several different keymaps are supported. For details how to build and flash QMK firmware on ANAVI Macro Pad 8 please have a look at the [README](https://github.com/qmk/qmk_firmware/blob/master/keyboards/anavi/macropad8/readme.md).

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

# CHAPTER 5: Frequently Asked Questions (FAQ) and Troubleshooting

* How to fix `The firmware is too large! 28866/28672 (194 bytes over)`?

The easiest way to reduce the size of QMK firmware with your custom new keymap for ANAVI Macro Pad 8 it to cut some of the RGB Lighting animations and effects.

For example, in your custom keymap you can create `config.h` in the keymap directory that overwrites the main `config.h` with a reduced number of supported RGB Lighting animations and effects:

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
| 09 December 2020  | Initial manual release      | All             | Leon Anavi      |
| 03 April 2021     | Assembly guidelines         | All             | Leon Anavi      |
| 04 April 2021     | Troubleshooting             | All             | Leon Anavi      |

## ANAVI Macro Pad 8 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.1     | Stable version                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
