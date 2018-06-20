# ANAVI Light Controller

**The open source hardware development board with WiFi for controlling 12V RGB LED strip**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
this license, visit https://creativecommons.org/licenses/by-sa/4.0/.

ANAVI Light Controller hardware design is licensed under a Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Light Controller. There are considered suitable only for ANAVI Light Controller.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Light Controller is a certified open source hardware WiFi device for controlling a 12 V RGB LED strip. It also supports sensors for light, temperature, humidity, and gesture recognition.

ANAVI Light Controller is fully compliant with the popular open source platform, Home Assistant. That means that when paired with Amazon Alexa, the device can be turned on and off with voice commands.

ANAVI Light Controller is designed with the free and open source electronics design automation suite [KiCAD](http://kicad-pcb.org/). No soldering is required. You can assemble ANAVI Light Controller with your bare hands and a screwdriver to attach 12V RGB LED strip.

## Features

ANAVI Light Controller includes:

* Terminal block for attaching 12 V RGB LED strip
* Slots for up to three plug and play I2C sensor modules
* Slot for PIR motion sensor
* UART pins for debugging
* EEPROM with board manufacturer information and a device tree fragment

## Target Market

ANAVI Light Controller is a certified open source hardware development board for customers interested in home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, open source supporters, students as well as web and/or mobile app developers. The main usage of the board is home automation of lights with RGB LED strip, sensors and the popular open source software Home Assistant.

## Board Version

Revision 1.3 of ANAVI Light Controller was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Light Controller is shipped in a protective bag. It must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Light Controller the following items are required:

* 12V RGB LED strip
* 12V power supply

It is recommended to use 1A (1000mA) or higher power supply.

## Supported Peripherals

ANAVI Light Controller has a terminal block for attaching 12V RGB LED strip, a slot for attaching PIR motion sensor as well as up to 3 slots I2C sensors.

### Sensors

ANAVI Light Controller supports PIR motion sensor. The officially supported I2C sensor modules are for:

* Light (BH1750)
* Temperature and humidity (HTU21D)
* Color and gesture recognition (APDS-9960)
* Temperature and barometric pressure (BMP180)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Light Sensor

The official light I2C sensor for ANAVI Light Controller is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 5 I2C slots on ANAVI Light Controller as follows:

| BH1750   | ANAVI Light Controller |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |


#### Temperature & Humidity Sensor

The official temperature and humidity sensor for ANAVI Light Controller is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 5 I2C slots on ANAVI Light Controller as follows:

| HTU21    | ANAVI Light Controller |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Light Sensor

The official I2C sensor for RGB color and gesture detection on ANAVI Ligth pHAT is APDS-9960.

Using 4 Dupont jumper wires connect APDS-9960 to one of the 5 I2C slots on ANAVI Light Controller as follows:

| APDS-9960  | ANAVI Light Controller |
| ---------- |:-------------- |
| VIN        | 3.3V           |
| GND        | GND            |
| SCL        | SCL            |
| SDA        | SDA            |

#### Temperature & Barometric Pressure Sensor

The official temperature and barometric pressure sensor for ANAVI Light Controller is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 5 I2C slots on ANAVI Light Controller as follows:

| BMP180   | ANAVI Light Controller |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Assembly

You can assemble ANAVI Light Controller with your bare hands and a screw driver following the steps below:

* Using a screw driver connect 12V RGB LED strip to the terminal blocks.
* Add sensors to your ANAVI Light Controller.
* Optionally, you may also assemble the simple acrylic case by removing the protective film and mounting all standoffs and screws. 
* Insert the 2.1x.5.5 DC jack of the power supply in ANAVI Light Controller to turn on the board.

## Powering ANAVI Light Controller

ANAVI Light Controller requires 12V power supply for the RGB LED strip.


ANAVI Light Controller has been tested using 12V power supplies from SUNNY Computer Technology Europe such as [SYS1530-1212-W2E](https://www.sunny-euro.com/en/products/sys1530-1212-w2e-europe-2-1x5-5x11-s-2wc-1-4m-4-5ft). The output current depends on the leght of the RGB LED strip and the number of LEDs in it. ANAVI Light Controller has been tested with power supplies with output current in the range from 1A to 5A. Using power supplies and RGB LED stip that requires higher output current than 5A is not recommended. Make sure that you are using a 12V power supply from a trusted supplier. Cheap, untested power supplies can be risky and unreliable.

---

# CHAPTER 3: Software Development

## 

## Examples

# CHAPTER 4: Home Assistant


---

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Light Controller relies on ESP8266 (ESP-12 module) and utilizes the following pins:

| Component    | Pins                                   |
| ------------------- |:------------------------------- |
| I2C                 | 13, 14                          |
| RGB LED connector   | 5, 6, 7                         |
| Indication LED (D1) | 7                               |
| Reset button (SW1)  | 12                              |
| UART                | 15, 16                          |

## I2C

The sensors that can be connected to ANAVI Light Controller communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Light Controller includes two 4.7kohm resistors labelled as R6 and R7. If for one reason or another you need to disable the I2C pullup resistors remove R6 and R7.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

---

# CHAPTER 7: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 20 June 2018      | Initial        release      | All             | Leon Anavi      |

## ANAVI Light Controller Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.1     | Prototype Alpha                                              |
| 1.2     | Prototype Beta                                               |
| 1.3     | Stable product                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTech/), [Twitter](https://twitter.com/AnaviTech) or [email](mailto:info@anavi.technology).

---
