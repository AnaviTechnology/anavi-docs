# ANAVI Macro Pad 2

**Open source, programmable two-key mechanical keypad with backlighting**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with ANAVI Technology products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Macro Pad 2 hardware design is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by ANAVI Technology in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. ANAVI Technology shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by ANAVI Technology to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Macro Pad 2. They are considered suitable only for ANAVI Macro Pad 2.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Macro Pad 2 is an open source, custom programmable, tiny 2% mechanical keyboard/keypad. Each of the two keys allows you to reprogram and use it as macro keypad or even dedicated shortcut keys.

ANAVI Macro Pad 2 can be customized for multiple use cases across various industries. It is the perfect fit for copy and paste as well as video conferencing applications. You can easily turn the camera or microphone on or off. Various keymaps are available, including for Zoom, Jitsi, Skype, Microsoft Teams, Google Meet, and Git.

ANAVI Macro Pad 2 boosts your daily productivity by providing an amazing level
of control with gorgeous light effects at your fingertips!

ANAVI Macro Pad 2 is an entirely open source project that combines open source hardware with free and open source software.

Only free and open source software tools like KiCad, OpenSCAD, and Inkscape were used to design ANAVI Macro Pad 2. [Quantum Mechanical Keyboard (QMK)](https://qmk.fm/) with V-USB is the default open source firmware. Source code and schematics are [available on GitHub](https://github.com/anavitechnology/).

ANAVI Macro Pad 2 runs thanks to [Microchip ATtiny85](https://www.microchip.com/wwwproducts/en/ATtiny85). This is a low-cost reliable 8-bit AVR RISC-based microcontroller. Although ATtiny85 is not as robust as ATmega32U4 or ATmega328P, the affordable price, reliability and small package makes ATtiny85 popular among both enthusiasts and professionals. ANAVI Macro Pad 2 uses the open source project V-USB that provides a software-only implementation of a low-speed USB device.

ANAVI Macro Pad 2 is made in Plovdiv, Bulgaria, EU and packaged in a eco-friendly recyclable cardboard box.

## Features

ANAVI Macro Pad 2 features:

* **Keys:** 2 Gateron red mechanical switches with 3 mm LED backlit and translucent keycaps
* **CPU:** [Microchip ATtiny85](https://www.microchip.com/wwwproducts/en/ATtiny85)
* **Connectivity:** microUSB
* **Firmware:** Quantum Mechanical Keyboard (QMK) open source firmware
* **Compatibility:** Windows, MacOS, and GNU/Linux support
* **Dimensions:** 40x38 mm (1.60x1.50 inches)

## Target Market

ANAVI Macro Pad 2 can be customized to fit multiple use cases across various industries: video conferencing software, video or audio editing, entertainment broadcasting, product and graphic design, gaming, engineering, programming, etc. It boosts your daily productivity by providing amazing level of control with gorgeous light effects on your fingertips!

## Board Version

Revision 1.0 of ANAVI Macro Pad 2 was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Macro Pad 2 is shipped in a protective bag. The board must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Macro Pad 2 the following items are required:

* Computer
* USB to microUSB cable

Getting started with and assembled ANAVI Macro Pad 2 is easy. Just connect it to your Linux, Windows, or macOS computer, and use a browser to configure and load your keyswitch macro or shortcut settings.

ANAVI Macro Pad 2 relies on the Quantum Mechanical Keyboard (QMK) firmware, To configure and modify the keyboard layouts you can use QMK Configurator, an online graphical user interface that generates QMK firmware hex files directly in a web browser or use the source code. Connect ANAVI Macro Pad 2 to a computer with USB to microUSB cable to enter flash mode and upload the new firmware.

Furthermore, ANAVI Macro Pad 2 is powered by a Microchip ATtiny85 microcontroller, so it is possible to use as an Adafruit Trinket-compatible development board and upload Arduino sketches through Arduino IDE or PlatformIO.

## Assembly

### ANAVI Macro Pad 2 Maker Kit

**NOTE:** The **maker** kit is for advanced users and requires soldering skills. If you have a developer kit chip this chapter.

The maker kit provides the printed circuit board and an addressable LED strip. There are also some nice stickers. Other accessories have to be purchased separately. You can use any mechanical switches compatible with Cherry MX plate footprint and 3mm LEDs.

**NOTE:** With the maker kit you can also perform [a hot-swap upgrade of ANAVI Macro 8](https://www.youtube.com/watch?v=lnFSAm9R4j0). It requires a very specific procedure explained in [this video](https://www.youtube.com/watch?v=lnFSAm9R4j0). If you have in mind a hot-swap upgrade do not solder anything and have a look at [the video](https://www.youtube.com/watch?v=lnFSAm9R4j0).

For soldering and a standard assembly of the **maker kit** several tools are required: a soldering iron, a screwdriver, scissors, tweezers and a keycap puller might be also useful. It is also a good idea to stay safe and get a smoke absorber while soldering, for example [ANAVI Fume Extractor](https://anavi.technology/#products).

Please have [a look at the video](https://www.youtube.com/watch?v=AlH5sLEsoNc) and follow the steps below to assemble ANAVI Macro Pad 2 **Maker** Kit.

* Solder mechanical switches to the printed circuit board

Any mechanical switches compatible with Cherry MX plate or PCB footprint are suitable for ANAVI Macro Pad 2. The developer kit comes with Gateron red mechanical switches. The maker kits allows you to choose another brand, type and color.

Choosing the most appropriate switch for your needs is a matter of personal preference. There are many different brands and colors. For example, the blue mechanical switches are more noisy which could be sometimes fun but also annoying during daily work. The red switches are fast and not very noisy therefore they are often proffered by gamers.

There are two pins on each mechanical switch that must be soldered to the printed circuit board. That makes 4 pins in total for the 2 keys on ANAVI Macro Pad 2. The position of the each of the pins is very specific and you can easily recognize it. One of the pins for the signal coming from the Microchip ATtiny85 microcontroller, the other pin is for ground.

* Solder 3mm LED

This step is actually optional depending on the the type of the mechanical switch. Some mechanical switches may not have a hole in the plastic enclosure for a 3mm LED. For example, the Gateron red switches have a dedicated place specially for 3mm LEDs.

Each 3mm LED for through-hole soldering has 2 legs. The longer leg is the positive terminal, also known as anode. The shorter leg is negative and also known as cathode.

The shorter leg that indicates the negative terminal must go into the square hole of the PCB. ANAVI Macro Pad 2 has 2 mechanical switches therefore 2 LEDs are required. If you want you can use different color of the LEDs. You can even mix colors.

Once you are ready with these 2 steps your ANAVI Macro Pad 2 should looks just like a developer kit having all accessories soldered. Therefore the next steps are the same as for both the developer and the maker kit.

### ANAVI Macro Pad 2 Developer Kit

Please have [a look at the video](https://www.youtube.com/watch?v=AlH5sLEsoNc) and follow the steps below to assemble ANAVI Macro Pad 2 **Developer** Kit. Although you can do it with your bare hands, simple tools like a screwdriver, tweezers and a keycap puller might be useful.

* Stickers

*This step is optional.* Each kit includes a set of stickers. Feel free to add them to the translucent keycaps included in ANAVI Macro Pad 2 developer kit. You can do it with your bare hand or eventually with the help of tweezers.

You can place a sticker on the top or on the side of the keycap. If you like retro electronics you may find some similarities in this approach to the famous keyboard of the best selling personal computer of the 20th century Commodore 64.

ANAVI Macro Pad 2 is powered by the popular open source firmware QMK which allows you to create various layouts. You can make a keymap with 2 or more layouts. A sticker on the side of the keycap might be useful as a visual aid to indicate the additional function of the key.

* Keycaps

Place all keycaps on the 2 mechanical switches of ANAVI Macro Pad 2. You can easily do this with your bare hands. It takes just a few seconds.

As you can see [in the video](https://www.youtube.com/watch?v=AlH5sLEsoNc), a keycap puller might be useful if you make a mistake and want to pull off a keycap and place it on another location.

* Peel Off Protective Films from the Acrylic Enclosure

Peel off the protective films from both sides of the two laser cut transparent acrylic parts. The removal of the protective films is quite annoying but once you get rid of them, the acrylic enclosure will be crystal clear and fully transparent.

* Assemble the Acrylic Enclosure

Assemble the acrylic enclosures. In the cardboard box you also will find M2.5 screws, nuts and washers. Although you can assemble them with your bare hands a screw driver will be very handy.

Use the two longer screws for the two mounting holes near the microUSB connector. Use 6 nuts and a couple of washer to attach the top and the bottom acrylic enclosures to the printed circuit board. Use the shorter screw for the mounting whole between the two mechanical switches as it should hold only the bottom acrylic enclosure.

Finally add the silicon protective pads to the bottom. There are 8 pads. Add two of them them on top of each other to the 4 corners of the bottom acrylic plate.

* Turn On ANAVI Macro Pad 2

Gently use a USB to microUSB cable to connect ANAVI Macro Pad 2 to a personal computer. Please be careful with the microUSB connector, because a harsh bending of the USB cable may damage the microUSB connector.

ANAVI Macro Pad 2 relies on QMK firmware, [Micronucleus](https://github.com/micronucleus/micronucleus) bootloader and [V-USB](https://www.obdev.at/products/vusb/index.html), an open source software-only implementation of a low-speed USB device for Atmel’s AVR® microcontrollers. There is 5 second boot delay during which the Microchip ATtiny85 microcontroller on ANAVI Macro Pad 2 can be reprogrammed.

Thanks to the QMK firmware, ANAVI Macro Pad 2 will be detected as human interface device and should work out of the box. Furthermore with QMK you have the freedom to fully customize each key.

Please note that a USB to microUSB cable is **not** included in any of the kits. Reuse a cable from an old electronic device or purchase a cable according to your taste. Make sure that the cable supports both power and data transfer over USB.

---

# CHAPTER 3: Software

Out of the box ANAVI Macro Pad 2 comes with [the popular open source firmware QMK](https://github.com/qmk/qmk_firmware/tree/master/keyboards/anavi/macropad8). Several different keymaps are supported. For details how to build and flash QMK firmware on ANAVI Macro Pad 2 please have a look at the [README](https://github.com/qmk/qmk_firmware/blob/master/keyboards/anavi/macropad2/readme.md).

## Flashing

### Prerequisites

```bash
git clone https://github.com/micronucleus/micronucleus.git
cd micronucleus/commandline/
sudo make install
```

On GNU/Linux distributions, you will need proper privileges to access the MCU. You can either use `sudo` when flashing firmware, or place [these files](https://github.com/micronucleus/micronucleus/blob/master/commandline/49-micronucleus.rules) in /etc/udev/rules.d/. Once added run the following:

```bash
sudo udevadm control --reload-rules
sudo udevadm trigger
```

### Instructions

* Run one of the following commands:

```bash
make anavi/macropad2:default:flash

# or directly with...
micronucleus --run <firmware.hex>
```

* Plug ANAVI Macro Pad 2 to the USB port and the flashing procedure should start

### Recovery

* [Original Firmware](https://github.com/AnaviTechnology/anavi-macro-pad-2/tree/main/bootloader)
* [Bootloader Repair](https://digistump.com/wiki/digispark/tutorials/proisp)

---

# CHAPTER 4: Hardware Schematics

## Pinout

ANAVI Macro Pad 2 utilize the following pins on Microchip ATtiny85:

| Component           | Pins                            |
| ------------------- |:------------------------------- |
| USB                 | PB3, PB4                        |
| Mechanical Switches | PB0, PB2                        |
| 3mm LEDs            | PB1                             |

---

# CHAPTER 5: Frequently Asked Questions (FAQ) and Troubleshooting

---

# CHAPTER 6: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 06 May 2021       | Initial manual release      | All             | Leon Anavi      |

## ANAVI Macro Pad 2 Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable version                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
