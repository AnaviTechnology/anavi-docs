# ANAVI Thermometer

**An ESP8266-powered, open source, Wi-Fi dev board with temperature and humidity sensors**

---

# DISCLAIMER

ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied
or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
this license, visit https://creativecommons.org/licenses/by-sa/4.0/.

ANAVI Thermometer hardware design is licensed under a Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Thermometer. There are considered suitable only for ANAVI Thermometer.

---

# CHAPTER 1: Overview

## Introduction

ANAVI Thermometer is an open source hardware, Wi-Fi development board for measuring temperature that’s powered by an ESP8266 processor. It comes with a built-in DHT22/AM2302 temperature and humidity sensor and has slots for a mini OLED display, waterproof DS18B20 temperature sensor, and empty slots for up to three additional I2C sensor modules. All these features make ANAVI Thermometer appropriate for developers, makers, students and open source enthusiasts interested in home automation.

ANAVI Thermometer is designed with the free and open source electronics design automation suite [KiCAD](http://kicad-pcb.org/). No soldering is required. You can assemble ANAVI Thermometer with your bare hands and a screwdriver.

## Features & Specifications

* **CPU**: Tensilica L106 32-bit processor (ESP8266)
* **Connectivity**: WiFi 802.11 b/g/n
* **Build-in sensor**: temperature and humidity (AM2302/DHT22)
* **Peripherals**: Mini OLED display, terminal block DS18B20 waterproof temperature sensor, UART pins, button, three slots for I2C sensors
* **Compatibility**: Arduino IDE, PlatformIO, Home Assistant, MQTT, and any modern web browser
* **Certification**: Open Source Hardware Association (OSHWA) BG000017
* **Dimensions**: 75 mm x 40 mm
* **Upgradable**: The software can be upgraded, either using an USB to UART module, or (if configured) over-the-air

## Target Market

ANAVI Thermometer is a certified open source hardware development board for customers interested in home automation, software development and Internet of Things. The option to attach a waterproof DS18B20 sensor makes it coconvenient for measuring temperature in fish tanks and liquids. The board is appropriate for embedded programming enthusiasts, open source supporters, students as well as web and/or mobile app developers. The main usage of the board is home automation.

## Board Version

Revision 1.0 of ANAVI Thermometer was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

---

# CHAPTER 2: Getting Started

## Electrostatic Warning

ANAVI Thermometer is shipped in a protective bag. It must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

## Requirements

In order to setup ANAVI Thermometer the following items are required:

* 5V power supply with microUSB

It is recommended to use 1A (1000mA) or higher power supply.

## Supported Peripherals

ANAVI Thermometer has a terminal block for attaching DS18B20 waterproof temperature sensor, I2C slot for mini OLED display as well as up to 3 slots I2C sensors.

### Sensors

ANAVI Thermometer has a built-in DHT22/AM2303 temperature and humidity sensor. Additionally, you can attach external DS18B20 waterproof temperature sensor module. The officially supported I2C add-on sensor modules are for:

* Light (BH1750)
* Temperature and humidity (HTU21D)
* Color and gesture recognition (APDS-9960)
* Temperature and barometric pressure (BMP180)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Light Sensor

The official light I2C sensor for ANAVI Thermometer is BH1750.

Using 4 Dupont jumper wires connect BH1750 to one of the 3 I2C slots on ANAVI Thermometer as follows:

| BH1750   | ANAVI Thermometer |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |


#### I2C External Temperature & Humidity Sensor

The official external temperature and humidity add-on sensor for ANAVI Thermometer is HTU21 (SHT21). This is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 3 I2C slots on ANAVI Thermometer as follows:

| HTU21    | ANAVI Thermometer |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Color & Gesture Recognition Sensor

The official I2C sensor for RGB color and gesture detection on ANAVI Ligth pHAT is APDS-9960.

Using 4 Dupont jumper wires connect APDS-9960 to one of the 3 I2C slots on ANAVI Thermometer as follows:

| APDS-9960  | ANAVI Thermometer |
| ---------- |:-------------- |
| VIN        | 3.3V           |
| GND        | GND            |
| SCL        | SCL            |
| SDA        | SDA            |

#### Temperature & Barometric Pressure Sensor

The official temperature and barometric pressure sensor for ANAVI Thermometer is BMP180. This is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 3 I2C slots on ANAVI Thermometer as follows:

| BMP180   | ANAVI Thermometer |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Assembly

You can assemble ANAVI Thermometer with your bare hands and a screw driver following the steps below:

* Add sensors to your ANAVI Thermometer.
* Optionally, you may also assemble the simple acrylic case by removing the protective film and mounting screws.
* Use 5V power supply and plug an appropriate cable in the microUSB of ANAVI Thermometer to turn on the board.

## Powering ANAVI Thermometer

ANAVI Thermometer has been tested using various 5V power supplies and USB to microUSB cables. It is recommended to use 5V power supply with 1A or higher current output. Make sure that you are using a 5V power supply from a trusted supplier. Cheap, untested power supplies can be risky and unreliable.

## Configure ANAVI Thermometer

[Video tutorial for getting started with ANAVI Light Controller, same procedure for ANAVI Thermometer](https://www.youtube.com/watch?v=Y_81CuuGm0Y)

Turn on ANAVI Thermometer by plugging an appropriate power supply. As soon as the board is turned on for the very first time it will create a temporary WiFi access point. Connect to it from your computer, smartphone or tablet.

The default software of ANAVI Thermometer has a captive portal which guides you through the configurations. As you see in the video you have to select your WiFi network and enter a password if it is not open.

Our open source software relies on the machine to machine communication protocol MQTT to report data from the sensors. You can connect to your own MQTT broker or just leave the default configurations and connect to the public broker as shown in the video.

Recent versions of the firmware support [Home Assistant MQTT Discovery](https://www.home-assistant.io/docs/mqtt/discovery/) which makes it very convenient to add ANAVI Thermometer to Home Assistant.  For this to work, you need to enter the sensor name (such as "Master Bedroom") that will be used for this Thermometer on the setup screen.  See Chapter 4 for more details.

Recent versions of the firmware support Over-the-Air upgrades of the software.  To enable this, you need to specify the IP address or DNS domain name of a web server that hosts the firmware. See Chapter 3 for more details.

It very important to copy the machine ID. Later it is needed to identify your device.

When you are ready just click save. If you have entered valid credentials in a moment ANAVI Thermometer will connect to your WiFi network and the configured MQTT broker. This way the configuration is complete and ANAVI Thermometer will turn off its temporary WiFi access point. After that your device, for example smartphone as in the video, will automatically connect again to your WiFi network.

To verify that ANAVI Thermometer is up and running open a modern web browser and visit demo.anavi.technology. Enter your machine ID. Check the advanced settings only if you are not using the default public MQTT broker. Click connect.

## Reset to Factory Defaults

If you decide to change the settings of ANAVI Thermometer you need to reset the board and configure it again.

To reset ANAVI Thermometer press the button and hold it for approximately 6 seconds until the red light stops blinking. After resetting the board there will be a steady red light that indicates that the temporary WiFi access point is on and you can proceed with the configuration again. The reset button works once the ANAVI Thermometer has successfully connected to a WiFi network. If you are running a recent enough version of the firmware, it also works for 2 seconds after you power on the device (while the red LED is blinking quickly).

---

# CHAPTER 3: Software Development

## Default Firmware

By default ANAVI Thermometer comes with [this free and open source Arduino sketch](https://github.com/AnaviTechnology/anavi-termometer-sw).

## USB to UART Module

For uploading firmware to ANAVI Thermometer you need USB to UART module. All kits include CP2102 which out of the box on GNU/Linux distributions. Drivers for MS Windows and Mac OS X are [available at silabs.com](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers).

## Setting up the Arduino IDE

1. Install the Arduino IDE following the instructions from from https://www.arduino.cc/en/Main/Software

2. Add the ESP8266 board package: In **File > Preferences** input http://arduino.esp8266.com/stable/package_esp8266com_index.json into the Additional Board Manager URLs field.

3. In **Tools > Board ... > Boards manager** find and add the **ESP8266** package. Now "Generic ESP8266" should be an option in the **Tools > Boards** menu.

4. In **Tools > Flash Size:** select **4M (1M SPIFFS)**

5. Go to **Sketch > Include Library > Manage Libraries...** and include the following dependencies of the default firmware for ANAVI Light Controller:

* WiFiManager by tzapu (version 0.12.0)
* ArduinoJson by Benoit Blanchon (version 5.11.1)
* PubSubClient by Nick O'Leary (version 2.7.0)
* Adafruit HTU21DF Library by Adafruit (version 1.0.1)
* Adafruit APDS9960 Library by Adafruit (version 1.0.5)
* DHT sensor library by Adafruit (version 1.3.4)
* U8g2 by oliver (version 2.23.18)
* OneWire (version 2.3.4)
* DallasTemperature (version 3.8.0)
* Adafruit Unified Sensor by Adafruit (version 1.0.2)
* Adafruit BMP085 Unified by Adafruit (version 1.0.0)


*Note: Issues might be experienced if using different versions of the libraries.*

## Flashing Custom Firmware

Follow the steps below to compile and flash custom firmware on ANAVI Thermometer from Arduino IDE:

1. To flash the firmware from Arduino IDE select Tools > Generic ESP8266 Module (Flash mode: DIO, Flash frequency: 40MHz, CPU frequency: 80MHz, Flash size: 4M, Debug port: Disabled, Debug level: None, Reset method: ck, Upload speed: 115200, Port: /dev/ttyUSB0). Set the flash size to 4M (1M SPIFFS). You might need to adjust the port if your USB to serial debug cable is connected on a different port.

2. After that press load an Arduino sketch. [A simple blinking LED example is available at GitHub](https://github.com/AnaviTechnology/anavi-examples/blob/master/anavi-light-controller/anavi-blinking-led/anavi-blinking-led.ino)

3. In Arudino IDE click Verify/Compile (Ctrl+R)

4. Connect ANAVI Thermometer to the USB to serial debug board: GND to GND, TX cable to RX of ANAVI Thermometer and RX cable to TX of ANAVI Thermometer.

5. In Arudino IDE click Upload (Ctrl+U)

6. Press and **hold** the RESET button on ANAVI Thermometer. Plug the 5V power supply in the jack of ANAVI Thermometer (without releasing the RESET button).

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

If you have flashed the blinking LED example, D1 on ANAVI Thermometer with start blinking.

Please have a look at [the YouTube video that shows the exact steps for compiling and uploading an Arduino sketch to ANAVI Thermometer](https://www.youtube.com/watch?v=HMIkPuz0ZJs).

**Note:** you have to be quick between step 5 and 6. Remember to press and **hold** RESET until the upload completes.

# OTA Firmware Upgrade
Recent versions of the official firmware also support OTA firmware updates by putting a firmare binary on a web server and then triggering the update via a MQTT message. This can be very convenient, as you do not have to connect the device to your computer.

## Check support
If the captive portal contained a "OTA server" field, your software supports OTA upgrades.

If you are unsure if your current firmware supports OTA update, you can first check if your ANAVI Thermometer is already setup to receive MQTT commands.

To do this, send a MQTT message to the topic "cmnd/[deviceId]/line1" with message body "test", for example using mosquitto_pub:

```
mosquitto_pub -h [mqttserver] -p 1883 -t cmnd/b5cfb5cfb5cfb5cfb5cfb5cfb5cfb5cf/line1 -u [mqttuser] -P [mqttpass] -m "test"
```

When this message causes the first line of your ANAVI Thermometer display to change to "test", OTA updates should be supported.
If not (after double checking that you used the correct topic and deviceId), please first update to a more recent firmware version.

(To reset the line again to the default display, just send an empty message to the same topic). 

## Enabling OTA upgrades
For security reasons, OTA upgrades are disabled by default. There are two ways to enable them: either enter an IP address or domain name on the captive portal screen (see Chapter 2), or edit the official source code and define OTA_SERVER as explained in the comment. (You can even do both, if you want the Thermometer to accept upgrades from two sources.)

The web server can be located anywhere, but for improved security it is best if it is located on your local network, and no untrusted persons should be able to edit any files at all on the server. Don't host your firmware images on a shared server!

## Build binary firmware image
Using the arduino build setting above, instead of clicking Upload (Ctrl+U), use Menu Sketch -> Export compiled binary (CTRL+ALT+S). A .bin file will be created in the same folder as the .ino file. 
Copy this file to the HTTP webserver you specified when you enabled OTA upgrades.

## Trigger update
The devices listens to MQTT messages in topic "cmnd/[deviceid]/update" and expects messages to be in the format

```
{"file":"/[filePath]", "server": "[server IP or DNS name]"}
```

For example, if you put the file at http://192.168.100.46/anavi.bin: 

```
{"file":"/anavi.bin", "server": "192.168.100.46"}
```

If your server does not listen on port 80, you can provide the port, for example for  http://192.168.100.46:8080/anavi.bin: 

```
{"file":"/anavi.bin", "server": "192.168.100.46", "port": 8080}
```

Example for sending an update message using mosquitto_pub:

```
mosquitto_pub -h [mqttserver] -p 1883 -t cmnd/b5cfb5cfb5cfb5cfb5cfb5cfb5cfb5cf/update -u [mqttuser] -P [mqttpass] -m "{\"file\":\"anavi.bin\", \"server\":\"192.168.100.46\", \"port\":8080}
```
***Note: To ensure successful update, please specify the file with leading slash ('/'), use an HTTP web server, not HTTPS, and -- when run from the command line -- escape quote characters***

On receipt of this message, ANAVI Thermometer will download the file from the specified server, update the firmware and restart. As with the normal firmware update, your saved settings such as WiFi and MQTT server settings should remain as configured. 

***Note: After the update, you may find that readings from the DHT22 sensor no longer work and temperature and humidity are shown as "0". In this case, please powercycle the device (unplug power until display turns off, then plug power in again)***

## Using signed builds

If you do OTA upgrades, and especially if you do so over the Internet, you are strongly encouraged to use [Signed Updates](https://arduino-esp8266.readthedocs.io/en/2.5.0/ota_updates/readme.html#advanced-security-signed-updates). Follow the link to see all the details.

If you are running the Arduino IDE on Linux or Mac it is very easy to enable automatic signing.  Just run these commands in the sketch directory:

```
openssl genrsa -out private.key 2048
openssl rsa -in private.key -outform PEM -pubout -out public.key
```

Once this is done, builds will be automatically signed.  In addition to the .bin file, a .bin.signed file will also be created.  You should see messages similar to these when you compile your sketch:

```
Enabling binary signing
Signed binary: /tmp/arduino_build_710055/sketch_apr03a.ino.bin.signed
```

The exact file name will change depending on your installation. Use the signed binary instead of the .bin file. Once you have upgraded your ANAVI Thermometer using a signed build, OTA upgrades will reject any attempt to use an unsigned build, a build signed using the wrong key, or a build that has been tampered with. (If necessary, you can still load an unsigned firmware using the USB to UART module, and then you will be able to use unsigned builds for OTA upgrades as well.)

Be sure the back up the private.key file, and make sure nobody can get hold of it.

---

# CHAPTER 4: Home Assistant

[Home Assistant](https://home-assistant.io/) is a free and open-source home automation platform running on Python 3 with more than 1200 components for integration with popular Internet of Things.

ANAVI Thermometer can be easily integrated in Home Assistant using the component [MQTT sensor](https://www.home-assistant.io/components/sensor.mqtt/). This component supports JSON in the payload of the MQTT messages. To use, in **configuration.yaml** specify MQTT broker and register the sensor with the correspoding MQTT topic, for example:

* Configure MQTT broker:

```
mqtt:
  broker: 127.0.0.1
```

* Register the MQTT sensor:

```
sensor:
    - platform: mqtt
      name: "Temperature"
      unit_of_measurement: 'C'
      state_topic: "home/room/temperature"
      value_template: "{{value_json.temperature}}"
    - platform: mqtt
      name: "Humidity"
      unit_of_measurement: '%'
      state_topic: "home/room/humidity"
      value_template: "{{value_json.humidity}}"
```

MQTT Discovery can simplify this process.  To use this, specify this in **configuration.yaml**:

```
mqtt:
  broker: 127.0.0.1
  discovery: true
  discovery_prefix: homeassistant
```

Also, supply a **Sensor name for Home Assistant** on the captive portal page of the ANAVI Thermometer. Sensors will automatically be created for the temperature, humidity, and (if connected) the DS18B20 waterproof temperature sensor module.

The other sensors do not yet support MQTT Discovery.

---

# CHAPTER 5: Schematics

## Pinout

The components of ANAVI Thermometer relies on ESP8266 (ESP-12 module) and utilizes the following pins:

| Component            | Pins                           |  Arduino Pin ID |
| -------------------- |:------------------------------ |-----------------|
| I2C                  | 13, 14                         |                 |
| DHT22/AM2302         | 11                             | 2               |
| DS18B20              | 6                              | 12              |
| Indication LED (D1)  | 7                              | 16              |
| Reset button (RESET) | 12                             | 0               |
| UART                 | 15, 16                         |                 |

## I2C

The sensors that can be connected to ANAVI Thermometer communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Thermometer includes two 4.7kohm resistors labelled as R2 and R3. If for one reason or another you need to disable the I2C pullup resistors remove R2 and R3.

---

# CHAPTER 6: Frequently Asked Questions (FAQ)

#### What power supply do I need?

You need a standard 5V power supply with microUSB connector.

#### Why isn't a power supply included?

We were unable to source power supplies with universal plugs for the US/EU/UK at an acceptable. Nowadays, 5V power supplies with a microUSB connector are a commodity item because of most smartphone and tables, so you should be able to easily find a suitable unit online or at your local electronics store.

#### Can I remotely control ANAVI Thermometer from a web browser on my smartphone, tablet, or laptop?

Yes, you can use our [demo website](http://demo.anavi.technology/) or easily integrate ANAVI Thermometer in your instance of the popular open source platform [Home Assistant](https://home-assistant.io/) as an MQTT Sensor component.

#### Is ANAVI Thermometer an open source project?

Yes, ANAVI Thermometer is an open source hardware project powered and created with free and open source software. The hardware designs are available at [GitHub under CC BY-SA 4.0 license](https://github.com/AnaviTechnology/anavi-thermometer). All schematics, documents, and source code files are available at [our GitHub repositories](https://github.com/AnaviTechnology/).

#### Is ANAVI Thermometer certified?

Yes, ANAVI Thermometer revision 1.0 has been [certified by the Open Source Hardware Association under UID BG000017](https://certification.oshwa.org/bg000017.html).

#### Does ANAVI Thermometer use the ESP8266?

Yes, ANAVI Thermometer is based on the ESP8266.

#### Can I flash different firmware to ANAVI Thermometer?

Yes, using a USB to serial cable, you can flash custom firmware built from your own source code.

#### Is ANAVI Thermometer compatible with Arduino IDE?

Yes, ANAVI Thermometer is compatible with Arduino IDE. You can easily upload your own Arduino sketches to the board.

#### How can I get involved and help?

Buy any of the available perks, get your hands on the ANAVI Thermometer, contribute to our GitHub repositories, and become part of our open source community!


---

# CHAPTER 7: Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 24 January 2019   | Initial        release      | All             | Leon Anavi      |

## ANAVI Thermometer Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | Stable product                                               |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
