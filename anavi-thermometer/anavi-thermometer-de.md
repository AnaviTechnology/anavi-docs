# ANAVI Thermometer
**Eine ESP8266-betriebene, open source Wi-Fi Entwicklungs-Platine mit Temperatur- und Feuchte-Sensoren**
---
# HAFTUNGSAUSSCHLUSS

ANAVI, das ANAVILogo und Kombinationen davon, sind registrierte Handelsmarken von Leon Anavi. Andere Produktnamen können Handelsmarken anderer sein und die Rechte daran ihren entsprechenden Besitzern gehören.

Die Information in diesem Dokument bezieht sich ausschließlich auf Anavi-Produkte. Dieses Dokument oder der Verkauf von Anavi-Produkten führt zu keiner Erteilung irgendwelcher Lizenzen, weder ausdrücklich noch implizit oder auf eine andere Weise, an irgendwelchen geistigen Eigentumsrechten.

Diese Arbeit ist lizensiert unter der Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) Lizenz.
Um diese Lizenz zu sehen, besuchen sie https://creativecommons.org/licenses/by-sa/4.0/.

Das Hardware-Design des ANAVI Thermometer steht unter der Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)-Lizenz.

Die Software-Beispiele sind unter der MIT- und der Rest die restliche Software unter der GPLv3-Lizenz heraus gegeben.

Die Bilder in dieser Anleitung können von der neuesten Version der Leiterplatte abweichen.

Das Produkt, das dieser Beschreibung zu Grunde liegt, wird ständig weiter entwickelt und verbessert. Alle Einzelheiten des Produkts und seiner Anwendung, die in diesem Dokument genannt werden von Anavi in gutem Glauben veröffentlicht. Es sind jedoch alle Gewährleistungsansprüche, implizit oder ausdrücklich erwähnt, einschließlich, aber nicht beschränkt auf die implizierte Zusicherung der Marktfähigkeit und Gebrauchsfähigkeit, ausgeschlossen. Dieses Dokument dient nur dazu dem Anwender bei der Benutzung des Produktes zu helfen. Anavi kann nicht für Verluste oder Beschädigungen haftbar gemacht werden, die von der Verwendung der Informationen, von Irrtümern oder Weglassungen in diesem Dokument beziehungsweise durch unsachgemäße Verwendung des Produktes entstanden.

Diese Entwicklungsplatine/Bausatz ist nur für die technische Entwicklung, Demonstration und Evaluierung gedacht und wird von Anavi nicht als fertiges Endprodukt für allgemeine Verwendung durch Konsumenten betrachtet. Verwender dieses Produktes müssen eine Ausbildung in Elektronik haben und nach dem Stand der Technik vorgehen. Somit sind die gelieferten Produkte nicht als fertiggestellt zu betrachten, weder in Betracht auf Entwicklungs- oder Marketing-, noch in Bezug auf herstellungsbezogene Schutzmaßnahmmen, einschließlich Produktsicherheits- und Umweltschutz-Maßnahmen wie sie für End-Produkte, die solche Halbleiter-Komponenten oder Leiterplatten enthalten, typisch sind.

Für das Design-Material und die Komponenten die für das ANAVI Thermometer verwendet werden, wird keine Garantie übernommen, sie sind lediglich für das ANAVI Thermometer geeignet.

---

# KAPITEL 1: Überblick

## Einleitung

Das ANAVI Thermometer ist eine open source Hardware. Es ist eine Wi-Fi Entwicklungs-Platine mir einem ESP8266-Prozessor zum Messen von Temperaturen. Ein DHT22/AM2302 Temperatur- und Feuchte-Sensor ist eingebaut und es hat Anschlüsse für ein mini OLED-Display, einen wasserdichten DS18B20 Temperatur-Sensor und freie Verbinder für bis zu drei zusätzliche I2C Sensor-Module. Alle diese Eigenschaften machen das ANAVI Thermometer ideal für Entwickler, Bastler, Studenten und open source Enthusiasten, die an Haus-Automation interessiert sind.

