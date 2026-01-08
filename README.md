# STM32WL LoRaWAN Prototyping Platform
## Modular Sensor Node for Industrial IoT & Water Quality Monitoring

## 📌 Project Overview
This repository contains the hardware design for a high-performance, ultra-low-power LoRaWAN node based on the **STM32WL55CCU6** SoC. 

This platform serves as an **architectural evaluation board**. It is designed to validate power management strategies, RF performance, and modular sensor interfacing before final product miniaturization.


## 🛠 Technical Specifications

### Core System
* **MCU:** STM32WL55CCU6 (Dual-core ARM Cortex-M4/M0+).
* **Connectivity:** Sub-GHz radio supporting LoRa, (G)FSK, (G)MSK, and BPSK.
* **RF Path:** Optimized 868MHz output with an integrated **BGS12WN6** RF switch and pi-filter matching network.

### Power Management (Ultra-Low Power Focus)
The hardware implements a sophisticated power tree for extreme battery longevity:
* **TPS63900 Buck-Boost:** High-efficiency converter with ultra-low quiescent current, providing a stable 3.3V output across the entire battery discharge curve.
* **LiFePO4 Charging:** Integrated **BQ25071** linear charger, specifically optimized for the safety and cycle-life requirements of LiFePO4 chemistry.
* **Power Gating:** Dedicated load switches to fully disconnect sensor peripherals during deep-sleep cycles, minimizing leakage current.

### PCB Design & Signal Integrity
* **Layer Stack:** 4-layer design (Signal-GND-PWR-Signal) utilizing the **JLC04161H** stackup.
* **Impedance Control:** * **50Ω Single-Ended:** Precision routing for the RF signal path to the antenna.
  * **90Ω Differential:** Calculated for USB data integrity.
* **Manufacturing Ready:** The layout has successfully passed **DFM (Design for Manufacturing)** suites for industrial production standards.

## 🧪 Modular Sensing Interface
To act as a versatile testbed, the board includes:
* Multi-protocol headers (I2C, SPI, UART).
* Analog conditioning circuitry for environmental probes.
* ESD protection on all external sensor interface lines.

## 📂 Project Status
* **Hardware:** Design finalized and DFM-validated. Ready for prototyping.
* **Firmware:** Under active development. Implementing low-power routines and LoRaWAN stack integration using STM32CubeWL HAL.
