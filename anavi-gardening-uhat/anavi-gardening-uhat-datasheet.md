---
fontfamily: dejavu
header-includes:
  - \exhyphenpenalty=10000
  - \hyphenpenalty=10000
  - \hypersetup{colorlinks=false,
            allbordercolors={0 0 0},
            pdfborderstyle={/S/U/W 1}}
---

# ANAVI Gardening uHAT

## DATASHEET

![ANAVI Gardening uHAT](images/anavi-gardening-uhat.jpg?raw=true "ANAVI Gardening uHAT")

**ANAVI Gardening uHAT** is a low-cost, open source Raspberry Pi add-on board that helps you develop smart solutions for monitoring and growing plants.

ANAVI Gardening uHAT supports multiple sensors for soil moisture, temperature, humidity,
barometric pressure, and light. No soldering is required. Getting started is easy. You just plug it into a Raspberry Pi with your bare hands (no tools needed) and follow the steps from the user manual.

## Features & Specifications

![ANAVI Gardening uHAT with sensors](images/anavi-gardening-uhat-sensors.jpg?raw=true "ANAVI Gardening uHAT with sensors")

* Slots for up to two capacitive soil moisture sensors
* Slot for waterproof temperature sensor
* Slots for up to two plug-and-play I2C sensors
* UART pins for serial communication
* GPIO pins for controlling irrigation systems and peripherals
* Green and red indication LEDs
* Microchip MCP3002 Analog-to-Digital Converter (ADC)
* Follows uHAT mechanical specification with a valid ID EEPROM
* Excellent software support, documentation, and open source examples

\pagebreak

Each kit contains two capacitive soil moisture sensors operating at 5V with analog output in the range 0 ~ 3V and made of corrosion resistant material.

![Capacitive Soil Moisture Sensor](images/anavi-gardening-uhat-capacitive-soil-moisture-sensor.jpg?raw=true "Capacitive Soil Moisture Sensor")

ANAVI Gardening uHAT follows Raspberry Pi Foundation [HAT and uHAT design guides and requirements](https://github.com/raspberrypi/hats). ANAVI Gardening uHAT dimensions are 65x30mm with 3mm radius corners and 4 M2.5 mounting holes.

ANAVI Gardening uHAT is made in Plovdiv, Bulgaria, EU by [ANAVI Technology Ltd](https://anavi.technology/).

\pagebreak

## **Compatibility:**

ANAVI Gardening uHAT works with any Raspberry Pi single board computer model and version with 40-pin header, including Raspberry Pi 4 and Raspberry Pi 0 W.

![ANAVI Gardening uHAT for Raspberry Pi](images/anavi-gardening-uhat-sensors.jpg?raw=true "ANAVI Gardening uHAT for Raspberry Pi")

ANAVI Gardening uHAT officially supports the following sensor modules with:

* Capacitive soil moisture sensors
* Waterproof DS18B20 temperature sensor
* HTU21D sensor for temperature and humidity
* BH1750 sensor for light
* BMP180 sensor for barometric pressure

*You may also attach any other I2C devices and sensors, but you will have to take care of their software integration.*

\pagebreak

## Kit Configurations

ANAVI Gardening uHAT is available in three do-it-yourself kits.

|                                      | Starter Kit  | Advanced Kit | Developer Kit |
| ------------------------------------ | ------------ | ------------ | ------------- |
| **ANAVI Gardening uHAT**             | Yes          | Yes          | Yes           |
| **Capacitive soil moisture sensors** | Yes          | Yes          | Yes           |
| **Light sensor**                     | No           | Yes          | Yes           |
| **Temperature and humidity sensor**  | No           | Yes          | Yes           |
| **Waterproof temperature sensor**    | No           | No           | Yes           |
| **USB to serial debug cable**        | No           | No           | Yes           |

#### ANAVI Gardening uHAT Stater Kit (CS-ANAVI-GRDN-1)

![ANAVI Gardening uHAT Starter Kit](images/anavi-gardening-uhat-starter.jpg?raw=true "ANAVI Gardening uHAT Starter Kit")

The perfect kit to get started with gardening. Includes one ANAVI Gardening uHAT (1) and two capacitive soil moisture sensors (2).

\pagebreak

#### ANAVI Gardening uHAT Advanced Kit (CS-ANAVI-GRDN-2)

![ANAVI Gardening uHAT Advanced Kit](images/anavi-gardening-uhat-advanced.jpg?raw=true "ANAVI Gardening uHAT Advanced Kit")

Take your gardening skills to next level. Includes one ANAVI Gardening uHAT, two capacitive soil moisture sensors (2), I2C sensor for light (1), I2C sensor for temperature and humidity (1).

\pagebreak

#### ANAVI Gardening uHAT Developer Kit (CS-ANAVI-GRDN-3)

![ANAVI Gardening uHAT Developer Kit](images/anavi-gardening-uhat-developer.jpg?raw=true "ANAVI Gardening uHAT Developer Kit")

Everything a developer needs to master gardening! Includes one ANAVI Gardening uHAT, two capacitive soil moisture sensors (2), one waterproof DS18B20 temperature sensor (1), I2C sensor for light (1), I2C sensor for temperature and humidity (1). Also comes with one USB-to-serial debug cable (1).

\pagebreak

## Hardware Schematics

ANAVI Gardening uHAT [schematics are available at GitHub](https://github.com/AnaviTechnology/anavi-gardening). It utilizes the following pins on Raspberry Pi:

| Feature             | Raspberry Pins                  |
| ------------------- |:------------------------------- |
| LED D1              | GPIO22                          |
| LED D2              | GPIO23                          |
| 1-wire terminal     | GPIO4                           |
| MCP3002 ADC         | GPIO10, GPIO9, GPIO11, GPIO8    |
| UART                | GPIO14, GPIO15                  |
| I2C slots           | GPIO2, GPIO3                    |
| I2C EEPROM          | ID_SC, ID_SD                    |

## Resources

* [KiCad board schematics](https://github.com/AnaviTechnology/anavi-gardening)
* [Documentation](https://github.com/AnaviTechnology/anavi-docs/anavi-gardening-uhat)
* [Software](https://github.com/AnaviTechnology/anavi-examples/tree/master/anavi-gardening-uhat)
* For more information visit [https://anavi.technology/](https://anavi.technology/)
