# ANAVI Light pHAT

**Make your Raspberry Pi bright and shiny with RGB LED strip and ANAVI Light pHAT!**

---

# DISCLAIMER

Raspberry Pi and the Raspberry Pi logo are registered trademarks of the Raspberry Pi Foundation. ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
this license, visit https://creativecommons.org/licenses/by-sa/4.0/.

ANAVI Light pHAT hardware design is licensed under a Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Light pHAT. There are considered suitable only for ANAVI Light pHAT.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Light pHAT is an open source hardware Raspberry Pi add-on board for controlling RGB LED strip and collecting data from various sensors for light, temperature, humidity, color and gesture recognition as well as from PIR motion sensor.

ANAVI Light pHAT is designed with the free and open source electronics design automation suite [KiCAD](http://kicad-pcb.org/). No soldering is required. You can assemble ANAVI Light pHAT to your Raspberry Pi with your bare hands and a screwdriver to attach 12V RGB LED strip.

ANAVI Light pHAT is fully compatible with the Raspbian GNU/Linux distribution and open source sample applications are provided.

## Features

ANAVI Light pHAT includes:

* Terminal block for attaching 12 V RGB LED strip
* Slots for up to three plug and play I2C sensor modules
* Slot for PIR motion sensor
* UART pins for debugging
* EEPROM with board manufacturer information and a device tree fragment

## Supported Raspberry Pi Versions and Models

ANAVI Light pHAT is compatible with the following Raspberry Pi versions and models:

* [Raspberry Pi 3 Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/)
* [Raspberry Pi 0](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi 0 W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi Model B+](https://www.raspberrypi.org/products/model-b-plus/)
* [Raspberry Pi Model A+](https://www.raspberrypi.org/products/model-a-plus/)

ANAVI Light pHAT is **NOT** compatible with the earlier 26-pin models of Raspberry Pi 1 Model B & A's.

## Target Market

ANAVI Light pHAT is a Raspberry Pi add-on suitable for existing Raspberry Pi customers interested in home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, GNU/Linux gadget fans, students as well as web and/or mobile app developers. The main usage of the board is home automation of lights with RGB LED strip, sensors and the popular open source software Home Assistant.

## Board Version

Revision 1.1 of ANAVI Light pHAT was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Light pHAT is shipped in a protective bag. The pHAT as well as the Raspberry Pi must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Light pHAT the following items are required:

* Compatible Raspberry Pi
* microSD card with compatible image
* USB power supply
* 12V RGB LED strip
* 12V power supply

Additionally you may attach USB mouse, keyboard, HDMI monitor or addition peripheral devices to your Raspberry Pi. It is recommended to use 2.5A (2500mA) power supply.

## Supported Peripherals

ANAVI Light pHAT has a terminal block for attaching 12V RGB LED strip, a slot for attaching PIR motion sensor as well as up to 3 slots I2C sensors.

### Sensors

ANAVI Light pHAT supports PIR motion sensor. The officially supported I2C sensor modules are for:

* Light (BH1750)
* Temperature and humidity (HTU21D)
* Color and gesture recognition (APDS-9960)
* Temperature and barometric pressure (BMP180)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Light Sensor

The official light I2C sensor for ANAVI Light pHAT is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 5 I2C slots on ANAVI Light pHAT as follows:

| BH1750   | ANAVI Light pHAT |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |


#### Temperature & Humidity Sensor

The official temperature and humidity sensor for ANAVI Light pHAT is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 5 I2C slots on ANAVI Light pHAT as follows:

| HTU21    | ANAVI Light pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Light Sensor

The official I2C sensor for RGB color and gesture detection on ANAVI Ligth pHAT is APDS-9960.

Using 4 Dupont jumper wires connect APDS-9960 to one of the 5 I2C slots on ANAVI Light pHAT as follows:

| APDS-9960  | ANAVI Light pHAT |
| ---------- |:-------------- |
| VIN        | 3.3V           |
| GND        | GND            |
| SCL        | SCL            |
| SDA        | SDA            |

#### Temperature & Barometric Pressure Sensor

The official temperature and barometric pressure sensor for ANAVI Light pHAT is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 5 I2C slots on ANAVI Light pHAT as follows:

| BMP180   | ANAVI Light pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Assembly

You can assemble ANAVI Light pHAT and mount it on your Raspberry Pi with your bare hands and a screw driver following the steps below:

* Ensure that you Raspberry Pi is compatible with ANAVI Light pHAT.
* Power off your Raspberry Pi.
* Gently mount ANAVI Light pHAT on the 40 pin header of your Raspberry Pi.
* Using a screw driver connect 12V RGB LED strip to the terminal blocks.
* Add sensors to your ANAVI Light pHAT.
* Use 12V power supply with 2.1x.5.5 DC jack for powering the RGB LED strip and 5V USB power supply for the Raspberry Pi.
* Optionally, you may also mount two or four brass M2.5 standoffs to keep your Pi HAT snug on your Raspberry Pi while also keeping the two boards separated.
* That's all, now you are ready to go!

## Powering ANAVI Light pHAT

ANAVI Light pHAT requires two power supplies:

* 12V power supply for the RGB LED strip
* 5V power supply for the Raspberry Pi


ANAVI Light pHAT has been tested using 12V power supplies from SUNNY Computer Technology Europe such as [SYS1530-1212-W2E](https://www.sunny-euro.com/en/products/sys1530-1212-w2e-europe-2-1x5-5x11-s-2wc-1-4m-4-5ft). The output current depends on the leght of the RGB LED strip and the number of LEDs in it. ANAVI Light pHAT has been tested with power supplies with output current in the range from 1A to 5A. Using power supplies and RGB LED stip that requires higher output current than 5A is not recommended. Make sure that you are using a 12V power supply from a trusted supplier. Cheap, untested power supplies can be risky and unreliable.

It is recommended to use the [official Raspberry Pi Power Supply](https://www.raspberrypi.org/products/universal-power-supply/) or another 2.5A USB power supply from reputable retailer to power the Raspberry Pi.

---

# CHAPTER 3: Software

## Installation

In order to work correctly, ANAVI Light pHAT requires an up-to-date kernel, I2C to be enabled, and a few libraries to get started. After booting microSD card with **Raspbian**, open a terminal and follow the steps below:

* Ensure your APT package list is up-to-date:

```
sudo apt-get update
```

* Install additional applications, libraries and other tools needed by ANAVI Light pHAT

```
sudo apt-get install -y git i2c-tools vim
```

### Enable I2C

Follow the steps below to enable I2C which is required by the sensors for ANAVI Light pHAT

* Open a terminal or login remotely via SSH to your Raspberry Pi and type in the following command:

```
sudo raspi-config
```

* Select **Interfacing Options > I2C** and enable it.

* Reboot the board.

### Serial Debugging

Follow the steps below to enable serial debugging through USB to serial cable:

* Open a terminal or login remotely via SSH to your Raspberry Pi and type in the following command:

```
sudo raspi-config
```

* Select **Interfacing Options > Serial** and enable it.

* Reboot the board.

* Plug the USB to serial cable and connect your Raspberry Pi to your PC. The **RX** line of the cable should go to **TX** line of **UART** on ANAVI Light pHAT. The **TX** line of the cable should go to the **RX** line of **UART** on ANAVI Light pHAT. The **GND** wire should go to the **GND** line of **UART** on ANAVI Light pHAT.

* Type in the following command on your computer if you are using GNU/Linux distribution to access ANAVI Light pHAT. Alternatively if your OS is Microsoft Windows use [putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

The recommended USB to serial cable for ANAVI Light pHAT is [Olimex USB-Serial-Cable-F](https://www.olimex.com/Products/Components/Cables/USB-Serial-Cable/USB-Serial-Cable-F/).

## Examples

Sample applications written in Python and the C programming language are provided for ANAVI Light pHAT under MIT license in GitHub. All examples have been tested on **Raspbian**.

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

* Download the examples for ANAVI Light pHAT:

```
cd ~
git clone https://github.com/AnaviTechnology/anavi-examples.git
cd anavi-examples
```

### Controlling 12V RGB LED Strip from the Terminal

Execute the following commands to turn all colors of the 12V RGB LED strip using  pigpio:

```
sudo pigpiod
pigs p 9 255
pigs p 10 255
pigs p 11 255
```

### Sensors

It is mandatory to enable **I2C** to use most of the sensors supported by ANAVI Light pHAT.

#### PIR Motion Sensor

#### Color and Gesture Recognition Sensor (APDS-9960)

#### Temperature Sensor (BMP180)

Follow the steps below to use the BMP180 I2C temperature and barometric pressure sensor with ANAVI Light pHAT:

* Connect BMP180 to any of the I2C slots on ANAVI Light pHAT using male to female Duport jumper wire.

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

#### Humidity Sensor (HTU21D)

Follow the steps below to use the HTU21D I2C temperature and humidity sensor with ANAVI Light pHAT:

* Connect HTU21D to any of the I2C slots on ANAVI Light pHAT using male to female Duport jumper wire.

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

Follow the steps below to use the BH1750 I2C light sensor with ANAVI Light pHAT:

* Connect BH1750 to any of the I2C slots on ANAVI Light pHAT using male to female Dupont jumper wires.

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

The EEPROM of ANAVI Light pHAT contains DT overlay with description of the peripheral devices on the HAT. After adding Anavi to your Raspberry Pi and booting it you  should have some new filesystem nodes at */proc/device-tree/hat*:

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

The information provided in these filesystem nodes helps you to identify ANAVI Light pHAT vendor, version, product name, etc. For example:

```
pi@raspberrypi:~ $ cat /proc/device-tree/hat/product
ANAVI Light pHAT

pi@raspberrypi:~ $ cat /proc/device-tree/hat/vendor
ANAVI
```

More information about device trees, overlays and parameters are available at [the official Raspberry Pi documentation](https://www.raspberrypi.org/documentation/configuration/device-tree.md).

---

# CHAPTER 4: Home Assistant


---

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Light pHAT utilize the following pins on Raspberry Pi:

| Component    | Pins                                 |
| ----------------- |:------------------------------- |
| I2C               | 3, 5                            |
| EEPROM            | 27, 28                          |
| RGB LED connector | 19, 21, 23                      |
| PIR motion sensor | 7                               |
| UART              | 1, 8, 9, 10                     |

## I2C

The sensors that can be connected to ANAVI Light pHAT communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Light pHAT includes two 4.7kohm resistors labelled as R6 and R7. If for one reason or another you need to disable the I2C pullup resistors remove R6 and R7.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

#### May I use ANAVI Light pHAT with other operating systems?

Yes, you can use ANAVI Light pHAT with other GNU/Linux distributions and even other operating systems but some porting efforts might be required.

#### May I use other I2C sensors with ANAVI Light pHAT?

Yes, you can use other I2C sensors with ANAVI Light pHAT but you should take care for their drivers and software support.

#### May I use non-I2C sensors with ANAVI Light pHAT?

No.

#### Can I remotely control ANAVI Light pHAT from a web browser on my smartphone, tablet, or laptop?

Yes, you may install popular open source software for home automation on your Raspberry Pi such as [Home Assistant](https://home-assistant.io/) and integrate ANAVI Light pHAT as MQTT JSON component.

#### Is ANAVI Light pHAT software free and open source?

Yes, the official ANAVI Light pHAT software is free and open source. The examples are available under MIT license and the rest is available under GPLv3. Please contact us if you are working on a commercial product and you would like to use the software under alternative commercial license.

#### What 12 V RGB LED strip is included in the kits?

All kits include 1M 12V RGB LED strip with 30 LEDs (size 5050), IP 20 and power consumption of 7.2W.

#### What power supply do I need?
You need a 5 V USB power supply for Raspberry Pi and a 12 V power supply with a standard 2.1x5.5mm DC jack for your light strip. Select a 12 V power supply with sufficient output current and power depending on the length and specifications of your RGB LED strip.

#### Can I use ANAVI Light pHAT without 12V power supply?

No, the main feature for controlling RGB LED strip requires a 12V power supply.

#### Is there a recommended 12V power supply?

ANAVI Light pHAT has been tested using 12V power supplies from SUNNY Computer Technology Europe such as SYS1530-1212-W2E.

Make sure that you are using a 12V power supply from a trusted supplier. Cheap, untested power supplies can be risky and unreliable.

#### Why power supply is not included in any of the kits?

We were unable to source power supplies with universal plugs for US/EU/UK at an acceptable price, and power needs will vary based on application. Nowadays, 12 V power supplies with 2.1x5.5 mm DC jack are a commodity item, therefore you should be able to easily find a suitable unit online or at your local electronics store.

---

# CHAPTER 7: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 10 December 2017  | Initial        release      | All             | Leon Anavi      |

## ANAVI Light pHAT Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Prototype                                                    |
| 1.1     | Stable product                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
