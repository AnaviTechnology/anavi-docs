# RabbitMax Flex

**Open source Raspberry Pi HAT for Internet of Things (IoT)**

---

# DISCLAIMER

The information in this document is provided in connection with RabbitMax products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of RabbitMax products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of
this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

RabbitMax Flex hardware design is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by RabbitMax in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. RabbitMax shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by RabbitMax to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create RabbitMax Flex. There are considered suitable only for RabbitMax Flex.

---

# CHAPTER 1: Overview

## Introduction

RabbitMax Flex is an open source hardware Raspberry Pi HAT for Internet of Things (IoT). RabbitMax Flex was started as a hobby project by Leon Anavi in 2016. It is suitable for do it yourself (DIY) weather station, automated desk assistant or rapid prototyping Internet of Things (IoT).

RabbitMax Flex is designed with the free and open source electronics design automation suite KiCAD. No soldering is required. You can assemple RabbitMax Flex to your Raspberry Pi with your bare hands.

RabbitMax is fully compatible with the Raspbian GNU/Linux distribution and open source sample applications are provided. RabbitMax Flex also supports its own RabbitMax IoT GNU/Linux distribution which is based on the Yocto Project and Openembedded and features open source daemon for communicating with other Internet ot Things (IoT) through the lightweight machine-to-machine connectivity protocol MQTT.

## Features

RabbitMax Flex Raspberry Pi HAT includes:

* Relay
* IR LED
* IR photo sensor
* Piezo buzzer
* Button
* RGB LED
* Slot for modular LCD character display
* Slots for up to 5 plug and play I2C sensors

## Supported Raspberry Pi Versions and Models

RabbitMax Flex is compatible with the following Raspberry Pi version and models:

* Raspberry Pi 3 
* Raspberry Pi 2 
* Raspberry Pi 0
* Raspberry Pi Model B+
* Raspberry Pi Model A+

RabbitMax Flex is **NOT** compatible with the earlier 26-pin models of Raspberry Pi 1 Model B & A's.

## Target Market

RabbitMax Flex is a Raspberry Pi HAT suitable for existing Raspberry Pi customers interested in home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, GNU/Linux gadget fans, students as well as web and/or mobile app developers. The main usage of the board is embedded software development without the urge of understanding perfectly the hardware.

## Board Version

Revision 1.1 of RabbitMax Flex was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

RabbitMax Flex is shipped in a protective antistatic bag. The HAT as well as the Raspberry Pi must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

## Supported Peripherals

### Sensors

#### Temperature Sensor

The official temperature sensor for RabbitMax Flex is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 5 I2C slots on RabbitMax Flex as follows:

| BMP180   | RabbitMax Flex |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Humidity Sensor

The official humidity temperature for RabbitMax Flex is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 5 I2C slots on RabbitMax Flex as follows:

| HTU21    | RabbitMax Flex |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Light Sensor

The official light I2C sensor for RabbitMax Flex is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 5 I2C slots on RabbitMax Flex as follows:

| BH1750   | RabbitMax Flex |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

### LCD Display Modules

RabbitMax Flex supports monochrome 1602 character LDC alphanumeric display screen with 16 characters on two rows. Plug the display in the 16 female header pins above the logo of RabbitMax Flex. Use a screwdriver to adjust the brightness of the backlight of the display through the potentiometer.

## Assembly

Ensure that you Raspberry Pi is compatible with RabbitMax Flex. Power off your Raspberry Pi. Gently mount RabbitMax Flex on the 40 pin header of your Raspberry Pi. Optionally, you may also assemple two brass M2.5 standoffs to keep your Pi HAT snug on your Raspberry Pi while also keeping the two boards separated, in particular the HDMI port. That's all, now you are ready to go!

## Powering RabbitMax Flex

RabbitMax Flex is Raspberry Pi HAT therefore it is powered through Raspberry Pi. It is recommended to use the [official Raspberry Pi Power Supply](https://www.raspberrypi.org/products/universal-power-supply/) or another 2.5A USB power supply from reputable retailer.

---

# CHAPTER 3: Software

## Installation

In order to work correctly, RabbitMax Flex HAT requires an up-to-date kernel, I2C to be enabled, and a few libraries to get started. After booting microSD card with Raspbian, open a terminal and execute the following commands:

* Ensure your APT package list is up-to-date:

```
sudo apt-get update
```

* Upgrade packages

```
sudo apt-get upgrade
```

* Install additional applications, libraries and other tools needed by RabbitMax Fles

```
sudo apt-get install -y git i2c-tools lirc
```

### Enable I2C

### Enable infrared (IR)

## Examples

### Relay

### Piezo Buzzer

### Button

### RGB LED

### LCD Display Module

### Sensors

#### Temperature Sensor (BMP180)

#### Humidity Sensor (HTU21D)

#### Light Sensor (BH1750)

## LIRC

## Device Tree Overlays

## Debugging

---

# CHAPTER 4: RabbitMax IoT GNU/Linux Distribution

---

# CHAPTER 5: Schematics

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

#### May I use RabbitMax Flex with other operating systems?

Yes, you can use RabbitMax Flex with other GNU/Linux distributions and even other operating systems but some porting effords might be required.

#### May I use other I2C sensors with RabbitMax Flex?

Yes, you can use other I2C sensors with RabbitMax Flex but you should take care for their drivers and software support.

#### May I use non-I2C sensors with RabbitMax Flex?

No.

#### Is RabbitMax Flex software free and open source?

Yes, the official RabbitMax Flex software is free and open source. The examples are available under MIT license and the rest is available under GPLv3. Please contact us if you are working on a commercial product and you would like to use the software under alternative commercial license.

---

# CHAPTER 7: Revision History

## Document Revision

| Date             | Changes                | Modified pages  |
| ---------------- |:----------------------:| :---------------|
| 14 September 2016| Initial manual release | All             |

## RabbitMax Flex HAT Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | First prototype                                              |
| 1.1     | Piezo buzzer and button changed, potentiometer added         |

## See Also

For more information please visit [rabbitmax.com](http://rabbitmax.com/) and our [GitHub repositories](https://github.com/RabbitMax). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/RabbitMax-1632492473734364/), [Twitter](https://twitter.com/rabbitmaxcom) or [email](mailto:info@rabbitmax.com).

---
