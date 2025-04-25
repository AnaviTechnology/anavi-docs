# ANAVI Miracle Emitter

***A RISC-V-based development board ready for home automation and NeoPixel LEDs***

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
this license, visit https://creativecommons.org/licenses/by-sa/4.0/.

ANAVI Miracle Emitter hardware design is licensed under a Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Miracle Emitter. There are considered suitable only for ANAVI Miracle Emitter.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Miracle Emitter is a compact, open-source Wi-Fi and Bluetooth development board powered by the ESP32-C3 microcontroller running at 160 MHz with the open standard instruction set RISC-V architecture. It is designed to control an addressable 5 V LED strip such as NeoPixels, which can be powered via the onboard USB Type-C port or externally.

Compatible with popular LEDs like Neopixels, WS2811, WS2812B, and TM1809, Miracle Emitter also features a slot for a mini OLED I²C display, support for up to three additional I²C sensor modules, UART pins, and extra GPIO pins for external peripherals. This makes it ideal for developers, makers, students, and open-source enthusiasts interested in home automation.


ANAVI Miracle Emitter is designed with the free and open source electronics design automation suite [KiCAD](http://kicad.org/). No soldering is required. You can assemble ANAVI Miracle Emitter with your bare hands and a screwdriver.

## Features & Specifications

- **Module**: [Seeed Studio XIAO ESP32C3](https://wiki.seeedstudio.com/XIAO_ESP32C3_Getting_Started/)
- **Microcontroller**: 32-bit RISC-V ESP32-C3 @  160 MHz
- **Connectivity**: Wi-Fi IEEE 802.11 b/g/n and Bluetooth 5 (LE)
- **Peripheral Support**: Mini OLED display, GPIO pins, UART pins, button, three slots for I²C sensors
- **Power**: USB Type-C (max 5 V at 1 A, suitable for short runs of NeoPixels), 5 V screw terminal port 
- **Dimensions**: 32.77 x 65.29 mm (1.29 x 2.57 inches)

## Target Market

ANAVI Miracle Emitter is a certified open source hardware development board for customers interested in home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, open source supporters, students as well as web and/or mobile app developers. The main usage of the board is home automation.

## Board Version

Revision 1.0 of ANAVI Miracle Emitter was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

---

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Miracle Emitter is shipped in a protective bag. It must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Miracle Emitter the following items are required:

* NeoPixel LED strip or 2D panel, supported by the popular FastLED Arduino library (with three wires), such as WS2812, WS2812b, WS2811, TM1804, etc.
* 5V power supply.

## Supported Peripherals

ANAVI Miracle Emitter has a terminal block for attaching a NeoPixel LED strip or 2D panel, I2C slot for mini OLED display as well as up to 3 slots I2C sensors.

### LED strips

All addressable LED strips currently supported by the popular [FastLED Arduino library](http://fastled.io/) (with three wires) are supported by ANAVI Miracle Emitter, including WS2812, WS2812b, WS2811, and TM1804. To prevent spikes, a 300 to 500 Ohm choke resistor might be required at the data wire. Some LED strips, including those provided with our kits, already have this resistor built-in.

Strips provided in ANAVI Miracle Emitter kits are WS2812B strips with ten LEDs each, appropriate connectors, and built-in 470 Ohm choke resistor.

You can attach 1 or 2 addressable LED strips to ANAVI Miracle Emitter.  Both attached strips must be of the same kind.

Non-addressable LED strips are not appropriate for ANAVI Miracle Emitter. If you need to control 12V non-addressable RGB LED strip have a look at our other open source product ANAVI Light Controller.

### Sensors

You can attach various I2C sensor modules to ANAVI Miracle Emitter. The officially supported I2C add-on sensor modules are for:

* Light (BH1750)
* Temperature and humidity (HTU21D)
* Color and gesture recognition (APDS-9960)
* Temperature and barometric pressure (BMP180)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Light Sensor

The official light I2C sensor for ANAVI Miracle Emitter is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 3 I2C slots on ANAVI Miracle Emitter as follows:

| BH1750   | ANAVI Miracle Emitter |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |


#### I2C External Temperature & Humidity Sensor

The official external temperature and humidity add-on sensor for ANAVI Miracle Emitter is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 3 I2C slots on ANAVI Miracle Emitter as follows:

| HTU21    | ANAVI Miracle Emitter |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Color & Gesture Recognition Sensor

The official I2C sensor for RGB color and gesture detection on ANAVI Ligth pHAT is APDS-9960.

Using 4 Dupont jumper wires connect APDS-9960 to one of the 3 I2C slots on ANAVI Miracle Emitter as follows:

| APDS-9960  | ANAVI Miracle Emitter |
| ---------- |:-------------- |
| VIN        | 3.3V           |
| GND        | GND            |
| SCL        | SCL            |
| SDA        | SDA            |

#### Temperature & Barometric Pressure Sensor

The official temperature and barometric pressure sensor for ANAVI Miracle Emitter is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 3 I2C slots on ANAVI Miracle Emitter as follows:

| BMP180   | ANAVI Miracle Emitter |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Assembly

You can assemble ANAVI Miracle Emitter with your bare hands and a screw driver following the steps below:

* Add addressable LED strips to your ANAVI Miracle Emitter.
* Optionally, add I2C sensor modules.
* Optionally, add I2C mini OLED display.
* Optionally, you may also assemble the simple acrylic case included in the advanced and developer kit by removing the protective film and mounting screws.
* Use appropriate 5V power supply.

## Configure ANAVI Miracle Emitter

The default software of ANAVI Miracle Emitter has a captive portal which guides you through the configurations. As you see in the video you have to select your WiFi network and enter a password if it is not open.

Our open source software relies on the machine to machine communication protocol MQTT to report data from the sensors. You can connect to your own MQTT broker or just leave the default configurations and connect to the public broker as shown in the video.

Recent versions of the firmware support [Home Assistant MQTT Discovery](https://www.home-assistant.io/docs/mqtt/discovery/) which makes it very convenient to add ANAVI Miracle Emitter to Home Assistant.  For this to work, you need to enter the sensor name (such as "Master Bedroom") that will be used for this Thermometer on the setup screen.  See Chapter 5 for more details.

Recent versions of the firmware support Over-the-Air upgrades of the software.  To enable this, you need to specify the IP address or DNS domain name of a web server that hosts the firmware. See Chapter 3 for more details.

It very important to copy the machine ID. Later it is needed to identify your device.

When you are ready just click save. If you have entered valid credentials in a moment ANAVI Miracle Emitter will connect to your WiFi network and the configured MQTT broker. This way the configuration is complete and ANAVI Miracle Emitter will turn off its temporary WiFi access point. After that your device, for example smartphone as in the video, will automatically connect again to your WiFi network.

To verify that ANAVI Miracle Emitter is up and running open a modern web browser and visit demo.anavi.technology. Enter your machine ID. Check the advanced settings only if you are not using the default public MQTT broker. Click connect.

## Reset to Factory Defaults

If you decide to change the settings of ANAVI Miracle Emitter you need to reset the board and configure it again.

To reset ANAVI Miracle Emitter press the button and hold it for approximately 6 seconds until the red light stops blinking. After resetting the board there will be a steady red light that indicates that the temporary WiFi access point is on and you can proceed with the configuration again. The reset button works once the ANAVI Miracle Emitter has successfully connected to a WiFi network. If you are running a recent enough version of the firmware, it also works for 2 seconds after you power on the device (while the red LED is blinking quickly).

---

# CHAPTER 3: Software Development

## Default Firmware

By default ANAVI Miracle Emitter comes with [this free and open source Arduino sketch](https://github.com/AnaviTechnology/anavi-miracle-emitter-sw).

## Setting up the Arduino IDE

1. Install the Arduino IDE following the instructions from from https://www.arduino.cc/en/Main/Software

2. Add the ESP32 board package: In **File > Preferences** input `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json` into the Additional Board Manager URLs field.

3. In **Tools > Board ... > Boards manager** find and add the **ESP32** package. Now "XIAO ESP32C3" should be an option in the **Tools > Boards** menu.

4. In **Tools > Flash Size:** select **4M (1M SPIFFS)**

5. Go to **Sketch > Include Library > Manage Libraries...** and include the following dependencies of the default firmware for ANAVI Miracle Emitter:

* WiFiManager by tzapu (version 0.12.0)
* ArduinoJson by Benoit Blanchon (version 6.11.2)
* PubSubClient by Nick O'Leary (version 2.7.0)
* Adafruit HTU21DF Library by Adafruit (version 1.0.1)
* Adafruit APDS9960 Library by Adafruit (version 1.0.5)
* U8g2 by oliver (version 2.23.18)
* Adafruit Unified Sensor by Adafruit (version 1.0.2)
* Adafruit BMP085 Unified (version 1.0.0)
* FastLED (version 3.2.6)

*Note: Issues might be experienced if using different versions of the libraries.*

## Flashing Custom Firmware

Follow the steps below to compile and flash custom firmware on ANAVI Miracle Emitter from Arduino IDE:

1. To flash the firmware from Arduino IDE select Tools > Generic ESP8266 Module (Flash mode: DIO, Flash frequency: 40MHz, CPU frequency: 80MHz, Flash size: 4M, Debug port: Disabled, Debug level: None, Reset method: ck, Upload speed: 115200, Port: /dev/ttyUSB0). Set the flash size to 4M (1M SPIFFS). You might need to adjust the port if your USB to serial debug cable is connected on a different port.

2. After that press load an Arduino sketch. [A simple blinking LED example is available at GitHub](https://github.com/AnaviTechnology/anavi-examples/blob/master/anavi-light-controller/anavi-blinking-led/anavi-blinking-led.ino)

3. In Arudino IDE click Verify/Compile (Ctrl+R)

4. Connect ANAVI Miracle Emitter to the USB to serial debug board: GND to GND, TX cable to RX of ANAVI Miracle Emitter and RX cable to TX of ANAVI Miracle Emitter.

5. In Arudino IDE click Upload (Ctrl+U)

6. Press and **hold** the RESET button on ANAVI Miracle Emitter. Plug the 5V power supply in the jack of ANAVI Miracle Emitter (without releasing the RESET button).

7. In Arduino IDE verify that the upload has been started. Hold RESET until the upload completes.

The output in Arduino IDE for successful flashing is:

```
Archiving built core (caching) in: /tmp/arduino_cache_954939/core/core_esp8266_esp8266_generic_CpuFrequency_80,FlashFreq_40,FlashMode_dio,UploadSpeed_115200,FlashSize_512K64,ResetMethod_ck,Debug_Disabled,DebugLevel_None_____1c2aa2b3da66da225b39c9bfab6531e5.a
Sketch uses 224949 bytes (51%) of program storage space. Maximum is 434160 bytes.
Global variables use 31756 bytes (38%) of dynamic memory, leaving 50164 bytes for local variables. Maximum is 81920 bytes.
Uploading 229104 bytes from /tmp/arduino_build_904122/anavi-blinking-led.ino.bin to flash at 0x00000000
................................................................................ [ 35% ]
................................................................................ [ 71% ]
................................................................                 [ 100% ]
```

If you have flashed the blinking LED example, D1 on ANAVI Miracle Emitter with start blinking.

Please have a look at [the YouTube video that shows the exact steps for compiling and uploading an Arduino sketch to ANAVI Miracle Emitter](https://www.youtube.com/watch?v=HMIkPuz0ZJs).

**Note:** you have to be quick between step 5 and 6. Remember to press and **hold** RESET until the upload completes.

---

# CHAPTER 4: Temperature scale: Celsius vs Fahrenheit

The temperature scale of the default open source firmware of ANAVI Miracle Emitter can be configured at the initial setup of the device. By default it is set to Celsius. Manually type in **fahrenheit** to change it.

After the initial setup the temperature scale can be still changed with a single MQTT message with topic **cmnd/<machine-id>/tempformat** (where **<machine-id>** must be replaced with the
unique value for your board) and a JSON payload:

```
{ "scale": "fahrenheit" }
```

To switch back to Celsius, send the same message and just edit the JSON payload by changing **fahrenheit** to **celsius**.

For example, if using the mosquitto_pub application from a command-line terminal and machine id 11111111111111111111111111111111:

```
mosquitto_pub -h iot.eclipse.org -d -p 1883 -t
"cmnd/11111111111111111111111111111111/tempformat" -m '{ "scale":
"fahrenheit" }'
```

# CHAPTER 5: Home Automation Platforms

This chapter provide guidelines how to connect ANAVI Miracle Emitter to popular home automation platforms like Home Assistant, OpenHab 2, Thinkspeak, etc.

## Home Assistant

[Home Assistant](https://home-assistant.io/) is a free and open-source home automation platform running on Python 3 with more than 1200 components for integration with popular Internet of Things.

ANAVI Miracle Emitter can be easily integrated in Home Assistant using the component [MQTT Light Component](https://www.home-assistant.io/integrations/light.mqtt/). This component supports JSON in the payload of the MQTT messages. To use it, in **configuration.yaml** specify MQTT broker and register the sensor with the corresponding MQTT topic, for example:

* Configure MQTT broker:

```
mqtt:
  broker: 127.0.0.1
```

* Register the MQTT component:

```

```

MQTT Discovery can simplify this process.  To use this, specify this in **configuration.yaml**:

```
mqtt:
  broker: 127.0.0.1
  discovery: true
  discovery_prefix: homeassistant
```

---

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Miracle Emitter relies on ESP8266 (ESP-12 module) and utilizes the following pins:

| Component           | Pins                            |  Arduino Pin ID |
| ------------------- |:------------------------------- |-----------------|
| I2C                 | 6, 7                            | D4, D5          |
| Indication LED (D1) | 3                               | D3              |
| LED data            | 10                              | D10             |
| Reset button (SW1)  | 8                               | D8              |
| Extra GPIO          | 2, 3, 4                         | D0, D1, D2      |
| UART                | 20, 21                          | D7, D6          |

## I2C

The sensors that can be connected to ANAVI Miracle Emitter communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Miracle Emitter includes two 4.7kohm resistors labelled as R2 and R3. If for one reason or another you need to disable the I2C pullup resistors remove R2 and R3.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

#### Why isn't a power supply included?

We were unable to source power supplies with universal plugs for the US/EU/UK at an acceptable. Nowadays, 5V power supplies with a USB-C connector are a commodity item because of most smartphone and tables, so you should be able to easily find a suitable unit online or at your local electronics store.

#### Which addressable LED strips are included in the kits?

The strip provided in ANAVI Miracle Emitter kits is 5V WS2812B strip with ten NeoPixel LEDs each and an appropriate connector.

#### Is ANAVI Miracle Emitter an open source project?

Yes, ANAVI Miracle Emitter is an open source hardware project powered and created with free and open source software. The hardware designs are available at [GitHub under CC BY-SA 4.0 license](https://github.com/AnaviTechnology/anavi-miracle-emitter). All schematics, documents, and source code files are available at [our GitHub repositories](https://github.com/AnaviTechnology/).

#### Does ANAVI Miracle Emitter use the ESP32-C3?

Yes, ANAVI Miracle Emitter is based on the ESP32-C3.

#### Is ANAVI Miracle Emitter compatible with Arduino IDE?

Yes, ANAVI Miracle Emitter is compatible with Arduino IDE. You can easily upload your own Arduino sketches to the board.

#### How can I get involved and help?

Buy any of the available perks, get your hands on the ANAVI Miracle Emitter, contribute to our GitHub repositories, and become part of our open source community!


---

# CHAPTER 7: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 20 April 2025     | Initial release             | All             | Leon Anavi      |

## ANAVI Miracle Emitter Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable product                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
