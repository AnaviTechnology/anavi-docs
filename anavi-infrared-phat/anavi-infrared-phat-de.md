# ANAVI Infrarot pHAT

**Machen sie eine leistungsfähige Fernbedienung aus ihrem Raspberry Pi**

---

# HAFTUNGSAUSSCHLUSS

Raspberry Pi und das Raspberry Pi-Logo sind registrierte Handelsmarken der Raspberry Pi Foundation. ANAVI, das ANAVILogo und Kombinationen davon, sind registrierte Handelsmarken von Leon Anavi. Andere Produktnamen können Handelsmarken anderer sein und die Rechte daran ihren entsprechenden Besitzern gehören.

Die Information in diesem Dokument bezieht sich ausschließlich auf Anavi-Produkte. Dieses Dokument oder der Verkauf von Anavi-Produkten führt zu keiner Erteilung irgendwelcher Lizenzen, 
weder ausdrücklich noch implizit oder auf eine andere Weise, an irgendwelchen geistigen Eigentumsrechten.</p>

Diese Arbeit ist lizensiert unter der Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) Lizenz. Um diese Lizenz zu sehen, 
besuchen sie http://www.creativecommons.org/licenses/by-sa/3.0/.

Das Hardware-Design des ANAVI Infrared pHAT steht unter der Creative Commons Attribution-ShareAlike 3.0 Unported-Lizenz.

Die Software-Beispiele sind unter der MIT- und der Rest die restliche Software unter der GPLv3-Lizenz heraus gegeben.

Die Bilder in dieser Anleitung können von der neuesten Version der Leiterplatte abweichen.

Das Produkt, das dieser Beschreibung zu Grunde liegt, wird ständig weiter entwickelt und verbessert. Alle Einzelheiten des Produkts und seiner Anwendung, die in diesem Dokument genannt werden von Anavi in gutem Glauben veröffentlicht. Es sind jedoch alle Gewährleistungsansprüche, implizit oder ausdrücklich erwähnt, einschließlich, aber nicht beschränkt auf die implizierte Zusicherung der Marktfähigkeit und Gebrauchsfähigkeit, ausgeschlossen. Dieses Dokument dient nur dazu dem Anwender bei der Benutzung des Produktes zu helfen. Anavi kann nicht für Verluste oder Beschädigungen haftbar gemacht werden, die von der Verwendung der Informationen, von Irrtümern oder Weglassungen in diesem Dokument beziehungsweise durch unsachgemäße Verwendung des Produktes entstanden.

Diese Entwicklungsplatine/Bausatz ist nur für die technische Entwicklung, Demonstration und Evaluierung gedacht und wird von Anavi nicht als fertiges Endprodukt für allgemeine Verwendung durch Konsumenten betrachtet. Verwender dieses Produktes müssen eine Ausbildung in Elektronik haben und nach dem Stand der Technik vorgehen. Somit sind die gelieferten Produkte nicht als fertiggestellt zu betrachten, weder in Betracht auf Entwicklungs- oder Marketing-, noch in Bezug auf herstellungsbezogene Schutzmaßnahmmen, einschließlich Produktsicherheits- und Umweltschutz-Maßnahmen wie sie für End-Produkte, die solche Halbleiter-Komponenten oder Leiterplatten enthalten, typisch sind.

Für das Design-Material und die Komponenten die für das ANAVI Thermometer verwendet werden, wird keine Garantie übernommen, sie sind lediglich für das ANAVI Thermometer geeignet.

---

# KAPITEL 1: Überblick

## Einleitung

Das ANAVI Infrarot pHAT ist eine open-source-hardware Raspberry Pi Zusatz-Platine mit einem IR-Empfänger, Sender, UART und 3 I2C-Verbinder für Sensoren. Das ANAVI Infrarot pHAT wurde von Leon Anavi im Jänner 2017 als Hobby-Projekt gestartet. Das Projekt erlaubt ihnen, unter Verwendung der open-source-Software LIRC, ihren Raspberry Pi in eine schlaue Fernbedienung zu verwandeln.

