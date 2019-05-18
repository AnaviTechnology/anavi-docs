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

## Features & Specifications

* **CPU:** Tensilica L106 32-bit processor
* **Connectivity:** WiFi 802.11 b/g/n
* **Input voltage:** 12 V
* **Peripherals:** Terminal block for 12 V RGB LED strip, UART pins, button, three slots for sensors
* **Compatibility:** Arduino IDE, Home Assistant, MQTT, and any modern web browser
* **Certification:** Open Source Hardware Association (OSHWA) BG000005
* **Dimensions:** 75 mm x 40 mm

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

## Configure ANAVI Light Controller

[Video tutorial for getting started with ANAVI Light Controller](https://www.youtube.com/watch?v=Y_81CuuGm0Y)

Turn on ANAVI Light Controller by plugging an appropriate 12V power supply. As soon as the board is turned on for the very first time it will create a temporary WiFi access point. Connect to it from your computer, smartphone or tablet.

The default software of ANAVI Light Controller has a captive portal which guides you through the configurations. As you see in the video you have to select your WiFi network and enter a password if it is not open.

Our open source software relies on the machine to machine communication protocol MQTT to control the lights and to report data from the sensors. You can connect to your own MQTT broker or just leave the default configurations and connect to the public broker as shown in the video.

It very important to copy the machine ID. Later it is needed to identify your device.

When you are ready just click save. If you have entered valid credentials in a moment ANAVI Light Controller will connect to your WiFi network and the configured MQTT broker. This way the configuration is complete and ANAVI Light Controller will turn off its temporary WiFi access point. After that your device, for example smartphone as in the video, will automatically connect again to your WiFi network.

To verify that ANAVI Light Controller is up and running open a modern web browser and visit demo.anavi.technology. Enter your machine ID. Check the advanced settings only if you are not using the default public MQTT broker. Click connect.

From this web page you can turn on and off as well as to change the colors of the RGB LED strip.

The strip can also be controlled from the command line with a client such as [mosquitto_pub](https://mosquitto.org/man/mosquitto_pub-1.html). For example:

    mosquitto_pub -h iot.eclipse.org -d -t "cmnd/####/color" -m '{"color":{ "r":0, "g":255, "b":0 }}'
    mosquitto_pub -h iot.eclipse.org -d -t "cmnd/####/color" -m '{"brightness":128}'

with '####' replaced with the machine ID and color and brightness values between 0 and 256.


## Reset to Factory Defaults

If you decide to change the settings of ANAVI Light Controller you need to reset the board and configure it again.

To reset ANAVI Light Controller press the button and hold it for 10 seconds until the red light is blinking. After resetting the board there will be a steady red light that indicates that the temporary WiFi access point is on and you can proceed with the configuration again.

---

# CHAPTER 3: Software Development

## Default Firmware

By default ANAVI Light Controller comes with [this free and open source Arduino sketch](https://github.com/AnaviTechnology/anavi-light-controller-sw).

## USB to UART Module

For uploading firmware to ANAVI Light Controller you need USB to UART module. All kits include CP2102 which out of the box on GNU/Linux distributions. Drivers for MS Windows and Mac OS X are [available at silabs.com](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers).

## Setting up the Arduino IDE

1. Install the Arduino IDE following the instructions from from https://www.arduino.cc/en/Main/Software

2. Add the ESP8266 board package: In **File > Preferences** input http://arduino.esp8266.com/stable/package_esp8266com_index.json into the Additional Board Manager URLs field.

3. In **Tools > Board ... > Boards manager** find and add the **ESP8266** package. Now "Generic ESP8266" should be an option in the **Tools > Boards** menu.

4. Go to **Sketch > Include Library > Manage Libraries...** and include the following dependencies of the default firmware for ANAVI Light Controller:

* WiFiManager by tzapu
* ArduinoJson by Benoit Blanchon
* PubSubClient by Nick O'Leary
* Adafruit HTU21DF Library by Adafruit
* Adafruit APDS9960 Library by Adafruit

## Flashing Custom Firmware

Follow the steps below to compile and flash custom firmware on ANAVI Light Controller from Arduino IDE:

1. To flash the firmware from Arduino IDE select Tools > Generic ESP8266 Module
and set the following parameters.

  * **Flash mode**: DIO
  * **Flash frequency**: 40MHz
  * **CPU frequency**: 80MHz
  * **Flash size**: 512K
  * **Debug port**: Disabled
  * **Debug level**: None
  * **Reset method**: ck
  * **Upload speed**: 115200
  * **Port**: /dev/ttyUSB0  
  You might need to adjust the port if your USB to serial debug cable is connected on a different port.

2. After that press load an Arduino sketch. [A simple blinking LED example is available at GitHub](https://github.com/AnaviTechnology/anavi-examples/blob/master/anavi-light-controller/anavi-blinking-led/anavi-blinking-led.ino)

3. In Arduino IDE click Verify/Compile (Ctrl+R)

4. Connect ANAVI Light Controller to the USB to serial debug board: GND to GND, TX cable to RX of ANAVI Light Controller and RX cable to TX of ANAVI Light Controller.

5. In Arduino IDE click Upload (Ctrl+U)

6. Press and **hold** SW1 on ANAVI Light Controller. Plug the 12V power supply in the jack of ANAVI Light Controller (without releasing SW1).

7. In Arduino IDE verify that the upload has been started. Then you can release SW1 on ANAVI Light Controller (the upload will not be interrupted and it will continue once it has started).

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

If you have flashed the blinking LED example, D1 on ANAVI Light Controller with start blinking.

**Note:** you have to be quick between step 5 and 6. Remember to press and **hold** SW1 until the upload starts.

# CHAPTER 4: Home Assistant


---

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Light Controller relies on ESP8266 (ESP-12 module) and utilizes the following pins:

| Component           | Pins                            |  Arduino Pin ID |
| ------------------- |:------------------------------- |-----------------|
| I2C                 | 13, 14                          |                 |  
| RGB LED connector   | 5, 6, 7                         | 12, 13, 14      |
| Indication LED (D1) | 7                               | 16              |
| Reset button (SW1)  | 12                              | 0               |
| UART                | 15, 16                          |                 |

## I2C

The sensors that can be connected to ANAVI Light Controller communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Light Controller includes two 4.7kohm resistors labelled as R6 and R7. If for one reason or another you need to disable the I2C pullup resistors remove R6 and R7.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)


#### Which 12 V RGB LED strip is included in the kits?

All kits include a one meter 12 V RGB LED strip with 30 LEDs (size 5050), IP 20, and power consumption of 7.2W.

#### What power supply do I need?

You need a 12 V power supply with a standard 2.1x5.5 mm DC jack for your light strip. Select a power supply with sufficient output current and power depending on the length and specifications of your RGB LED strip.

#### Is there a recommended 12 V power supply?

ANAVI Light Controller has been tested using 12 V power supplies from SUNNY Computer Technology Europe such as [SYS1530-1212-W2E](https://www.sunny-euro.com/en/products/sys1530-1212-w2e-europe-2-1x5-5x11-s-2wc-1-4m-4-5ft).

Make sure that you are using a 12 V power supply from a trusted supplier. Cheap, untested power supplies can be risky and unreliable.

#### Why isn't a power supply included?

We were unable to source power supplies with universal plugs for the US/EU/UK at an acceptable price and, further, power needs will vary based on application. Nowadays, 12 V power supplies with a 2.1x5.5 mm DC jack are a commodity item, so you should be able to easily find a suitable unit online or at your local electronics store.

#### Can I remotely control ANAVI Light Controller from a web browser on my smartphone, tablet, or laptop?

Yes, you can use our [demo website](http://demo.anavi.technology/) or easily integrate ANAVI Light Controller in your instance of the popular open source platform [Home Assistant](https://home-assistant.io/) as an MQTT JSON Light component.

#### Is ANAVI Light Controller an open source project?

Yes, ANAVI Light Controller is an open source hardware project powered and created with free and open source software. The hardware designs are available at [GitHub under CC BY-SA 4.0 license](https://github.com/AnaviTech/anavi-light-controller). All schematics, documents, and source code files are available at [our GitHub repositories](https://github.com/AnaviTech/).

#### Is ANAVI Light Controller certified?

Yes, ANAVI Light Controller revision 1.3 has been [certified by the Open Source Hardware Association under UID BG000005](http://certificate.oshwa.org/certification-directory/).

#### Does ANAVI Light Controller use the ESP8266?

Yes, ANAVI Light Controller is based on the ESP8266.

#### Can I flash different firmware to ANAVI Light Controller?

Yes, using a USB to serial cable, you can flash custom firmware built from your own source code.

#### Is ANAVI Light Controller compatible with Arduino IDE?

Yes, ANAVI Light Controller is compatible with Arduino IDE. You can easily upload your own Arduino sketches to the board.

#### How can I get involved and help?

Buy any of the available perks, get your hands on the ANAVI Light Controller, contribute to our GitHub repositories, and become part of our open source community!


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
