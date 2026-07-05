# ANAVI TPM 2.0

## DATASHEET

---

## Overview

![ANAVI TPM 2.0](images/anavi-tpm-2-1.jpg?raw=true "ANAVI TPM 2.0")

**ANAVI TPM 2.0** is an open-source hardware add-on that provides a **Trusted Platform Module (TPM) 2.0** for Raspberry Pi single board computers. It is designed to deliver hardware-based security, including secure key storage, cryptographic operations, and platform integrity.

The board is built around the **Infineon OPTIGA™ TPM SLB 9672**, a certified TPM 2.0 security controller compliant with modern standards and cryptographic requirements. 

The **OPTIGA™ TPM SLB 9672** is a high-end, standardized TPM 2.0 security controller designed for PCs, embedded systems, and IoT devices. It provides strong cryptographic capabilities and future-proof security features including post-quantum protection. 

---

## Key Features

### ANAVI TPM 2.0 

- Open-source hardware design
- Certified by the [Open Source Hardware Association (OSHWA) under UID BG000152](https://certification.oshwa.org/bg000152.html)
- Compatible with Raspberry Pi single board computers via GPIO (2x5 header)
- Available in:
  - Horizontal version ANAVI-SPI-TPM2-H
  - Vertical (90°) version ANAVI-SPI-TPM2-V
- Supports SPI communication interface
- Functions as:
  - Secure key storage
  - Cryptographic processor
  - True Hardware Random Number Generator (TRNG)
- Made in Plovdiv, Bulgaria, EU

---

### ANAVI TPM 2.0 Variants

| Variant                  | Mounting                      | Part Number                  |
|--------------------------|-------------------------------|------------------------------|
| ANAVI TPM 2.0 Horizontal | Horizontal                    | ANAVI-SPI-TPM2-H             |
| ANAVI TPM 2.0 Vertical   | Vertical                      | ANAVI-SPI-TPM2-V             |

![ANAVI TPM 2.0](images/anavi-tpm-2-2.jpg?raw=true "ANAVI TPM 2.0")

---

## Security Features & Compliance

Infineon OPTIGA TPM SLB 9672 used in ANAVI TPM 2.0 is:

- TCG TPM 2.0 Library Specification Rev. 1.59
- High confidence level based on Common Criteria and FIPS certification
- High-performance cryptographic engine
- RSA, ECC, AES, SHA, NIST RNG SP800-90A/B, 3GPIO
- Firmware update capability with PQC protection
- Full personalization with 3 endorsement keys (EK) and 3 EK certificates (RSA-2048, ECC NIST P256, ECC NIST P384)

![ANAVI TPM 2.0](images/anavi-tpm-2-3.jpg?raw=true "ANAVI TPM 2.0")

---

## Electrical & Interface Characteristics

| Parameter            | Value                               |
|----------------------|-------------------------------------|
| Interface            | SPI                                 |
| Supply Voltage       | 3.3 V                               |
| Raspberry Pi Pins    | 2x5 pins: 17 to 26                  |
| PCB Dimensions       | 18.4 x 12.9 mm (0.72 x 0.51 inches) |
| Temperature Range    | -20°C to +85°C                      |

---

## Software & Compatibility

- Native support in Linux distributions, including Raspberry Pi OS
- Works with standard TPM drivers and tools
- Compatible with existing TPM device tree overlays in Raspberry Pi OS
- Supported by development tools and example code

---

## Applications

- IoT and edge devices
- Secure Raspberry Pi projects
- Industrial automation 
- Networking equipment (routers, gateways)
- Servers and embedded systems
- Smart buildings and home automation

---

## Mechanical & Integration

- Form factor: compact add-on board
- Connector: 2x5 pin female header (2.54 mm)
- Mounting options: horizontal or vertical
- Compatible with all Raspberry Pi single board computers

![ANAVI TPM 2.0](images/anavi-tpm-2-4.jpg?raw=true "ANAVI TPM 2.0")
