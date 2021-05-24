---
fontfamily: dejavu
header-includes:
  - \exhyphenpenalty=10000
  - \hyphenpenalty=10000
  - \hypersetup{colorlinks=false,
            allbordercolors={0 0 0},
            pdfborderstyle={/S/U/W 1}}
---

# ANAVI Macro Pad 2

## DATASHEET

![ANAVI Macro Pad 2](images/anavi-macro-pad-2-01.jpg?raw=true "ANAVI Macro Pad 2")

ANAVI Macro Pad 2 is a tiny open source, programmable two-key mechanical keypad with backlighting. Each of the two keys allows you to reprogram and use it as macro keypad or even dedicated shortcut keys.

ANAVI Macro Pad 2 is certified by the Open Source Hardware Association under [UID
BG000077](https://certification.oshwa.org/bg000077.html). Designed with [KiCad](https://kicad.org/), [OpenSCAD](https://openscad.org/) and [Inkscape](https://inkscape.org/). Made in Plovdiv, Bulgaria, EU.

ANAVI Macro Pad 2 can be customized for multiple use cases across various industries. It is the perfect fit for copy and paste as well as video conferencing applications. You can easily turn the camera or microphone on or off. Various keymaps are available, including for Zoom, Jitsi, Skype, Microsoft Teams, Google Meet, and Git.

ANAVI Macro Pad 2 boosts your daily productivity by providing an amazing level
of control with gorgeous light effects at your fingertips!

\pagebreak

## Features & Specifications

* **Keys:** 2 Gateron red mechanical switches with 3 mm LED backlit and translucent keycaps
* **CPU:** [Microchip ATtiny85](https://www.microchip.com/wwwproducts/en/ATtiny85)
* **Connectivity:** microUSB
* **Firmware:** Quantum Mechanical Keyboard (QMK) open source firmware
* **Compatibility:** Windows, MacOS, and GNU/Linux support
* **Dimensions:** 40x38 mm (1.60x1.50 inches)

ANAVI Macro Pad 2 relies on [QMK firmware](https://github.com/qmk/qmk_firmware), [Micronucleus](https://github.com/micronucleus/micronucleus) bootloader and [V-USB](https://www.obdev.at/products/vusb/index.html), an open source software-only implementation of a low-speed USB device for Microchip’s AVR® microcontrollers. There is 5 second boot delay during which the Microchip ATtiny85 microcontroller on ANAVI Macro Pad 2 can be reprogrammed.

![ANAVI Macro Pad 2](images/anavi-macro-pad-2-02.jpg?raw=true "ANAVI Macro Pad 2")

ANAVI Macro Pad 2 is made in Plovdiv, Bulgaria, EU by [ANAVI Technology Ltd](https://anavi.technology/).

\pagebreak

## Kit Configurations

ANAVI Macro Pad 2 is available in two do-it-yourself kits. USB to Micro USB cable is **not** included in any of the kits.

||Maker Kit|Developer Kit|
|----|----|----|
|**ANAVI Macro Pad 2**|Yes|Yes|
|**2 Gateron red mechanical switches**|Yes|Yes|
|**2 translucent keycaps**|Yes|Yes|
|**Keyswitch red backlighting**|Yes|Yes|
|**Acrylic enclosure**|Yes|Yes|
|**Requires Soldering**|Yes|No|

![ANAVI Macro Pad 2](images/anavi-macro-pad-2-03.jpg?raw=true "ANAVI Macro Pad 2")

\pagebreak

#### ANAVI Macro Pad 2 Developer Kit (CS-ANAVI-MP2-1)

![ANAVI Macro Pad 2 Developer Kit](images/anavi-macro-pad-developer-kit.jpg?raw=true "ANAVI Macro Pad 2 Developer Kit")

The Developer Kit does **not** require any soldering. It features Gateron red mechanical switches and translucent keycaps with red backlighting. The Developer Kit is easy to get started with, and it is perfect even for newbies. Just pop the keycaps on, and you're ready to go.

\pagebreak

#### ANAVI Macro Pad 2 Maker Kit (CS-ANAVI-MP2-2)

![ANAVI Macro Pad 2 Maker Kit](images/anavi-macro-pad-maker-kit.jpg?raw=true "ANAVI Macro Pad 2 Maker Kit")

The Maker Kit is for advanced users only. It requires soldering, but provides you the opportunity to pick your own mechanical switches (compatible with Cherry MX plate or PCB footprint) and color of 3 mm backlit LEDs.

## Hardware Schematics

ANAVI Macro Pad 2 [schematics are available at GitHub](https://github.com/AnaviTechnology/anavi-macro-pad-2). It utilizes the following pins on Microchip ATtiny85:

| Component           | Pins                            |
| ------------------- |:------------------------------- |
| USB                 | PB3, PB4                        |
| Mechanical Switches | PB0, PB2                        |
| 3mm LEDs            | PB1                             |

## Resources

* [User's manual](https://github.com/AnaviTechnology/anavi-docs/tree/master/anavi-macro-pad-2)
* [Quantum Mechanical Keyboard (QMK) configurations](https://github.com/qmk/qmk_firmware/tree/master/keyboards/anavi/macropad2)
* For more information visit [https://anavi.technology/](https://anavi.technology/)
