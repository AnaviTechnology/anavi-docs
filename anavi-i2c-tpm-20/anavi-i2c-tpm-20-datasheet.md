# ANAVI I2C TPM 2.0

## DATASHEET

---

## Overview

**ANAVI I2C TPM 2.0** is an open-source hardware add-on that provides a **Trusted Platform Module (TPM) 2.0** functionality to Raspberry Pi single-board computers via the **I2C** interface. It is designed to deliver hardware-based security, including secure key storage, cryptographic operations, and platform integrity.

The board is built around the **Infineon OPTIGA™ TPM SLB 9673**, a certified TPM 2.0 security controller compliant with modern standards and cryptographic requirements. 

The **OPTIGA™ TPM SLB 9673** is a high-end, standardized TPM 2.0 security controller designed for PCs, embedded systems, and IoT devices. It provides strong cryptographic capabilities and future-proof security features including post-quantum protection. 

---

## Key Features

### ANAVI I2C TPM 2.0 

- Open-source hardware design
- Compatible with Raspberry Pi single board computers via GPIO (1x5 header)
- Available in:
  - Horizontal version ANAVI-I2C-TPM2-H
  - Vertical (90°) version ANAVI-I2C-TPM2-V
- Supports SPI communication interface
- Functions as:
  - Secure key storage
  - Cryptographic processor
  - True Hardware Random Number Generator (TRNG)
- Made in Plovdiv, Bulgaria, EU

---

### ANAVI I2C TPM 2.0 Variants

| Variant                      | Mounting                      | Part Number                  |
|------------------------------|-------------------------------|------------------------------|
| ANAVI I2C TPM 2.0 Horizontal | Horizontal                    | ANAVI-I2C-TPM2-H             |
| ANAVI I2C TPM 2.0 Vertical   | Vertical                      | ANAVI-I2C-TPM2-V             |

---

## Security Features & Compliance

Infineon OPTIGA TPM SLB 9673 used in ANAVI I2C TPM 2.0 is:

- TCG TPM 2.0 Library Specification Rev. 1.59 and PC Client Platform TPM Profile (PTP) version 1.05
- High confidence level based on Common Criteria and FIPS 140-2 Level 2
- I2C interface (using clock stretching)
- Random Number Generator (RNG)
- Provisioned with 4 Endorsement Keys (EK) and EK certificates
- 24 PCRs (SHA-1, SHA-256 or SHA384)
- RSA, ECC, SHA-1, SHA-256, SHA-384, AES-128, AES-192, AES-256
- Firmware update capability with PQC protection

---

## Electrical & Interface Characteristics

| Parameter            | Value                              |
|----------------------|------------------------------------|
| Interface            | I2C                                |
| Supply Voltage       | 3.3 V                              |
| Raspberry Pi Pins    | 5 pins: 1, 3, 5, 7, 9              |
| PCB Dimensions       | 16.5 x 12.8mm (0.65 x 0.51 inches) |
| Temperature Range    | -20°C to +85°C                     |

---

## Software & Compatibility

- Native support in Linux distributions, including Raspberry Pi OS
- Works with standard TPM drivers and tools
- Compatible with existing TPM device tree overlay `tpm-slb9673` in the Linux kernel for Raspberry Pi OS
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
- Connector: 1x5 pin female header (2.54 mm)
- Mounting options: horizontal or vertical
- Compatible with all Raspberry Pi single board computers
