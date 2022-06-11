---
fontfamily: dejavu
header-includes:
  - \exhyphenpenalty=10000
  - \hyphenpenalty=10000
  - \hypersetup{colorlinks=false,
            allbordercolors={0 0 0},
            pdfborderstyle={/S/U/W 1}}
---

# ANAVI Info uHAT

## DATASHEET

![ANAVI Info uHAT](images/anavi-info-uhat.jpg?raw=true "ANAVI Info uHAT")

**ANAVI Info uHAT** is a low-cost, open source Raspberry Pi add-on board with mini OLED display, 3 buttons, red and green indication LEDs as well as slots for various sensors. Each kit includes 0.96" yellow-blue I²C OLED display with resolution of 128x64 individual white OLED pixels. This is a low power consumption display that makes its own light abd therefore no additional backlight is required. Additional slots allows attaching various I²C sensors for temperature, humidity, light and barometric pressure as well as a UART pins for easy serial communication. ANAVI Info uHAT follows the official Raspberry Pi uHAT mechanical specification with a valid ID EEPROM.

![ANAVI Info uHAT on Raspberry Pi 400](images/anavi-info-uhat-rpi400.jpg?raw=true "ANAVI Info uHAT and Raspberry Pi 400")

## Features & Specifications

![ANAVI Info uHAT with sensors](images/anavi-info-uhat-sensors.jpg?raw=true "ANAVI Info uHAT with sensors")

* Replaceable 0.96" yellow-blue I²C OLED display
* Slots for up to 3 plug-and-play I²C sensors
* UART pins for serial communication
* Green and red indication LEDs
* 3 buttons
* Follows uHAT mechanical specification with a valid ID EEPROM
* Excellent software support, documentation, and open source examples

\pagebreak

![ANAVI Info uHAT](images/anavi-info-uhat-rpi4.jpg?raw=true "ANAVI Info uHAT with sensors")

ANAVI Info uHAT follows Raspberry Pi Foundation [HAT and uHAT design guides and requirements](https://github.com/raspberrypi/hats). ANAVI Info uHAT dimensions are 65x30mm with 3mm radius corners and 4 M2.5 mounting holes.

ANAVI Info uHAT is made in Plovdiv, Bulgaria, EU by [ANAVI Technology Ltd](https://anavi.technology/).

\pagebreak

## **Compatibility:**

ANAVI Info uHAT works with any Raspberry Pi single board computer model and version with 40-pin header, including Raspberry Pi 4 and Raspberry Pi 0 W.

![ANAVI Info uHAT for Raspberry Pi](images/anavi-info-uhat-sensors.jpg?raw=true "ANAVI Info uHAT for Raspberry Pi")

ANAVI Info uHAT officially supports the following sensor modules and peripherals:

* Mini 0.96" OLED I2C display
* HTU21D sensor for temperature and humidity
* BH1750 sensor for light
* BMP180 sensor for barometric pressure

*You may also attach any other I2C devices and sensors, but you will have to take care of their software integration.*

\pagebreak

## Kit Configurations

ANAVI Info uHAT is available in three do-it-yourself kits.



#### ANAVI Info uHAT Stater Kit (CS-ANAVI-INFO-1)

![ANAVI Info uHAT Starter Kit](images/anavi-info-uhat-starter.jpg?raw=true "ANAVI Info uHAT Starter Kit")

The perfect kit to get started. Includes one ANAVI Info uHAT (1) and one mini 0.96" OLED I2C display, yellow-blue (1).

\pagebreak

#### ANAVI Info uHAT Advanced Kit (CS-ANAVI-INFO-2)

![ANAVI Info uHAT Advanced Kit](images/anavi-info-uhat-advanced.jpg?raw=true "ANAVI Info uHAT Advanced Kit")

Take your project to the next level. Includes one ANAVI Info uHAT (1), one mini 0.96" OLED I2C display, yellow-blue (1), one temperature and humidity sensor (1) and one light sensor (1).

\pagebreak

#### ANAVI Info uHAT Developer Kit (CS-ANAVI-INFO-3)

![ANAVI Info uHAT Developer Kit](images/anavi-info-uhat-developer.jpg?raw=true "ANAVI Info uHAT Developer Kit")

Everything a developer needs! Includes ANAVI Info uHAT (1), one mini 0.96" OLED I2C display, yellow-blue (1), one temperature and humidity sensor (1), one light sensor (1), one barometric pressure and temperature sensor (1) and one USB-to-serial debug cable (1).

\pagebreak

## Hardware Schematics

ANAVI Info uHAT [schematics are available at GitHub](https://github.com/AnaviTechnology/anavi-gardening). It utilizes the following pins on Raspberry Pi:

| Component    | Raspberry Pi Pins               |
| ------------ |:------------------------------- |
| I2C          | 3, 5                            |
| EEPROM       | 27, 28                          |
| UART         | 1, 8, 9, 10                     |
| LED D1       | 29                              |
| LED D2       | 31                              |
| Button SW1   | 15                              |
| Button SW2   | 13                              |
| Button SW3   | 11                              |

## Resources

* [KiCad board schematics](https://github.com/AnaviTechnology/anavi-info-uhat)
* [Documentation](https://github.com/AnaviTechnology/anavi-docs/anavi-info-uhat)
* [Software](https://github.com/AnaviTechnology/anavi-examples/)
* For more information visit [https://anavi.technology/](https://anavi.technology/)
