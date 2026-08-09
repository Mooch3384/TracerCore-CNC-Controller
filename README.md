<div align="center">

# ⚡ TracerCore CNC Controller v1.0

### High-Performance, Noise-Isolated 3-Axis Motion Control Board

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![GRBL Version](https://img.shields.io/badge/Firmware-GRBL%20v1.1-blue.svg)
![CAD](https://img.shields.io/badge/Designed%20With-Altium%20Designer-red.svg)
![MCU](https://img.shields.io/badge/MCU-ATmega328P-green.svg)

<p align="center">
  <b>A robust open-source hardware solution tailored for PCB milling, desktop CNC carving, and laser engraving.</b>
</p>

---

</div>

## 📌 Overview

**TracerCore v1.0** is a custom hardware controller engineered to deliver precision and heavy noise immunity in high-EMI environments. Built around the industry-proven **ATmega328P** running **GRBL v1.1**, it bridges the gap between low-cost Hobby CNC shields and industrial-grade controllers by integrating opto-isolated inputs, active EMI filtering, dedicated PWM spindle control, and high-step resolution drivers on a single board.

---

## 🔥 Key Features

- 🧠 **Core Processing:** Powered by ATmega328P (TQFP-32) running GRBL 1.1 firmware.
- 🔌 **Modern Connectivity:** USB Type-C interface driven by a CH340G IC with an integrated auto-reset timing network for seamless flashing and communication.
- ⚡ **Wide Power Input:** Integrated LM2596S DC-DC Buck Converter steps down main power (up to 24V) to a stable 5V logic supply.
- 🎯 **3-Axis Motor Control:** Triple DRV8825 stepper driver sockets supporting up to 1/32 microstepping for ultra-smooth movement.
- 🛡️ **Opto-Isolated Limits:** 4x Fully isolated channels (PC817) for X, Y, Z limit switches and a Z-Probe, backed by hardware RC filters to eliminate false triggers from motor noise.
- ⚙️ **Spindle Speed Control:** High-current AOD4184A N-Channel MOSFET with SS14 flyback diode protection for PWM control of 775-type motors.
- 💡 **Visual Diagnostics:** Onboard status LEDs for Power (24V & 5V), RX/TX USB activity, and System Status (D13).

---

## 🏗️ Hardware Architecture

```text
 ┌────────────────┐      ┌─────────────────┐      ┌──────────────────────┐
 │ 24V Main Power ├─────►│  LM2596S Buck   ├─────►│  5V Logic Subsystem  │
 └───────┬────────┘      └─────────────────┘      └──────────┬───────────┘
         │                                                   │
         ├──────────────► 3x DRV8825 Drivers ◄───────────────┤
         │                                                   │
         ├──────────────► Spindle MOSFET (AOD4184A) ◄────────┼───► ATmega328P MCU
         │                                                   │      ▲
         └──────────────► Opto-Isolators (PC817) ────────────┴──────┘