Das ANAVI Thermometer wurde mit der freien open source electronics design automation suite [KiCAD](href="http://kicad-pcb.org/) entwickelt. Es sind keine Lötarbeiten notwendig. Sie können das ANAVI Thermometer mit ihren Händen und einem Schraubenzieher zusammenbauen.

## Eigenschaften &amp; Spezifikationen

* **CPU**: Tensilica L106 32-bit Prozessor (ESP8266)
* **Connectivity**: WiFi 802.11 b/g/n
* **eingebauter Sensor**: Temperatur und Feuchte (AM2302/DHT22)
* **Peripherie-Anschlüsse**: Mini OLED display, Klemmen für den wasserfesten Temperatursensor DS18B20, UART Stifte, Taster, drei Verbinder für I2C-Sensoren
* **Kompatibilität**: Arduino-IDE, PlatformIO, Home Assistant, MQTT, und jeder moderne Web-Browser
* **Zertifizierung**: Open Source Hardware Association (OSHWA) BG000017
* **Abmessungen**: 75 mm x 40 mm

## Ziel-Markt

Das ANAVI Thermometer ist eine zertifizierte open source Hardware Entwicklungs-Platine für Kunden, die an Haus-Automation, Software Entwicklung und dem Internet of Things interessiert sind. Die Möglichkeit einen wasserfesten DS18B20 Sensor anzuschließen macht auch die Temperaturmessung in Aquarien und Flüssigkeiten einfach. Die Platine ist für Enthusiasten des "embedded programming", für open source Unterstützer, für Studenten und/oder Entwickler mobiler Applikationen geeignet. Die Hauptanwendung der Platine ist die Haus-Automation.

## Platinen Version

Revision 1.0 des ANAVI Thermometers wurde beim Schreiben dieses Dokuments verwendet. Da es daher möglich ist, dass es bereits überholt ist, wird empfohlen die neuesten sourcen von der GitHub-Seite der Platine zu überprüfen.

# KAPITEL 2: Los geht es

## Warnung: Elektrostatik

Das ANAVI Thermometer wird in einem Schutzbeutel geliefert. Es darf **KEINEN** hohen elektrostatischen Potentialen ausgesetzt werden. Beim Arbeiten mit der Platine sollte ein Erdungsband getragen werden. Vermeiden sie das Berühren der Bauteil-Anschlüsse oder anderer metallischer Teile.

## Voraussetzungen

Um das ANAVI Thermometer in Betrieb zu nehmen, benötigen sie die folgenden Artikel:

* 5V Stromversorgung mit einem microUSB-Stecker

Es wird eine Stromversorgung mit 1A (1000mA) oder höherer Belastbarkeit empfohlen.

## unterstützte Peripherie

Das ANAVI Thermometer hat Schraubklemmen zum Anschluss eines wasserfesten Temperaturfühlers DS18B20, einen I2C-Anschluss für ein mini OLED-Display sowie bis zu 3 Anschlüsse für I2C-Sensoren.

### Sensoren

Das ANAVI Thermometer hat einen eingebauten DHT22/AM2303 Temperatur- und Feuchte-Sensor. Zusätzlich können sie einen externen wasserfesten Temperaturfühler DS18B20 anschließen. Die offiziell unterstützten I2C Zusatz-Sensormodule sind für:

* Licht (BH1750)
* Temperatur und Feuchte (HTU21D)
* Farbe und Gestenerkennung (APDS-9960)
* Temperatur und Luftdruck (BMP180)

Sie können auch andere I2C-Sensoren anschließen, müssen sich aber selbst um die Software-Integration kümmern.

#### Licht-Sensor

Der offizielle I2C-Lichtsensor des ANAVI Thermometers ist der BH1750.

Verbinden sie den BH1750 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Thermometers wie folgt:

| BH1750   | ANAVI Thermometer |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |


#### I2C Externer Temperatur- &amp; Feuchte-Sensor

Der offizielle Temperatur- und Feuchte-Zusatzsensor des ANAVI Thermometers ist der HTU21 (SHT21). Dieser I2C-Sensor misst sowohl Feuchte als auch Temperatur.

Verbinden sie den HTU21 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Thermometers wie folgt:

| HTU21    | ANAVI Thermometer |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Farb- und Gestenerkennungs-Sensor

Der offizielle I2C-Sensor zur RGB-Farb- und Gesten-Erkennung des ANAVI Ligth pHAT ist der APDS-9960.

Verbinden sie den APDS-9960 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Thermometers wie folgt:

| APDS-9960  | ANAVI Thermometer |
| ---------- |:-------------- |
| VIN        | 3.3V           |
| GND        | GND            |
| SCL        | SCL            |
| SDA        | SDA            |

#### Temperatur- &amp; Luftdruck-Sensor

Der offizielle Temperatur- und Luftdruck-Sensor des ANAVI Thermometers ist der BMP180. Dieser I2C-Sensor kann sowohl Temperatur, als auch Luftdruck messen.

Verbinden sie den BMP180 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Thermometers wie folgt:

| BMP180   | ANAVI Thermometer |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Zusammenbau

Sie können das ANAVI Thermometer mit ihren bloßen Händen und einem Schraubenzieher anhand der folgenden Schritte zusammensetzen:

* Schließen sie die Zusatz-Sensoren an ihr ANAVI Thermometer an.
* Optional können sie es auch in das einfache Acryl-Gehäuse einbauen, indem sie den Schutzfilm abziehen und die Schrauben entfernen.
* Verwenden sie eine 5V-Stromversorgung und stecken sie das entsprechende Kabel in die microUSB-Buchse des ANAVI Thermometers um es einzuschalten.

## Stromversorgung des ANAVI Thermometers

Das ANAVI Thermometer wurde mit verschiedenen 5V-Netzteilen und mit USB zu microUSB Kabeln getestet. Eine 5V-Stromversorgung mit einem Ausgangsstrom von 1A oder mehr wird  empfohlen. Stellen sie sicher, dass ihre Stromversorgung von einem seriösen Hersteller ist. Billige, ungetestete Stromversorgungen können riskant und unzuverlässig sein.

## Konfiguration des ANAVI Thermometers

[Video-Anleitung für den Start mit dem ANAVI Light Controller (gleicher Vorgang beim ANAVI Thermometer](https://www.youtube.com/watch?v=Y_81CuuGm0Y)

Schalten sie das ANAVI Thermometer durch das Anstecken der Stromversorgung ein. Wenn die Platine zum ersten mal eingeschaltet wird, startet sie einen temporären WiFi access point. Verbinden sie sich damit mit ihrem Computer, Smartphone oder Tablet.

Die Standard-Software des ANAVI Thermometers hat ein Captive Portal, das sie durch die Konfiguration führt. Wie sie im Video sehen, müssen sie ihr WiFi-Netz wählen und ein Passwort angeben, falls es nicht offen ist.

Unsere open source Software benutzt das Maschine zu Maschine Kommunikations-Protokoll MQTT um Daten von den Sersoren zu melden. Sie können sich zu ihrem eigenen MQTT-broker verbinden oder einfach die Standardkonfiguration belassen und sich mit dem öffentlichen broker verbinden, wie es im Video gezeigt wird.

Es ist sehr wichtig, sich die Maschinen-ID aufzuschreiben. Sie wird später benötigt, um ihr Gerät zu identifizieren.

Wenn sie fertig sind, klicken sie auf "Save". Wenn sie gültige Anmeldedaten eingegeben haben, wird sich ihr ANAVI Thermometer einen Moment später mit ihrem WiFi-Netz und dem konfigurierten MQTT-broker verbinden. Damit ist die Konfiguration abgeschlossen und das ANAVI Thermometer wird seinen temporären WiFi access point abschalten. Danach wird sich ihr Gerät, z.B. das Handy wie im Video, wieder automatisch mit ihrem WiFi-Netz verbinden.

Um zu überprüfen, ob ihr ANAVI-Thermometer läuft, öffnen sie einen modernen Web-browser und gehen sie zu demo.anavi.technology. Geben sie ihre Maschinen-ID ein. Gehen sie zu den forgeschrittenen Einstellungen (advanced settings) nur wenn sie nicht den öffentlichen Standard-MQTT-broker verwenden. Klicken sie auf "connect".

## Rücksetzen auf Werkseinstellungen

Wenn sie die Einstellungen des ANAVI Thermometers ändern wollen, müssen sie einen Reset der Platine machen und sie neu konfigurieren.

Um das ANAVI Thermometer zurück zu setzen, drücken sie die Taste ca 10 Sekunden bis das rote LED zu blinken beginnt. Nach dem Zurücksetzen der platine leuchtet das rote LED ständig und zeigt damit an, dass der temporäre WiFi access-point eingeschaltet ist und sie mit der erneuten Konfiguration beginnen können.
---

# KAPITEL 3: Software Entwicklung

## Standard Firmware

Das ANAVI Thermometer wird mit [diesem freien open source Arduino sketch](https://github.com/AnaviTechnology/anavi-termometer-sw) geliefert.

## USB zu UART Modul

Zum upload von Firmware in das ANAVI Thermometer benötigen sie ein USB zu UART Modul. Alle kits enthalten einen CP2102, der direkt auf GNU/Linux Distributionen funktionieren. Treiber für MS Windows und Mac OS X [finden sie auf silabs.com](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)

## Einrichten der Arduino-IDE
1. Installieren sie die Arduino-IDE nach den Anweisungen von https://www.arduino.cc/en/Main/Software

2. Fügen sie das ESP8266 Paket hinzu: Schreiben sie im Menü **Datei > Voreinstellungen** http://arduino.esp8266.com/stable/package_esp8266com_index.json in das Feld "Zusätzliche Boardverwalter-URLs".

3. Suchen sie in **Werkzeuge > Board: ... > Boardverwalter** das ESP8266-Paket und installieren sie es. Jetzt sollte "Generic ESP8266 Module" eine Auswahlmöglichkeit im Menü **Werkzeuge > Board** sein.

4. Im Menü **Werkzeuge > Flash Size:** wählen sie **4M (1M SPIFFS)**

5. Gehen sie ins Menü **Sketch > Bibliothek einbinden > Bibliotheken verwalten...** und installieren sie die folgenden Abhängigkeiten der Standard-Firmware für das ANAVI Thermometer:

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

*Bemerkung: Wenn sie andere Versionen der Bibliotheken verwenden, kann es zu Problemen kommen.*

## eigene Firmware flashen

Folgen sie den unten stehenden Schritten und flashen sie mit der Arduino-IDE ihre eigene Firmware auf das ANAVI Thermometer:

1. Um die Firmware mit der Arduino-IDE zu flashen, wählen sie Werkzeuge > Generic ESP8266 Module (Flash mode: DIO, Flash frequency: 40MHz, CPU frequency: 80MHz, Flash size: 4M,  Debug port: Disabled, Debug level: Keine, Reset method: ck, Upload speed: 115200, Port: /dev/ttyUSB0). Bei Bedarf müssen sie eine andere Port-Einstellung wählen, falls ihr USB-zu-seriell-Kabel mit einem anderen Anschluss verbunden ist.

2. Laden sie einen Arduino-sketch mit "Datei" > "Öffnen...". [Ein einfaches Beispiel einer blinkenden LED finden sie auf GitHub](https://github.com/AnaviTechnology/anavi-examples/blob/master/anavi-light-controller/anavi-blinking-led/anavi-blinking-led.ino)

3:Klicken sie auf "Sketch" > "Überprüfen/Kompilieren" in der Arudino-IDE (Ctrl+R)

4. Verbinden sie das ANAVI Thermometer mit der USB-zu-seriell debug-Platine: GND to GND, TX-Leitung an RX am ANAVI Thermometer und RXLeitung an TX am ANAVI Thermometer.

5. Klicken sie auf "Sketch" > "Hochladen" in der Arudino-IDE (Ctrl+U)

6. Drücken und **halten** sie SW1 am ANAVI Thermometer. Stecken sie die 5V-Stromversorgung in die Buchse am ANAVI Thermometer (ohne SW1 loszulassen).

7. Verifizieren sie in der Arduino-IDE, dass der Upload begonnen hat. Halten sie die RESET-Taste bis der upload fertig ist.

In der Arduino-IDE sieht erfolgreiches Flashen so aus:

```
Archiving built core (caching) in: /tmp/arduino_cache_954939/core/core_esp8266_esp8266_generic_CpuFrequency_80,FlashFreq_40,FlashMode_dio,UploadSpeed_115200,FlashSize_512K64,ResetMethod_ck,Debug_Disabled,DebugLevel_None_____1c2aa2b3da66da225b39c9bfab6531e5.a
Sketch uses 224949 bytes (51%) of program storage space. Maximum is 434160 bytes.
Global variables use 31756 bytes (38%) of dynamic memory, leaving 50164 bytes for local variables. Maximum is 81920 bytes.
Uploading 229104 bytes from /tmp/arduino_build_904122/anavi-blinking-led.ino.bin to flash at 0x00000000
................................................................................ [ 35% ]
................................................................................ [ 71% ]
................................................................                 [ 100% ]
```

Wenn sie das Beispiel mit der blinkenden LED geflasht haben, sollte D1 am ANAVI Thermometer zu blinken beginnen.

Bitte sehen sie sich das [YouTube Video an, das die genauen Schritte zum Kompilieren und Hochladen einer Arduino-Sketch auf das ANAVI Thermometer zeigt](https://www.youtube.com/watch?v=HMIkPuz0ZJs).

**Bemerkung:** Sie müssen zwischen Punkt 5 und Punkt 6 schnell sein. Denken sie daran SW1 zu drücken und zu **halten** bis der Upload fertig ist.

# Home Assistant

[Home Assistant](https://home-assistant.io/) ist eine freie open-source Hausautomatisations-Plattform, die auf Python 3 läuft und mehr als 1200 Komponenten zur Integration mit dem populären Internet of Things unterstützt.

Das ANAVI Thermometer kann unter Verwendung der Komponente [MQTT sensor](https://www.home-assistant.io/components/sensor.mqtt/) einfach in Home Assistant integriert werden. Diese Komponente unterstützt JSON in der Nutzlast der MQTT-Nachrichten. Um das zu verwenden, müssen sie in **configuration.yaml** den MQTT-broker angeben und den Sensor am korrespodierenden MQTT-Thema registrieren, zum Beispiel:
* Konfiguration des MQTT-brokers:

```
mqtt:
  broker: 127.0.0.1
```

* Registrieren des MQTT-Sensors:

```
sensor:
    - platform: mqtt
      name: "Temperatur"
      unit_of_measurement: 'C'
      state_topic: "home/room/temperature"
      value_template: "{{value_json.temperature}}"
    - platform: mqtt
      name: "rel. Feuchte"
      unit_of_measurement: '%'
      state_topic: "home/room/humidity"
      value_template: "{{value_json.humidity}}"
```

---

# Schaltung

## Anschlüsse

Die Komponenten des ANAVI Thermometer nutzen einen ESP8266 (ESP-12 Modul) und verwenden die folgenden pins:

| Komponente         | Pins         | Arduino Pin ID |
| ------------------ |:------------ |--------------- |
| I2C                | 13, 14       |                |
| DHT22/AM2302       | 11           | 2              |
| DS18B20            | 6            | 12             |
| LED-Anzeige (D1)   | 7            | 16             |
| Reset Taster (SW1) | 12           | 0              |
| UART               | 15, 16       |                |

## I2C

Die Sensoren, die mit dem ANAVI Thermometer verbunden werden können, kommunizieren mit dem Microcontroller mittels eines Kommunikationsstandards namens **I2C** (Inter-Integrated-Circut). I2C benutzt zwei Leitungen, SDA (Serial Data) und SCL (Serial Clock). Um richtig zu funktionieren, benötigt I2C pullup-Widerstände auf jeder dieser Leitungen weshalb das ANAVI Thermometer die zwei 4.7kOhm Widerstände R2 und R3 verwendet. Wenn sie aus irgend einem Grund die I2C-Schnittstelle ohne pullup-Widerstände benutzen wollen, entfernen sie R2 und R3.

---

KAPITEL 6: Häufig gestellte Fragen (FAQ)

#### Welche Stromversorgung brauche ich?

Sie benötigen eine Standard-5V-Stromversorgung mit einem microUSB-Stecker.

#### Warum wird keine Stromversorgung mitgeliefert?

Wir konnten keine Stromversorgungen mit Steckern für US/EU/UK zu einem annehmbaren Preis finden. Heutzutage finden sie 5V-Stromversorgungen mit microUSB-Stecker allerorten (für smartphones und Tablets), sie sollten ein passendes Gerät daher mühelos online oder in ihrem örtlichen Elektronik-Geschäft erhalten.

#### Kann ich das ANAVI Thermometer von einem web-browser auf meinem Smartphone, Tablet, oder Laptop steuern?

Ja, sie können unsere [Demo Website](http://demo.anavi.technology/) benutzen, oder das ANAVI Thermometer einfach in die populäre open source Plattform [Home Assistant](https://home-assistant.io/) als einen MQTT-Sensor integrieren.

#### Ist das ANAVI Thermometer ein open source Projekt?

Ja, das ANAVI Thermometer ist ein open source Hardware-Projekt, das mit freier und open source Software geschaffen wurde und damit läuft. Die Hardware-Designs sind auf [GitHub unter der CC BY-SA 4.0 Lizenz](https://github.com/AnaviTechnology/anavi-thermometer) verfügbar. Alle Schaltpläne, Dokumente und die source-code Dateien sind auf [unseren GitHub-Repositories](https://github.com/AnaviTechnology/) verfügbar.

#### Ist das ANAVI Thermometer zertifiziert?

Ja, das ANAVI Thermometer Revision 1.0 wurde [zertifiziert von der Open Source Hardware Association unter UID BG000017](https://certification.oshwa.org/bg000017.html)

#### Verwendet das ANAVI Thermometer den ESP8266?

Ja, das ANAVI Thermometer basiert auf dem ESP8266.

#### Kann ich andere Firmware auf das ANAVI Thermometer laden?

Ja, mit dem USB-zu-seriell Kabel können sie beliebige Firmware, die sie aus ihrem eigenen Source-Code kompiliert haben, laden.

#### Ist das ANAVI Thermometer kompatibel mit der Arduino-IDE?

Ja, das ANAVI Thermometer ist mit der Arduino-IDE kompatibel. Sie können ganz einfach ihre eigenen Arduino-Sketches auf die Platine hochladen.

#### Wie kann ich mitmachen und helfen?

Kaufen sie eines der verfügbaren Angebote, arbeiten sie mit dem ANAVI Thermometer, tragen sie zu unseren GitHub-Repositories bei und werden sie Teil unserer open-source Community!

---

# KAPITEL 7: Revisions-Geschichte

## Dokumenten Revision

| Datum           | Änderungen                            | geänderte Seiten  | Autor          |
| --------------- |:-------------------------------------:| :-----------------| :--------------|
|24 Jänner 2019   | erste Ausgabe                         | Alle              | Leon Anavi     |
|24 April 2019    | Software Entwicklung - Abhängigkeiten | Kapitel 3         | Leon Anavi     |


## ANAVI Thermometer Revision
| Revision | bemerkenswerte Änderungen                  |
| -------  |:-------------------------------------------|
| 1.0      | Stabiles Produkt                           |

## Lesen sie auch

Für weitere Informationen besuchen sie [anavi.technology](http://anavi.technology/) und unsere [GitHub-Repositories](https://github.com/AnaviTechnology). Wenn sie Fragen oder Unklarheiten haben, kontaktieren sie uns auf [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) oder mittels [email](href="mailto:info@anavi.technology).

---