Das ANAVI Infrarot pHAT wurde mit der freien open source electronics design automation suite <a href="http://kicad-pcb.org/" rel="nofollow">KiCAD</a> entwickelt. Es sind keine Lötarbeiten notwendig. Sie können das ANAVI Thermometer mit ihren Händen und einem Schraubenzieher zusammenbauen.

Anavi ist mit der Raspbian GNU/Linux Distribution voll kompatibel und es werden ihnen open-source Beispiel-Applikationen zur Verfügung gestellt.

## Eigenschaften

Das ANAVI Infrarot pHAT Raspberry Pi HAT enthält:

* IR LED
* IR Foto-Sensor
* Verbinder für bis zu 3 plug and play I2C-Sensoren

## Unterstützte Raspberry Pi Versionen und Modelle

Das ANAVI Infrarot pHAT ist mit den folgenden Raspberry Pi Versionen und Modellen kompatibel:

* [Raspberry Pi 3 Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/)
* [Raspberry Pi 0](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi 0 W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Raspberry Pi Model B+](https://www.raspberrypi.org/products/model-b-plus/)
* [Raspberry Pi Model A+](https://www.raspberrypi.org/products/model-a-plus/)

Das ANAVI Infrarot pHAT ist **NICHT**  mit den früheren 26-pin Modellen des Raspberry Pi 1 Modelle B & A kompatibel.

## Zielmarkt

Das ANAVI Infrarot pHAT ist ein Raspberry Pi HAT für bestehende Raspberry-Pi-Kunden, die an Hausautomation, Software-Entwicklung und dem Internet of Things interessiert sind. Die Platine ist für Enthusiasten von embedded programming, GNU/Linux gadget Fans, Studenten, sowie für web und/oder mobile-app Entwickler geeignet. Die Haupt-Verwendung der platine ist embedded Software-Entwicklung und Steuerung von IR-Geräten, ohne die Notwendigkeit, die Hardware komplett zu verstehen.

## Platinen Version

Revision 1.0 des ANAVI Infrarot pHAT wurde beim Schreiben dieses Dokumentes verwendet. Da es daher möglich ist, dass es bereits überholt ist, wird empfohlen die neuesten Sourcen von der GitHub-Seite der Platine zu überprüfen.

# KAPITEL 2: Los geht es

## Electrostatic Warning

Das ANAVI Infrarot pHAT wird in einem Elektrostatik-Schutzbeutel geliefert. Das HAT, sowie der Raspberry Pi darf <strong>KEINEN</strong> hohen elektrostatischen Potentialen ausgesetzt werden. Beim Arbeiten mit der Platine sollte ein Erdungsband oder eine ähnliche Schutzmaßnahme getragen werden. Vermeiden sie das Berühren der Bauteil-Anschlüsse oder anderer metallischer Teile.

## Voraussetzungen

Um das ANAVI Thermometer in Betrieb zu nehmen, benötigen sie die folgenden Artikel:

* kompatibler Raspberry Pi
* microSD-Karte mit einem kompatiblen image
* USB-Stromversorgung

Zusätzlich können sie eine USB-Maus, eine Tastatur, einen HDMI-Monitor oder zusätzliche Peripherie-Geräte an ihren Raspberry Pi anschließen. Es wird eine 2.5A (2500mA) Stromversorgung empfohlen.

## unterstützte Peripherie

Das ANAVI Infrarot pHAT hat einen infrarot Empfänger und einen infrarot Sender. Bis zu 3 I2C-Sensoren können einfach mit dem pHAT verbunden werden.

### Sensoren

Die offiziell unterstützten I2C-Sensor-Module des ANAVI Infrarot pHAT sind:

* Temperatur und Luftdruck (BMP180)
* Temperatur und Feuchte (HTU21)
* Licht (BH1750)

Sie können auch andere I2C-Sensoren anschließen, müssen sich aber selbst um die Software-Integration kümmern.

#### Temperature Sensor

Der offizielle Temperatur-Sensor des ANAVI Infrarot pHAT ist der BMP180. Dieser I2C-Sensor kann sowohl Temperatur, als auch Luftdruck messen.

Verbinden sie den BMP180 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Infrarot pHAT wie folgt:</p>

| BMP180   | ANAVI Infrarot pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Feuchte Sensor

Der offizielle Temperatur- und Feuchte-Sensor des ANAVI Infrarot pHAT ist der HTU21 (SHT21). Dieser I2C-Sensor misst sowohl Feuchte als auch Temperatur.

Verbinden sie den HTU21 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Thermometers wie folgt:

| HTU21    | ANAVI Infrarot pHAT |
| -------- |:-------------- |
| VIN      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

#### Licht Sensor

Der offizielle I2C-Lichtsensor des ANAVI Infrarot pHAT ist der BH1750.

Verbinden sie den BH1750 mit 4 Dupont jumper-Drähten mit einem der 3 I2C-Anschlüsse des ANAVI Infrarot pHAT wie folgt:

| BH1750   | ANAVI Infrarot pHAT |
| -------- |:-------------- |
| VCC      | 3.3V           |
| GND      | GND            |
| SCL      | SCL            |
| SDA      | SDA            |

## Zusammenbau

Anhand der folgenden Schritte können sie den ANAVI Infrarot pHAT mit ihren bloßen Händen zusammenbauen und an ihrem Raspberry Pi montieren:

* Stellen sie sicher, dass ihr Raspberry Pi mit dem ANAVI Infrarot pHAT kompatibel ist.
* Schalten sie ihren Raspberry Pi aus.
* Stecken sie das ANAVI Infrarot pHAT vorsichtig auf den 40-poligen Steckkamm an ihrem Raspberry Pi.
* Schließen sie die Zusatz-Sensoren an ihr ANAVI Infrarot pHAT an.
* Optional können sie auch zwei oder vier Abstandsbolzen M2,5 aus Messing verwenden, um ihren Pi HAT ordentlich am Raspberry Pi zu befestigen und die beiden Platinen auf Abstand zu halten.
* Das ist alles, nun geht es los!

## Stromversorgung des ANAVI Infrarot pHAT

Das ANAVI Infrarot pHAT ist ein Raspberry Pi HAT und wird daher vom Raspberry Pi mit Strom versorgt. Wir empfehlen das [offizielle Raspberry Pi Netzteil](https://www.raspberrypi.org/products/universal-power-supply/) oder ein anderes 2.5A USB Netzteil von einem verläßlichen Lieferanten zu verwenden.

---

# KAPITEL 3: Software

## Installation

Damit das ANAVI Infrarot pHAT richtig arbeitet, benötigt es einen up-to-date kernel, I2C muss aktiviert sein und einige Libraries müssen installiert sein. Nachdem sie **Raspbian** von einer microSD-Karte gebootet haben, öffnen sie ein terminal und folgen den Schritten unten:

* Stellen sie sicher, dass ihre APT-Paketliste up-to-date ist:

```
sudo apt-get update
```

* Installieren sie zusätzliche Applikationen, Libraries und andere Tools, die vom ANAVI Infrarot pHAT gebraucht werden

```
sudo apt-get install -y git i2c-tools vim
```

### Aktivieren sie I2C

Folgen sie den Schritten unten, um I2C zu aktivieren, das von den Sensoren des ANAVI Infrarot pHAT gebraucht wird

* Öffnen sie ein Terminal oder loggen sie sich via SSH auf ihren  Raspberry Pi ein und tippen sie den folgenden Befehl:

```
sudo raspi-config
```

* Wählen sie **Interfacing Options > I2C** und aktivieren sie es.

* Booten sie den Raspberry pi neu.

### Serielles Debugging

Folgen sie den Schritten unten, um das serielle Debugging mit einem USB-zu-seriell-Kabel zu aktivieren:

*  Öffnen sie ein Terminal oder loggen sie sich via SSH auf ihren  Raspberry Pi ein und tippen sie den folgenden Befehl:

```
sudo raspi-config
```

* Wählen sie **Interfacing Options > Serial** und aktivieren sie es.

* Booten sie den Raspberry pi neu.

* Stecken sie das USB-zu-seriell-Kabel an und verbinden sie ihren Raspberry Pi mit ihrem PC. Die **RX** Leitung des Kabels muss zum **TX** Anschluss des **UART** Verbinders am ANAVI Infrarot pHAT führen. Die **TX** Leitung des Kabels muss zum **RX** Anschluss des **UART** Verbinders am ANAVI Infrarot pHAT führen. Die **GND** Leitung muss mit dem **GND** Anschluss am  **UART** Verbinder des ANAVI Infrarot pHAT verbunden werden.

* Um auf das ANAVI Infrared pHAT zuzugreifen, geben sie folgenden Befehl in ihren Computer ein falls sie eine GNU/Linux Distribution verwenden. Wenn ihr OS Microsoft Windows ist, verwenden sie [putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

Es können alle USB-zu-UART seriellen Module, die CP2102 benutzen oder das [Olimex USB-Serial-Cable-F](https://www.olimex.com/Products/Components/Cables/USB-Serial-Cable/USB-Serial-Cable-F/) verwendet werden. Alle Infrarot-Kits enthalten den CP2102, der direkt mit GNU/Linux Distributionen funktioniert. Treiber für MS Windows und Mac OS X erhalten sie auf [silabs.com](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers).

## Beispiele

Unter der MIT-Lizenz werden auf GitHub Beispielanwendungen in Python und C für das ANAVI Infrarot pHAT zur Verfügung gestellt. Alle Beispiele wurden mit **Raspbian** getestet.

Öffnen sie ein Terminal und folgen sie der Schritt-für-Schritt-Anleitung um alle Abhängigkeiten zu installlieren und den source-Code zu bekommen:

* Abhängigkeiten installieren:

```
sudo apt-get update
sudo apt-get install -y git git-core vim python-dev python-rpi.gpio
```

* Installation der GPIO-Interface-Library für den Raspberry Pi namens [wiringPi](http://wiringpi.com/):

```
cd ~
git clone git://git.drogon.net/wiringPi
cd wiringPi
./build
```

* Herunterladen der Beispiele für das ANAVI Infrarot pHAT Raspberry Pi HAT

```
cd ~
git clone https://github.com/AnaviTechnology/anavi-examples.git
cd anavi-examples
```

### Sensoren

Um die Sensoren, die vom ANAVI Infrarot pHAT unterstützt werden, muss **I2C** aktiviert sein.

#### Temperatur Sensor (BMP180)

Folgen sie den Schritten unten, um den BMP180 I2C Temperatur- und Luftdruck-Sensor mit dem ANAVI Infrarot pHAT zu verwenden:

* Verbinden sie den BMP180 mit einem beliebigen I2C-Verbinder des ANAVI Infrarot pHAT mit Hilfe von male-to-female Duport jumper-Drähten.

* Geben sie den folgenden Befehl ein und überzeugen sie sich, dass die Adresse des Sensors angezeigt wird:

```
sudo i2cdetect -y 1
```

* Geben sie den folgenden Befehl ein, um die Beispiel-Anwendung zu kompilierern und Temperatur und Luftdruck anzuzeigen:

```
cd ~/anavi-examples/sensors/BMP180/c/
make
./BMP180
```

* Achten sie darauf, dass ihre Ausgabe ähnlich aussieht (die genauen Werte hängen vom Wetter bei ihnen ab):

```
pi@raspberrypi:~/anavi-examples/sensors/BMP180/c $ ./BMP180
BMP180 Sensor Module
Temperature	28.6 C
Pressure	991.57 hPa
```

#### Feuchte-Sensor (HTU21D)

Folgen sie den Schritten unten, um den HTU21D I2C Temperatur- und Feuchte-Sensor mit dem ANAVI Infrarot pHAT zu verwenden:

* Verbinden sie den HTU21D mit einem beliebigen I2C-Verbinder des ANAVI Infrarot pHAT mit Hilfe von male-to-female Duport jumper-Drähten.

* Geben sie den folgenden Befehl ein und überzeugen sie sich, dass die Adresse des Sensors angezeigt wird:

```
sudo i2cdetect -y 1
```

* Geben sie den folgenden Befehl ein, um die Beispiel-Anwendung zu kompilierern und Temperatur und rel. Luftfeuchte anzuzeigen:

```
cd ~/anavi-examples/sensors/HTU21D/c/
make
./HTU21D
```

* Achten sie darauf, dass ihre Ausgabe ähnlich aussieht (die genauen Werte hängen vom Wetter bei ihnen ab):

```
pi@raspberrypi:~/anavi-examples/sensors/HTU21D/c $ ./HTU21D
HTU21D Sensor Module
25.64C
118.99%rh
```

#### BH1750 Licht Sensor Modul

Folgen sie den Schritten unten, um den BH1750 I2C Licht-Sensor mit dem ANAVI Infrarot pHAT zu verwenden:

* Verbinden sie den BH1750 mit einem beliebigen I2C-Verbinder des ANAVI Infrarot pHAT mit Hilfe von male-to-female Duport jumper-Drähten..

* Geben sie den folgenden Befehl ein und überzeugen sie sich, dass die Adresse des Sensors angezeigt wird:

```
sudo i2cdetect -y 1
```

* Geben sie den folgenden Befehl ein, um die Beispiel-Anwendung zu kompilierern und die Beleuchtungsstärke anzuzeigen:

```
cd ~/anavi-examples/sensors/BH1750/c/
make
./BH1750
```

* Achten sie darauf, dass ihre Ausgabe ähnlich aussieht (die genauen Werte hängen von der Helligkeit bei ihnen ab):

```
pi@raspberrypi:~/anavi-examples/sensors/BH1750/c $ ./BH1750
BH1750 Sensor Module
Light: 418 Lux
```

## Infrarot und LIRC

Das ANAVI Infrarot pHAT Raspberry Pi HAT hat eingebaute IR-Sender und Empfänger. [LIRC](http://www.lirc.org/) (Linux Infrared Remote Control) ist eine beliebte open source Anwendung um, mit GNU/Linux Distributionen, Daten über Infrarot zu senden und zu empfangen. Dieses Kapitel zeigt ihnen, wie sie unter **Raspbian** den IR-Empfänger und IR-Sender, sowie LIRC, verwenden.

## Einrichten von LIRC

Führen sie die unten stehenden Schritte aus, um den infrarot Empfänger und Sender zu aktivieren:

* Installation von LIRC

```
sudo apt-get update
sudo apt-get install -y lirc
```

* Bearbeiten sie die Datei */etc/modules* und fügen sie die IR-Anschlüsse hinzu, indem sie folgende Zeilen an das Ende der Datei anhängen:

```
lirc_dev
lirc_rpi gpio_in_pin=18 gpio_out_pin=17
```
* Legen sie die Datei */etc/lirc/hardware.conf* an und schreiben sie Folgendes hiein:

```
# /etc/lirc/hardware.conf
#
# Arguments which will be used when launching lircd
LIRCD_ARGS="--uinput"

#Don't start lircmd even if there seems to be a good config file
#START_LIRCMD=false

#Don't start irexec, even if a good config file seems to exist.
#START_IREXEC=false

#Try to load appropriate kernel modules
LOAD_MODULES=true

# Run "lircd --driver=help" for a list of supported drivers.
#DRIVER="UNCONFIGURED"
DRIVER="default"
# usually /dev/lirc0 is the correct setting for systems using udev
DEVICE="/dev/lirc0"
MODULES="lirc_rpi"

# Default configuration files for your hardware if any
LIRCD_CONF=""
LIRCMD_CONF=""
```

* Bearbeiten sie die Datei */etc/lirc/lirc_options.conf* und stellen sie sicher, dass Treiber und Geräte so gesetzt sind:

```
driver          = default
device          = /dev/lirc0
```

* Bearbeiten sie die Datei */boot/config.txt* und konfigurieren sie die Kernel-Erweiterungen durch hinzufügen folgender Zeile an das Ende der Datei:

```
dtoverlay=lirc-rpi,gpio_in_pin=18,gpio_out_pin=17
```

* Booten sie den Raspberry Pi neu:

```
sudo shutdown -r 0
```

## Verwendung des IR-Empfängers

Folgen sie den Schritten unten, um sich zu überzeugen, dass der Empfänger wie erwartet funktioniert:

* Stoppen des LIRC systemd Dienstes:

```
sudo systemctl stop lircd
```

* Starten sie die Ausgabe von Rohdaten des IR-Empfängers

```
mode2 -d /dev/lirc0
```

* Zielen sie mit einer fernbedienung auf den IR-Empfänger am ANAVI Infrarot pHAT und drücken sie einige Tasten. Wenn der IR-Empfänger richtig konfiguriert ist, werden sie eine ähnliche Ausgabe sehen:

```
space 3662230
pulse 2428
space 594
pulse 1201
space 596
pulse 1230
space 595
pulse 1209
space 590
pulse 1204
```

## Verwendung der IR LED

Folgen sie den Schritten unten, um eine LIRC-Konfigurations-Datei zu erstellen und den IR-Sender zu testen:

* Stoppen des LIRC systemd Dienstes:

```
sudo systemctl stop lircd
```

* Lassen sie sich alle verfügbaren Namen für Fernbedienungs-Befehle von LIRC anzeigen:

```
irrecord --list-namespace
```

* Geben sie den folgenden Befehl ein, um eine neue LIRC Steuerungs-Konfigurations-Datei zu erstellen indem sie den Anweisungen am Bildschirm zum Scannen einer Fernbedienung folgen :

```
irrecord -d /dev/lirc0 ~/lircd.conf
```

Beispiel einer Konfigurations-Ausgabe mit dem Namen "hifi":
```
Using driver default on device /dev/lirc0

irrecord -  application for recording IR-codes for usage with lirc
Copyright (C) 1998,1999 Christoph Bartelmus(lirc@bartelmus.de)

This program will record the signals from your remote control
and create a config file for lircd.

A proper config file for lircd is maybe the most vital part of this
package, so you should invest some time to create a working config
file. Although I put a good deal of effort in this program it is often
not possible to automatically recognize all features of a remote
control. Often short-comings of the receiver hardware make it nearly
impossible. If you have problems to create a config file READ THE
DOCUMENTATION at https://sf.net/p/lirc-remotes/wiki

If there already is a remote control of the same brand available at
http://sf.net/p/lirc-remotes you might want to try using such a
remote as a template. The config files already contains all
parameters of the protocol used by remotes of a certain brand and
knowing these parameters makes the job of this program much
easier. There are also template files for the most common protocols
available. Templates can be downloaded using irdb-get(1). You use a
template file by providing the path of the file as a command line
parameter.

Please take the time to finish the file as described in
https://sourceforge.net/p/lirc-remotes/wiki/Checklist/ an send it
to  <lirc@bartelmus.de> so it can be made available to others.

Press RETURN to continue.

Checking for ambient light  creating too much disturbances.
Please don't press any buttons, just wait a few seconds...

No significant noise (received 0 bytes)

Enter name of remote (only ascii, no spaces) :hifi
Using hifi.lircd.conf as output filename

Now start pressing buttons on your remote control.

It is very important that you press many different buttons randomly
and hold them down for approximately one second. Each button should
generate at least one dot but never more than ten dots of output.
Don't stop pressing buttons until two lines of dots (2x80) have
been generated.

Press RETURN now to start recording.
................................................................................
Got gap (45034 us)}

Please keep on pressing buttons like described above.
...............................................................................

Please enter the name for the next button (press <ENTER> to finish recording)
KEY_POWER

Now hold down button "KEY_POWER".

Please enter the name for the next button (press <ENTER> to finish recording)

Checking for toggle bit mask.
Please press an arbitrary button repeatedly as fast as possible.
Make sure you keep pressing the SAME button and that you DON'T HOLD
the button down!.
If you can't see any dots appear, wait a bit between button presses.

Press RETURN to continue.
..............................Cannot find any toggle mask.
You have only recorded one button in a non-raw configuration file.
This file doesn't really make much sense, you should record at
least two or three buttons to get meaningful results. You can add
more buttons next time you run irrecord.


Successfully written config file hifi.lircd.conf
```

* Machen sie ein Backup der original LIRC-Konfigurations-Datei:

```
sudo mv /etc/lirc/lircd.conf /etc/lirc/lircd-backup.conf
```

* Laden sie die neue Konfigurations-Datei, zum Beispiel:

**ACHTUNG: Der Name der Konfiguration häng vom gewählten Namen der Fernbedienung ab. Bitte passen sie den Befehl unten abhängig davon an!**

```
sudo mv hifi.lircd.conf /etc/lirc/lircd.conf
```

* Starten sie den LIRC systemd Dienst wieder:

```
sudo systemctl start lircd
```

* Lassen sie sich alle gespeicherten Tastenanzeigen, zum Beispiel:

**ACHTUNG: Bitte passen sie den Befehl unten abhängig vom Namen ihrer Fernbedienung an!**

```
irsend LIST hifi ""
```

* * Testen sie die Konfiguration-Datei durch das Senden aufgezeichneter IR-Befehle, zum Beispiel POWER (bitte beachten sie, dass der genaue Befehl für unterschiedliche LIRC-Konfigurationen, IR-Geräte und IR-Fernbedienungen varieren kann):

**ACHTUNG: Bitte passen sie den Befehl unten abhängig vom Namen ihrer Fernbedienung an!**

```
irsend SEND_ONCE hifi KEY_POWER
```

## Device Tree Overlays

Device Tree (DT) ist eine Beschreibung der Hardware in einem Linux-System. Das DT-overlay fügt eine Reihe von optionalen Elementen hizu.

Das EEPROM des ANAVI Infrarot pHAT enthält DT-overlay-Daten mit Beschreibungen der Peripherie-Geräte auf dem HAT. Nach dem Anschluss des Anavi an ihren Raspberry Pi und neuem booten, sollten sie einige neue Dateisystem-Knoten in */proc/device-tree/hat* haben:

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

Die Informationen in diesen Dateisystem-Knoten helfen ihnen den Hersteller, die Version, den Produktnamen, etc herauszubekommen. Zum Beispiel:

```
pi@raspberrypi:~ $ cat /proc/device-tree/hat/product
ANAVI Infrared pHAT

pi@raspberrypi:~ $ cat /proc/device-tree/hat/vendor
ANAVI
```

Weitere Informationen über Device-Trees, Overlays und Parameter bekommen sie von der [offiziellen Raspberry Pi Dokumentation](https://www.raspberrypi.org/documentation/configuration/device-tree.md).

---

# KAPITEL 4: ANAVI IoT GNU/Linux Distribution

Die Anavi IoT GNU/Linux Distribution ist noch *under construction*. Sie wird unter Verwendung des **Yocto Project** und von **OpenEmbedded** gebaut und bietet einen Dienst, der, mittels des leichtgewichtigen Maschine-zu-Maschine-Protokolls **MQTT**, Daten von den Sensoren sendet und Nachrichten empfängt. Es gibt auch ein responsive HTML5 web interface, das mit jQuery Mobile und **Node.js** API entwickelt wird. Mehr Details finden sie auf:

* [anaviflexd](https://github.com/AnaviTechnology/anaviflexd)
* [meta-anavi](https://github.com/AnaviTechnology/meta-anavi)
* [anavi-api](https://github.com/AnaviTechnology/anavi-api)
* [anavi-ui](https://github.com/AnaviTechnology/anavi-ui)

---

# KAPITEL 5: Schaltung

## Anschlüsse

Die Komponenten des ANAVI Infrarot pHAT verwenden die folgenden pins am Raspberry Pi:

| Komponente    | Pins                            |
| ------------ |:------------------------------- |
| I2C          | 3, 5                            |
| EEPROM       | 27, 28                          |
| IR LED       | 11                              |
| IR-Empfänger | 12                              |
| UART         | 1, 8, 9, 10                     |

## I2C

Die Sensoren, die mit dem ANAVI Infrarot pHAT verbunden werden können, kommunizieren mit dem Microcontroller mittels eines Kommunikationsstandards namens **I2C** (Inter-Integrated-Circut). I2C benutzt zwei Leitungen, SDA (Serial Data) und SCL (Serial Clock). Um richtig zu funktionieren, benötigt I2C pullup-Widerstände auf jeder dieser Leitungen weshalb das ANAVI Infrarot pHAT die zwei 4.7kOhm Widerstände R6 und R7 verwendet. Wenn sie aus irgend einem Grund die I2C-Schnittstelle ohne pullup-Widerstände benutzen wollen, entfernen sie R6 und R7.

---

# KAPITEL 6: Häufig gestellte Fragen (FAQ)

#### Kann ich das ANAVI Infrarot pHAT mit anderen Betriebssystemen verwenden?

Ja, sie können das ANAVI Infrarot pHAT mit anderen GNU/Linux Distributionen und sogar mit anderen Betriebssystemen, aber es könnten einige Adaptierungsarbeiten erforderlich sein.

#### Kann ich andere I2C-Sensoren mit dem ANAVI Infrarot pHAT verwenden?

Ja, sie können andere I2C-Sensoren mit dem ANAVI Infrarot pHAT verwenden, aber sie müssen sich selbst um die Treiber und um Software-Support kümmern.

#### Kann ich Sensoren ohne I2C-Schnittstelle mit dem ANAVI Infrarot pHAT benutzen?

Nein.

#### Kann ich das ANAVI Infrarot pHAT mit einem Web-Browser auf meinem Smartphone, Tablet oder Laptop aus der Ferne steuern?

Ja, sie können eine populäre open source Software für Haus-Automation, wie [Home Assistant](https://home-assistant.io/) oder [OpenHAB 2](https://www.openhab.org/) auf ihrem Raspberry Pi installieren und das ANAVI Infrarot pHAT integrieren.

#### Ist die ANAVI Infrarot pHAT Software frei und open source?

Ja, die offizielle ANAVI Infrarot pHAT Software ist frei und open source. Die Beispiele stehen unter der MIT Lizenz und der Rest ist unter der GPLv3 verfügbar. Bitte kontaktieren sie uns, wenn sie an einem kommerziellen Produkt arbeiten und die Software unter einer alternativen, kommerziellen Lizenz nutzen wollen.

---

# KAPITEL 7: Revisions-Geschichte

## Documenten Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 15 February 2017  | erste Ausgabe des Handbuches| Alle            | Leon Anavi      |
| 16 September 2017 | Update für Raspbian Stretch | Alle            | Leon Anavi      |

## ANAVI Infrarot pHAT Revision

| Revision| bemerkenswerte Änderungen                                    |
| ------- |:-------------------------------------------------------------|
| 1.0     | erste Version                                                |

## Lesen sie auch

Für weitere Informationen besuchen sie [anavi.technology](http://anavi.technology/) und unsere [GitHub-Repositories](https://github.com/AnaviTechnology). Wenn sie fragen oder Unklarheiten haben, kontaktieren sie uns auf [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) oder per [email](mailto:info@anavi.technology).

---
