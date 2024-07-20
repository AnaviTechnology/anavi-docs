# ANAVI Handle

**Open source USB adapter for Nunchuk compatible controller with Raspberry Pi RP2040 MCU**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with ANAVI Technology products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Handle hardware designs are licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by ANAVI Technology in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. ANAVI Technology shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by ANAVI Technology to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Handle. They are considered suitable only for ANAVI Handle.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Handle lets you easily connect a Wii Nunchuk-compatible controller to any USB-equipped computer. It features Seeed Studio’s XIAO RP2040 module, which offers a USB Type-C connector along with a Raspberry Pi RP2040 microcontroller.

## Features

ANAVI Handle boasts a compact design with a black, gold-plated printed circuit board with the cutting-edge Seeed Studio XIAO RP2040 module. Here are the technical specifications:

* **MCU:** Raspberry Pi RP2040
* **Connectivity:** USB-C
* **Firmware:** open-source based on CircuitPython
* **Compatibility:** Windows, macOS, and Linux support
* **Dimensions:** 35.0 mm x 33.3 mm (1.38 x 1.31 inches)

## Board Version

Revision 1.0 of ANAVI Handle was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Handle is shipped as a do-it-yourself (DIY) kit, with all parts enclosed in protective bags. To prevent damage, ensure the board is **NOT** exposed to high electrostatic potentials. Always wear a grounding strap or a similar protective device when handling the board, and avoid touching the component pins or any other metallic elements.

## Requirements

In order to setup ANAVI Handle the following items are required:

* Personal Computer with MS Windows, Mac OS or GNU/Linux distribution
* USB to USB-C cable
* Nunchuk or a compatible controller

Getting started with ANAVI Handle is easy. By default the device comes pre-installed with [open source firmware](https://github.com/AnaviTechnology/anavi-handle-sw) written in [CircuitPython](https://circuitpython.org/).

## Assembly

### Step 1: Peel Off Protective Film

The acrylic enclosure consists of two laser-cut parts, each covered with protective film on both sides. Carefully remove the film from all surfaces to reveal the crystal-clear acrylic.

### Step 2: Align Acrylic Enclosure

Take the top part of the acrylic enclosure, which features a knob that fits into the notch of the Nunchuk connector. Insert a screw into each of the four mounting holes and secure each one with a nut.

### Step 3: Printed Circuit Board

The ANAVI Handle features a gold-plated printed circuit board with a black solder mask. It has four mounting holes, one in each corner. Position the PCB onto the four screws beneath the nuts securing the top part of the acrylic enclosure.

### Step 4: Affix the Enclosure  

Secure the bottom part of the acrylic enclosure by fastening it tightly with four nuts.

### Step 5: Connect

Connect your Wii Nunchuk controller to your computer using the ANAVI Handle, which features firmware written in CircuitPython. Currently, it supports three modes: joystick, keyboard, and mouse. The default open-source firmware uses an RGB LED to indicate the connection status:

* Green light: Nunchuk controller is connected correctly.

* Blue light: The Nunchuk controller is disconnected from the ANAVI Handle.

* Red light: The Nunchuk controller is absent or improperly connected.

Please note that a USB to USB-C cable is **not** included in any of the kits. Re-use a cable from an old electronic device or purchase a cable according to your taste. Make sure that the cable supports both power and data transfer over USB.

---

# CHAPTER 3: Software

Out of the box ANAVI Handle comes with [open source firmware](https://github.com/AnaviTechnology/anavi-handle-sw) written in [CircuitPython](https://circuitpython.org/).

If you need to reset ANAVI Handle and restore it to factory defaults, follow the steps below to install CircuitPython and the open source firmware:

* Download [CircuitPython for XIAO RP2040](https://circuitpython.org/board/seeeduino_xiao_rp2040/)

* Press and hold **B** button on XIAO RP2040 and ANAVI Handle.

* Copy the downloaded CircuitPython file to XIAO RP2040 and ANAVI Handle.

* Wait until ANAVI Handle and XIAO RP2040 installs CircuitPython.

* Copy [firmware files from GitHub](https://github.com/AnaviTechnology/anavi-handle-sw) to XIAO RP2040

* Install CircuitPython dependencies on XIAO RP2040 installs CircuitPython:

Make sure that you have ``circup`` installed in your Python environment.
Install it with the following command if necessary:

```
pip3 install circup
```

With ``circup`` installed and your CircuitPython device connected use the following command to install:

```
circup install adafruit_bus_device adafruit_hid adafruit_nunchuk adafruit_seesaw neopixel
```

Or the following command to update an existing version:

```
circup update
```

---

# CHAPTER 4: Hardware Schematics

ANAVI Handle is an entirely open source project that harmonizes open-source hardware with free and open-source software. The [printed circuit board and its acrylic enclosure](https://github.com/AnaviTechnology/anavi-handle) were designed in [KiCad](https://www.kicad.org/), an open-source software suite for electronic design automation (EDA) that runs on Windows, MacOS, and GNU Linux distributions.

The [Open Source Hardware Association (OSHWA)](https://www.oshwa.org/) has officially granted certification to ANAVI Handle. OSHWA, a renowned non-profit organization based in the United States, oversees the Certified Projects Directory and hosts the esteemed Open Hardware Summit annually. OSHWA’s certification program ensures that a project’s conception of "open source hardware" harmonizes with the broader community’s definition, thus guaranteeing transparency and accessibility.

Each certified hardware version is distinguished by a unique identification number (UID) comprising a country code and a numerical sequence. On April 19th, ANAVI Handle version 1.0 received certification with the [UID BG000134](https://certification.oshwa.org/bg000134.html). The OSHW Certification Mark showcases the project’s unique certification ID and streamlines navigation and information retrieval for interested parties. The "BG" prefix signifies Bulgaria, indicating that ANAVI Handle originates from the historic city of Plovdiv, Bulgaria’s second-largest city and Europe’s oldest continually inhabited city, boasting over 6000 years of rich history.

## Pinout

ANAVI Handle utilizes the following pins on [Seeed Studio XIAO RP2040](https://wiki.seeedstudio.com/XIAO-RP2040/):

| Component           | Pins                                   |
| ------------------- |:-------------------------------------- |
| I2C                 | D4 (SDA), D5 (SCL)                     |

---

# CHAPTER 5: Frequently Asked Questions (FAQ)

* Does the ANAVI Handle work with the Wii Classic Controller?

The hardware connector on ANAVI Handle is compatible with the Wii Classic Controller. Currently, the [open-source firmware written in CircuitPython](https://github.com/AnaviTechnology/anavi-handle-sw) supports only Nunchuk-compatible controllers. However, it can be extended to support the Classic Controller using [libraries from Adafruit](https://github.com/adafruit/Adafruit_CircuitPython_Wii_Classic).

# CHAPTER 6: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author             |
| ----------------- |:---------------------------:| :---------------| :------------------|
| 24 May 2024       | Initial manual release      | All             | Leon Anavi         |
| 20 July 2024      | Frequently Asked Questions  | All             | Leon Anavi         |

## ANAVI Handle

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable version                                               |

## See Also

For more information please visit [anavi.technology](https://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
