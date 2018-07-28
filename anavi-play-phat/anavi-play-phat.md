# ANAVI Play pHAT

**Put Your Raspberry Pi to Work: IoT hub during the day and retro gaming machine during the night!**

---

# DISCLAIMER

Raspberry Pi and the Raspberry Pi logo are registered trademarks of the Raspberry Pi Foundation. ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0). To view a copy of this license, visit https://creativecommons.org/licenses/by-sa/4.0/.

ANAVI Play pHAT hardware design is licensed under a Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Play pHAT. There are considered suitable only for ANAVI Play pHAT.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Play pHAT is an open source hardware Raspberry Pi add-on board with 8 buttons, EEPROM and 3 I2C slots for sensors. ANAVI Play pHAT is useful as a gamepad for low cost retro gaming and/or IoT hub with buttons and sensors. It was started as a hobby project by Leon Anavi in the summer of 2018. It is certified by the [Open Source Hardware Association under UID BG000007](http://certificate.oshwa.org/certification-directory/).

ANAVI Play pHAT is designed with the free and open source electronics design automation suite [KiCAD](http://kicad-pcb.org/).

Anavi is fully compatible with the Raspbian GNU/Linux distribution and open source sample applications are provided. It is also compatible with RetroPie.

## Features

ANAVI Play pHAT Raspberry Pi HAT includes:

* 8 buttons
* Slots for up to 3 plug and play I2C sensors
* EEPROM with device tree binary overlay

## Supported Raspberry Pi Versions and Models

ANAVI Play pHAT is compatible with the following Raspberry Pi versions and models:

* [Raspberry Pi 3 Model B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)
* [Raspberry Pi 3 Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/)
* [Raspberry Pi 0](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi 0 W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi Model B+](https://www.raspberrypi.org/products/model-b-plus/)
* [Raspberry Pi Model A+](https://www.raspberrypi.org/products/model-a-plus/)

ANAVI Play pHAT is **NOT** compatible with the earlier 26-pin models of Raspberry Pi 1 Model B & A's.

## Target Market

ANAVI Play pHAT is a Raspberry Pi HAT suitable for existing Raspberry Pi customers interested in retro gaming, home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, GNU/Linux gadget fans, students as well as web and/or mobile app developers. The main usage of the board is gaming and home automation without the urge of understanding perfectly the hardware.

## Board Version

Revision 1.0 of ANAVI Play pHAT was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Play pHAT is shipped in a protective antistatic bag. The HAT as well as the Raspberry Pi must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Play pHAT the following items are required:

* Compatible Raspberry Pi
* microSD card with compatible image
* USB power supply

Additionally you may attach USB mouse, keyboard, HDMI monitor or addition peripheral devices to your Raspberry Pi. It is recommended to use 2.5A (2500mA) power supply.

## Supported Peripherals

ANAVI Play pHAT Raspberry Pi HAT has 8 buttons. Up to 3 I2C sensors can be also easily attached to the pHAT.

### Sensors

The officially supported I2C sensor modules by ANAVI Play pHAT are:

* Temperature and barometric pressure (BMP180)
* Temperature and humidity (HTU21)
* Light (BH1750)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Temperature and Barometric Pressure Sensor (BMP180)

The official temperature sensor for ANAVI Play pHAT is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 5 I2C slots on ANAVI Play pHAT as follows:

| BMP180   | ANAVI Play pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Temperature and Humidity Sensor (HTU21D)

The official humidity temperature for ANAVI Play pHAT is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 5 I2C slots on ANAVI Play pHAT as follows:

| HTU21    | ANAVI Play pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Light Sensor (BH1750)

The official light I2C sensor for ANAVI Play pHAT is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 5 I2C slots on ANAVI Play pHAT as follows:

| BH1750   | ANAVI Play pHAT |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Assembly

You can mount ANAVI Play pHAT on your Raspberry Pi with your bare hands following the steps below:

* Ensure that you Raspberry Pi is compatible with ANAVI Play pHAT.
* Power off your Raspberry Pi.
* Gently mount ANAVI Play pHAT on the 40 pin header of your Raspberry Pi.
* Add sensors to your ANAVI Play pHAT.
* Optionally, you may also mount two or four brass M2.5 standoffs and the acrylic case to keep your Pi HAT snug on your Raspberry Pi while also keeping the two boards separated.
* That's all, now you are ready to go!

## Powering ANAVI Play pHAT

ANAVI Play pHAT is Raspberry Pi HAT therefore it is powered through Raspberry Pi. It is recommended to use the [official Raspberry Pi Power Supply](https://www.raspberrypi.org/products/universal-power-supply/) or another 2.5A USB power supply from reputable retailer.

---

# CHAPTER 3: Software

## Installation

In order to work correctly, ANAVI Play pHAT requires an up-to-date kernel, I2C to be enabled, and a few libraries to get started. After booting microSD card with **Raspbian**, open a terminal and follow the steps below:

* Ensure your APT package list is up-to-date:

```
sudo apt-get update
```

* Install additional applications, libraries and other tools needed by ANAVI Play pHAT

```
sudo apt-get install -y git i2c-tools vim
```

### Enable I2C

Follow the steps below to enable I2C which is required by the sensors for ANAVI Play pHAT

* Open a terminal or login remotely via SSH to your Raspberry Pi and type in the following command:

```
sudo raspi-config
```

* Select **Interfacing Options > I2C** and enable it.

* Reboot the board.

## Examples

Sample applications written in Python and the C programming language are provided for ANAVI Play pHAT under MIT license in GitHub. All examples have been tested on **Raspbian**.

Open a terminal and execute the follow the steps by step instructions to install all dependencies and to get the source code:

* Install dependencies:

```
sudo apt-get update
sudo apt-get install -y git git-core vim python-dev python-rpi.gpio
```

* Install the GPIO interface library for Raspberry Pi called [wiringPi](http://wiringpi.com/):

```
cd ~
git clone git://git.drogon.net/wiringPi
cd wiringPi
./build
```

* Download the examples for ANAVI Play pHAT Raspberry Pi HAT

```
cd ~
git clone https://github.com/AnaviTechnology/anavi-examples.git
cd anavi-examples
```

### Sensors

It is mandatory to enable **I2C** to use any of the sensors supported by ANAVI Play pHAT Raspberry Pi HAT.

#### Temperature Barometric Pressure Sensor (BMP180)

Follow the steps below to use the BMP180 I2C temperature and barometric pressure sensor with ANAVI Play pHAT:

* Connect BMP180 to any of the I2C slots on ANAVI Play pHAT using male to female Duport jumper wire.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```

* Type in the following commands to build and run the sample application that display temperature and barometric pressure:

```
cd ~/anavi-examples/sensors/BMP180/c/
make
./BMP180
```

* Verify that the output is similar to (the exact values depend on the atmospheric condition):

```
pi@raspberrypi:~/anavi-examples/sensors/BMP180/c $ ./BMP180
BMP180 Sensor Module
Temperature	28.6 C
Pressure	991.57 hPa
```

#### Temperature and Humidity Sensor (HTU21D)

Follow the steps below to use the HTU21D I2C temperature and humidity sensor with ANAVI Play pHAT:

* Connect HTU21D to any of the I2C slots on ANAVI Play pHAT using male to female Duport jumper wire.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```

* Type in the following commands to build and run the sample application that display temperature and humidity:

```
cd ~/anavi-examples/sensors/HTU21D/c/
make
./HTU21D
```

* Verify that the output is similar to (the exact values depend on the atmospheric condition):

```
pi@raspberrypi:~/anavi-examples/sensors/HTU21D/c $ ./HTU21D
HTU21D Sensor Module
25.64C
118.99%rh
```

#### BH1750 Light Sensor Module

Follow the steps below to use the BH1750 I2C light sensor with ANAVI Play pHAT:

* Connect BH1750 to any of the I2C slots on ANAVI Play pHAT using male to female Dupont jumper wires.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```

* Type in the following commands to build and run the sample application that display luminous emittance:

```
cd ~/anavi-examples/sensors/BH1750/c/
make
./BH1750
```

* Verify that the output is similar to (the exact values depend on the atmospheric condition):

```
pi@raspberrypi:~/anavi-examples/sensors/BH1750/c $ ./BH1750
BH1750 Sensor Module
Light: 418 Lux
```

## Device Tree Overlays

Device Tree (DT) in Linux is a description of the hardware in a system. The DT overlay adds a number of optional elements.

The EEPROM of ANAVI Play pHAT contains DT overlay with description of the peripheral devices on the HAT. After adding Anavi to your Raspberry Pi and booting it you  should have some new filesystem nodes at */proc/device-tree/hat*:

```
pi@raspberrypi:~ $ ls -l /proc/device-tree/hat/
total 0
-r--r--r-- 1 root root  4 Feb 15 00:27 name
-r--r--r-- 1 root root 20 Feb 15 00:27 product
-r--r--r-- 1 root root  7 Feb 15 00:27 product_id
-r--r--r-- 1 root root  7 Feb 15 00:27 product_ver
-r--r--r-- 1 root root 37 Feb 15 00:27 uuid
-r--r--r-- 1 root root  6 Feb 15 00:27 vendor
```

The information provided in these filesystem nodes helps you to identify ANAVI Play pHAT vendor, version, product name, etc. For example:

```
pi@raspberrypi:~ $ cat /proc/device-tree/hat/product
ANAVI Play pHAT

pi@raspberrypi:~ $ cat /proc/device-tree/hat/vendor
ANAVI
```

More information about device trees, overlays and parameters are available at [the official Raspberry Pi documentation](https://www.raspberrypi.org/documentation/configuration/device-tree.md).

---

# CHAPTER 4: RetroPie

[RetroPie](https://retropie.org.uk/) is a free GNU/Linux distribution that turns Raspberry Pi into a retro-gaming machine. It builds upon popular open source projects such as Raspbian, EmulationStation, RetroArch and many other to enable you to play your favourite Arcade, home-console, and classic PC games with the minimum efforts for setup.

Python script has to be launched to ensure that ANAVI Play pHAT will work with the emulators provided in RetroPie. Follow the steps below to install and configure it:

* Download [RetroPie](https://retropie.org.uk/) and flash it on microSD card
* Boot RetroPie, login as user **pi** via SSH or open a terminal to execute the following commands:
```
sudo apt-get update
sudo apt-get install -y python-pip
sudo pip install evdev
```
* Download the open source examples from GitHub that bring all needed scripts:
```
cd ~
git clone https://github.com/AnaviTechnology/anavi-examples.git
```
* Open file **/etc/rc.local** (using sudo) with you favorite text editor, for example nano, append the follow line at the end **before** *exit 0*:
```
sudo python /home/pi/anavi-examples/anavi-play-phat/anavi-play-gamepad.py &
```
* Reboot RetroPie

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Play pHAT utilize the following pins on Raspberry Pi:

| Component    | Pins                            |
| ------------ |:------------------------------- |
| I2C          | 3, 5                            |
| EEPROM       | 27, 28                          |
| Button UP    | 15                              |
| Button DOWN  | 13                              |
| Button LEFT  | 7                               |
| Button RIGHT | 11                              |
| Button START | 29                              |
| Button SELECT| 31                              |
| Button A     | 35                              |
| Button B     | 37                              |

For more details have a look at [the KiCad project which is available in GitHub](https://github.com/AnaviTechnology/anavi-play-phat).

## I2C

The sensors that can be connected to ANAVI Play pHAT communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Play pHAT includes two 4.7kohm resistors labelled as R6 and R7. If for one reason or another you need to disable the I2C pullup resistors remove R6 and R7.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

#### May I use ANAVI Play pHAT with other operating systems?

Yes, you can use ANAVI Play pHAT with other GNU/Linux distributions and even other operating systems but some porting efforts might be required.

#### May I use other I2C sensors with ANAVI Play pHAT?

Yes, you can use other I2C sensors with ANAVI Play pHAT but you should take care for their drivers and software support.

#### May I use non-I2C sensors with ANAVI Play pHAT?

No.

#### Is ANAVI Play pHAT software free and open source?

Yes, the official ANAVI Play pHAT software is free and open source. The examples are available under MIT license and the rest is available under GPLv3. Please contact us if you are working on a commercial product and you would like to use the software under alternative commercial license.

---

# CHAPTER 7: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 28 July 2018      | Initial release             | All             | Leon Anavi      |

## ANAVI Play pHAT Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | First version                                                |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
