# TracerCore CNC Controller v1.0 🛠️

**TracerCore** is a custom 3-axis CNC controller board designed for PCB milling and lightweight CNC applications. Powered by the ATmega328P microcontroller running GRBL v1.1 firmware, it features opto-isolated limit inputs, robust motor drivers, and integrated spindle PWM speed control.

---

## Key Features 🚀

* **Microcontroller:** ATmega328P (TQFP-32) running GRBL 1.1.
* **USB Interface:** USB Type-C connector with CH340G auto-reset circuit.
* **Power Supply:** Integrated LM2596S buck converter (24V to 5V Step-Down).
* **Stepper Motor Drivers:** 3x DRV8825 stepper drivers supporting up to 1/32 microstepping.
* **Spindle Control:** High-current AOD4184A N-Channel MOSFET with flyback protection diode.
* **Inputs & Noise Immunity:** 4x Opto-isolated inputs (PC817) for X/Y/Z Limit switches and Z-Probe with RC filters.
* **Status LEDs:** Power indicators, RX/TX activity, and System Status (D13).

---

## Hardware Architecture 🔌

| Block | Key Components | Function |
| :--- | :--- | :--- |
| **Logic & MCU** | ATmega328P, 16MHz Crystal | GRBL execution and signal routing |
| **USB-Serial** | CH340G, USB Type-C | G-code communication with PC |
| **Power Logic** | LM2596S-5.0, 33µH Inductor | 24V Main to 5V Logic power |
| **Motor Drivers** | DRV8825, 100µF Capacitors | Driving X, Y, Z Axis Steppers |
| **Spindle MOSFET** | AOD4184A, SS14 Diode | PWM Control for 775 Spindle |
| **Limit Filters** | PC817, 10kΩ/100nF Filters | EMI-protected limit switch triggering |

---

## License 📜
Distributed under the **MIT License**.