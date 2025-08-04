# ANAVI TPM 2.0

***A hardware security add-on board for Raspberry Pi computers*

---

# DISCLAIMER

Raspberry Pi and the Raspberry Pi logo are registered trademarks of the Raspberry Pi Foundation. ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0). To view a copy of
this license, visit https://creativecommons.org/licenses/by-sa/4.0/

ANAVI TPM 2.0 hardware design is licensed under a  Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI TPM 2.0. They are considered suitable only for ANAVI TPM 2.0.

---

# Overview

## Introduction

[ANAVI TPM 2.0](https://www.crowdsupply.com/anavi-technology/anavi-tpm-2-0-for-raspberry-pi) is a user-friendly add-on board for Raspberry Pi single board computers that interfaces via the SPI bus and is based on the Infineon Optiga SLB 9672 TPM 2.0 chip.

Trusted Platform Module (TPM) 2.0 is an industry standard designed to deliver robust, hardware-based security. It supports trusted computing by securely managing cryptographic keys and enabling features such as disk encryption, device authentication, digital signatures, and measured boot. Commonly integrated into both enterprise and consumer systems, TPM 2.0 plays a vital role in protecting sensitive information and ensuring the integrity of computing platforms.

ANAVI TPM 2.0 is a fully open-source project that combines open hardware with free and open-source software. It provides a reliable solution for secure key storage and cryptographic operations, and it can also function as a True Hardware Random Number Generator (TRNG), offering a high-entropy source suitable for security-critical applications. The printed circuit board was designed using [KiCAD](http://kicad.org/), an open-source electronics design suite. No soldering is required. You can assemble ANAVI TPM 2.0 to your Raspberry Pi with your bare hands.

ANAVI TPM 2.0 for Raspberry Pi is fully compatible with the Raspberry Pi OS.

## Features

**Trusted Platform Module**: Infineon Optiga SLB 9672 TPM 2.0
**Standards compliance**: Compliant with TCG TPM Library specification revision 1.59 and PC Client Platform TPM Profile (PTP) version 1.05
**Random Number Generator (RNG)**:  implemented according to NIST SP 800-90A using entropy source according to NIST SP 800-90B
**Compatibility**: Works with all Raspberry Pi single board computers
**Interface**: Serial Peripheral Interface (SPI)
**Compact**: Only uses 10 header pins (2x5 pins: 17 to 26), leaving other GPIO pins free
**Secure mounting**: Small hole included for physical attachment
**Dimensions**: 18.4 x 12.9 mm (0.72 x 0.51 in)

## Supported Raspberry Pi Versions and Models

ANAVI TPM 2.0 is compatible with the following Raspberry Pi versions and models:

* [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)
* [Raspberry Pi 400](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
* [Raspberry Pi 4 Model B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
* [Raspberry Pi 3 Model A+](https://www.raspberrypi.com/products/raspberry-pi-3-model-a-plus/)
* [Raspberry Pi 3 Model B+](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/)
* [Raspberry Pi 3 Model B](https://www.raspberrypi.com/products/raspberry-pi-3-model-b/)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.com/products/raspberry-pi-2-model-b/)
* [Raspberry Pi Zero](https://www.raspberrypi.com/products/raspberry-pi-zero/)
* [Raspberry Pi Zero W](https://www.raspberrypi.com/products/raspberry-pi-zero-w/)
* [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)
* [Raspberry Pi Model B+](https://www.raspberrypi.com/products/raspberry-pi-1-model-b-plus/)
* [Raspberry Pi Model A+](https://www.raspberrypi.com/products/raspberry-pi-1-model-a-plus/)

## Target Market

Designed as open source hardware, ANAVI TPM 2.0 is intended for developers, hobbyists, and professionals who require enhanced security for Raspberry Pi-based projects.

## Board Version

Revision 1.1 of ANAVI TPM 2.0 was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# Getting Started

## Electrostatic Warning

ANAVI TPM 2.0 is shipped in a protective antistatic bag. The add-on board as well as the Raspberry Pi must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI TPM 2.0 the following items are required:

* Raspberry Pi single board computer
* microSD card with compatible image
* Power supply

Additionally you may attach USB mouse, keyboard, HDMI monitor or addition peripheral devices to your Raspberry Pi.

## Assembly

You can assemble ANAVI TPM 2.0 and mount it on your Raspberry Pi with your bare hands following the steps below:

* Ensure that you Raspberry Pi is compatible with ANAVI TPM 2.0.
* Power off your Raspberry Pi.
* Gently mount ANAVI TPM 2.0 on the 40 pin header of your Raspberry Pi.

## Powering ANAVI TPM 2.0

ANAVI TPM 2.0 is Raspberry Pi HAT therefore it is powered through Raspberry Pi. It is recommended to use the [official Raspberry Pi Power Supply](https://www.raspberrypi.org/products/universal-power-supply/) or another 2.5A USB power supply from reputable retailer.

---

# Software

ANAVI TPM 2.0 is compatible with the `tpm-slb9670.dtbo` device tree binary overlay, which is [included in the official Raspberry Pi Linux kernel](https://github.com/raspberrypi/linux/blob/rpi-6.12.y/arch/arm/boot/dts/overlays/tpm-slb9670-overlay.dts), enabling seamless integration.

---

# Schematics

## Pinout

The components of ANAVI TPM 2.0 utilize the following pins on Raspberry Pi:

| Component    | Pins                            |
| ------------ |:------------------------------- |
| MISO         | 24                              |
| MOSI         | 21                              |
| SCLK         | 19                              |
| CS           | 20                              |
| PIRQ         | 18                              |
| RST          | 17                              |

---

# Frequently Asked Questions (FAQ)

#### Which device tree binary overlay should be used with ANAVI TPM 2.0?

Although ANAVI TPM 2.0 features Infineon Optical™ SLB 9672, the SPI communication is compatible with the previous generation Infineon Optical™ SLB 9670 and the `tpm-slb9670.dtbo` device tree binary overlay, which is [included in the official Raspberry Pi Linux kernel](https://github.com/raspberrypi/linux/blob/rpi-6.12.y/arch/arm/boot/dts/overlays/tpm-slb9670-overlay.dts).

---

# Revision History

## Document Revision

| Date              | Changes                     | Author         |
| ----------------- |:---------------------------:|:---------------|
| 04 August 2025    | Initial manual release      | Leon Anavi     |

## ANAVI TPM 2.0 Revisions

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.1     | First stable version                                         |

## See Also

For more information please visit [anavi.technology](https://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
