# 🛠️ Lenovo ThinkCentre M720q / M920q / M920x / P330 Tiny — Complete Boardview & Schematics

[![Platform](https://img.shields.io/badge/Platform-Intel%20Coffee%20Lake--S-0071C5.svg)](https://www.intel.com/)
[![Motherboard](https://img.shields.io/badge/Motherboard-IQ3X0IL%20%2F%20NM--B511-orange.svg)]()
[![Revision](https://img.shields.io/badge/Revision-REV%201.0-blue.svg)]()
[![Chipset](https://img.shields.io/badge/Chipset-Intel%20Q370%20%7C%20B360-green.svg)]()
[![Schematic Pages](https://img.shields.io/badge/Schematic-62%20Pages%20Full%20Circuit-red.svg)](schematics/Lenovo-ThinkCentre-M720q-M920q-M920x-Schematics-NM-B511-Rev1.0.pdf)
[![Direct Download](https://img.shields.io/badge/Files-Included%20In%20Repo-success.svg)](#-direct-repository-downloads)

Comprehensive technical documentation, circuit schematics, boardview layout diagrams, and high-resolution motherboard reference photographs for the **Lenovo ThinkCentre Tiny 5th Generation** series (`M720q`, `M920q`, `M920x`) and **ThinkStation P330 Tiny**.

These resources are provided for hardware engineers, electronics repair technicians, and homelab modding enthusiasts conducting component-level diagnostics, power rail tracing, short-circuit troubleshooting, and PCIe expansion modifications.

---

## ⚡ Direct Repository Downloads

All schematics and boardview files are hosted directly within this repository for instant in-browser viewing or offline download:

| Document | Format | Description | Quick View Link |
|:---|:---:|:---|:---:|
| **Full Circuit Schematics** | PDF (62 Pages) | Complete electrical diagrams, power delivery, IC pinouts & timing sequence. | [📖 View Schematics PDF](schematics/Lenovo-ThinkCentre-M720q-M920q-M920x-Schematics-NM-B511-Rev1.0.pdf) |
| **Vector Boardview Layout** | PDF (2 Pages) | Top & bottom silkscreen component locator (PR, PC, PL, PQ, PU, U). | [🔍 View Boardview PDF](schematics/Lenovo-ThinkCentre-M720q-M920q-M920x-Boardview-NM-B511-Rev1.0.pdf) |
| **Motherboard Top Photo** | JPG (2680×2832) | High-resolution component photograph (top side). | [🖼️ View Top Photo](images/Lenovo-M720q-Motherboard-Top.jpg) |
| **Motherboard Bottom Photo** | JPG (2666×3058) | High-resolution component photograph (bottom side). | [🖼️ View Bottom Photo](images/Lenovo-M720q-Motherboard-Bottom.jpg) |

> 🌐 *Alternative Cloud Mirror:* [Google Drive Folder — Boardview & Schematic](https://drive.google.com/drive/folders/1PbOBiAmKG6ls85OmZaaPQPaNJitxXBxA?usp=sharing)

---

## 📸 Motherboard Hardware Overview

### Top Side Reference
The top side accommodates the LGA1151v2 socket, dual DDR4 SO-DIMM slots, proprietary PCIe x8 riser slot, M.2 2280 NVMe SSD slot (White connector), M.2 2230 Wi-Fi/BT slot, Realtek USB-C controller, front I/O, and CPU VRM inductors.

![Lenovo ThinkCentre M720q Motherboard Top](images/Lenovo-M720q-Motherboard-Top.jpg)

### Bottom Side Reference
The bottom side features the Intel Q370/B360 PCH, secondary M.2 2280 NVMe SSD pads (Black connector on M920x/P330), Nuvoton SIO chip, SPI BIOS flash chip, and VRM MOSFET drivers.

![Lenovo ThinkCentre M720q Motherboard Bottom](images/Lenovo-M720q-Motherboard-Bottom.jpg)

---

## 📐 System Architecture & Visual Diagrams

### 1. System Block Diagram
*From Page 2 of the official schematic document.*

The architecture details the Coffee Lake-S desktop processor interconnected via DMI 3.0 (x4) to the Intel 300 Series PCH, PCIe 3.0 lanes, DDR4 channels, display outputs (DisplayPort, HDMI), and peripheral controllers.

![Lenovo ThinkCentre M720q System Block Diagram](images/Lenovo-M720q-M920q-System-Block-Diagram.png)

---

### 2. Boardview Component Layout Previews

#### Top Layer Silk-Screen & Component Map
Vector layout identifying every resistor (`R`), capacitor (`C`), diode (`D`), transistor (`Q`), fuse (`F`), and integrated circuit (`U`) on the primary side:

![Lenovo M720q Boardview Top](images/Lenovo-M720q-Boardview-Top-Preview.png)

#### Bottom Layer Silk-Screen & Component Map
Component designations on the secondary side, covering the PCH perimeter, BIOS SPI ROM, and power rail decoupling caps:

![Lenovo M720q Boardview Bottom](images/Lenovo-M720q-Boardview-Bottom-Preview.png)

---

### 3. Power-On Timing Sequence (G3 → S0 State)
*From Page 60 of the schematic.*

Essential for diagnosing **no-power**, **no-POST**, or **instant power-off** symptoms. Traces the progression from AC DC-IN (+20V) through RTC battery, deep sleep wells (+3.3V_DSW), standby rails (+3.3V_ALW, +5V_ALW), PCH power-good signals, S5/S3 sleep signals, memory power, VCORE power-good, and PLTRST# de-assertion.

![Lenovo ThinkCentre Power Sequence Flow](images/Lenovo-M720q-Power-Sequence.png)

---

## 💻 Supported Models & Motherboard Specifications

### Compatible Machine Types
| Model | Machine Types (MT-M) | Chipset | PCIe Expansion | M.2 NVMe Slots | Default TDP |
|:---|:---|:---:|:---:|:---:|:---:|
| **ThinkCentre M720q Tiny** | `10T7`, `10T8`, `10T9`, `10TA` | Intel B360 / Q370 | PCIe 3.0 x8 (via riser) | 1× M.2 2280 (PCIe 3.0 x4) | 35W (65W with mod) |
| **ThinkCentre M920q Tiny** | `10RR`, `10RS`, `10RT`, `10RU` | Intel Q370 (vPro) | PCIe 3.0 x8 (via riser) | 1× M.2 2280 (PCIe 3.0 x4) | 35W (65W with mod) |
| **ThinkCentre M920x Tiny** | `10S0`, `10S1`, `10S2`, `10S3` | Intel Q370 (vPro) | PCIe 3.0 x8 (dedicated GPU / NIC) | 2× M.2 2280 (Dual NVMe) | 35W / 65W |
| **ThinkStation P330 Tiny** | `30CE`, `30CF`, `30CG` | Intel Q370 (Workstation) | PCIe 3.0 x16 mechanical / x8 elec. | 2× M.2 2280 (Dual NVMe) | 35W / 65W |

### Motherboard Model Codes & Identifiers
* **PCB Silk Markings:** `IQ3X0IL REV: 1.0` / `NM-B511` (also cross-referenced as `NM-B551`)
* **ODM Manufacturer:** LCFC Electronics (Hefei) Co., Ltd.
* **Processor Socket:** Intel LGA1151v2 (Supports 8th & 9th Generation Intel Core i3 / i5 / i7 / i9, Pentium Gold, and Celeron processors)
* **Memory Architecture:** Dual-Channel DDR4-2666 / 2400 MHz SO-DIMM (Up to 64GB supported, non-ECC)
* **Lenovo FRU Part Numbers:** `01MN632`, `01MN633`, `01MN634`, `01MN635`, `02CW258`, `5B20U53896`, `5B20U53897`, `5B20U53898`

---

## 🔬 Key Components & Integrated Circuits (IC) Directory

| Component Function | Designator / IC Part Number | Schematic Location | Key Specifications / Notes |
|:---|:---|:---:|:---|
| **CPU Core VRM Controller** | ON Semi `NCP81220` | Pages 49–52 | Multi-phase IMVP8 PWM Controller driving VCCIA, VCCGT, and VCCSA. |
| **Super I/O (SIO / EC)** | Nuvoton `NCT6686D-L` | Page 21 | Hardware health monitor, fan speed PWM, LPC bus, power sequencing control. |
| **Gigabit Ethernet PHY** | Intel Jacksonville `i219-LM` / `i219-V` | Page 43 | Single-port 10/100/1000 Mbps PHY connected to PCH via PCIe/PCIe CLK. |
| **HD Audio Codec** | Realtek `ALC233VB` | Page 23 | 4-channel high-definition audio codec with integrated stereo headphone amplifier. |
| **USB Type-C Controller** | Realtek `RTS5449` | Page 25 | Front-panel USB-C CC logic, cable orientation detection, and USB 3.1 Gen1 mux. |
| **SPI Flash BIOS ROM** | Winbond `25Q128` (16MB) + `25Q64` (8MB) | Page 20 | Dual SOIC-8 SPI ROM holding UEFI firmware, Intel ME 12.x, and descriptor region. |
| **Trusted Platform Module** | Infineon / Nuvoton `TPM 2.0 (TCG 2.0)` | Page 22 | Hardware-based cryptographic security module for BitLocker / Windows 11. |
| **+3.3V / +5V Dual Buck Reg** | Synchronous Step-Down DC-DC | Page 55 | Derives always-on `+3.3V_ALW` and `+5V_ALW` from primary `+20V_DC_IN`. |
| **DDR4 Memory Power (VDIMM)**| Step-Down Buck Converter | Page 56 | Generates `+1.2V_VDIMM` and DDR4 VTT termination voltage (`+0.6V_VTT`). |
| **PCIe +12V Boost Regulator** | Step-Up Boost Converter | Page 57 | Generates `+12V_PCIE` for the PCIe x8 riser slot from the 19.5V/20V rail. |

---

## 📑 62-Page Circuit Schematics Index

For rapid component lookup, use this table to navigate [schematics/Lenovo-ThinkCentre-M720q-M920q-M920x-Schematics-NM-B511-Rev1.0.pdf](schematics/Lenovo-ThinkCentre-M720q-M920q-M920x-Schematics-NM-B511-Rev1.0.pdf):

| Page | Title & Circuit Description | Page | Title & Circuit Description |
|:---:|:---|:---:|:---|
| **01** | Cover Page, Document Index & Revisions | **32** | DisplayPort B Connector & EMI Protection |
| **02** | System Architecture Block Diagram | **33** | M.2 2230-E Key Wi-Fi / Bluetooth / Intel CNVi |
| **03** | SMBus, Clock Map & Reset Block Diagram | **34** | PCH Display Interfaces (DDP, CNVi, XDP) |
| **04** | CPU: DDR4 Memory Bus Channel A | **35** | PCH Clock Generation & CLK_REQ Lines |
| **05** | CPU: DDR4 Memory Bus Channel B | **36** | Front Panel Power Button & Diagnostic Status LEDs |
| **06** | CPU: PCIe PEG, DMI 3.0 & eDP Interface | **37** | PCH Core Power Rails Decoupling |
| **07** | CPU: Clock, CFG Straps, VID & Debug Signals | **38** | Internal Buzzer & 2.5" SATA FFC Connector |
| **08** | CPU: VCCIA, VCCGT & VCCSA Power Pins | **39** | System PWRGD Logic & Capacitor Bleed-Off |
| **09** | CPU: Ground (VSS) Pin Map | **40** | **PCIe 3.0 x8 Expansion Slot (Riser Header)** |
| **10** | DDR4 SO-DIMM Channel A Connector | **41** | Rear Dual USB 3.1 Gen1 Ports |
| **11** | DDR4 SO-DIMM Channel B Connector | **42** | Rear USB 3.1 Gen2 Ports & Optical Drive FFC |
| **12** | PCH: DMI 3.0 & High-Speed PCIe Lanes | **43** | Intel Jacksonville i219-LM/V Gigabit RJ45 |
| **13** | PCH: PCIe, SATA 6Gbps & GPIO Pins | **44** | Mounting Holes, PCB Fiducials & Ground Stitching |
| **14** | PCH: USB 3.0, USB 2.0 & Port Power Control | **45** | **Primary M.2 2280-M SSD-1 (White Connector)** |
| **15** | PCH: HDA Audio, JTAG, SMBus & SPI ROM | **46** | **Secondary M.2 2280-M SSD-2 (Black Connector)** |
| **16** | PCH: Low-Speed I2C, UART & Power Control | **47** | SMBus Thermal Sensing & Thunderbolt Header |
| **17** | PCH: Ground (VSS) Pin Distribution | **48** | **DC-IN Jack (+20V) & CR2032 RTC Battery** |
| **18** | Hardware Strap Resistors & PCH Boot Config | **49** | NCP81220 IMVP8 PWM Controller Circuit |
| **19** | Intel XDP Debug Header | **50** | CPU VCCIA Phase Inductors & Driver Stages |
| **20** | Dual SPI Flash ROMs (BIOS / ME Firmware) | **51** | CPU VCCGT Integrated GPU Power Rail |
| **21** | Nuvoton NCT6686D-L Super I/O Controller | **52** | CPU VCCSA System Agent Power Rail |
| **22** | Discrete TPM 2.0 (TCG 2.0) Security Chip | **53** | VCCIO 0.95V Power Rail Regulator |
| **23** | Realtek ALC233VB HD Audio & Combo Jack | **54** | PCH 1.05V & Standby 1.8V Regulators |
| **24** | Front USB 3.1 Port with Fast Charging | **55** | **+3.3V_ALW & +5V_ALW Dual Buck Regulators** |
| **25** | Realtek RTS5449 Type-C CC/PD Controller | **56** | **DDR4 +1.2V VDIMM & +0.6V VTT Power** |
| **26** | Modern Standby & CEC Power Management | **57** | **PCIe +12V Step-Up Boost Regulator** |
| **27** | RS-232 COM Header, PS/2 & PWM Fan Control | **58** | Overall Power Rail Architecture Tree |
| **28** | Board-to-Board (BTB) Punch-Out I/O Header | **59** | Power Rail DC/DC Efficiency & Inductor Specs |
| **29** | Deep Sleep Well (DSW) Power Rail Controls | **60** | **System Power Sequence Timing Diagram (G3-S0)** |
| **30** | DisplayPort Output Connector C | **61** | PCH GPIO Configuration Table |
| **31** | Punch-Out Option Port (DP / HDMI / Type-C) | **62** | Revision History & Engineering Notes |

---

## ⚡ Multimeter Troubleshooting & Power Rail Reference

When troubleshooting a motherboard that will not power on, verify these primary voltages in sequence using a digital multimeter with the negative probe grounded to chassis:

```
[DC-IN Adapter: +19.5V / +20.0V]
        │
        ├─► Page 48: Reverse Polarity Protection & Fuse (F1)
        │
        ├─► Page 55: +3.3V_ALW (Always-On Standby Rail)
        ├─► Page 55: +5V_ALW (Always-On Standby Rail)
        │
        ▼ (Power Button Pressed)
        ├─► Page 21: SIO (NCT6686D) releases PWRBTN# to PCH
        ├─► Page 54: +1.05V_PCH / +1.8V_S5 (Chipset Standby)
        ├─► Page 56: +1.2V_VDIMM (DDR4 Memory Power)
        ├─► Page 57: +12V_PCIE (Boost circuit for PCIe slot)
        │
        ▼ (PCH asserts ALL_SYS_PWRGD)
        ├─► Page 49–52: VCCIA (0.8V–1.2V), VCCSA (1.05V), VCCGT (GPU)
        ├─► Page 53: VCCIO (0.95V)
        │
        ▼
   [PLTRST# De-asserted 3.3V -> System Boots]
```

### Common Failure Points:
1. **No Standby LED / Dead Board:** Check input fuse `F1` near the DC input jack and measure resistance across `+3.3V_ALW` and `+5V_ALW` inductors to ground. A reading below 10Ω indicates a shorted buck regulator or bad ceramic MLCC capacitor.
2. **Instant Shut-off after 0.5s:** Check `+12V_PCIE` boost circuit (Page 57) or shorted high-side MOSFETs on the CPU VCCIA power phases (Page 50).
3. **Flashing Amber Power LED:** Indicates memory detection failure (`+1.2V_VDIMM` or missing `+0.6V_VTT` termination) or corrupted Intel ME firmware in the SPI flash.

---

## 🛠️ Homelab Mods & Expansion Guide

### 1. PCIe Riser Card & Baffle Installation
The proprietary horizontal slot allows installing low-profile expansion cards in the M720q, M920q, M920x, and P330 Tiny:
* **Official Lenovo PCIe x16 Riser FRU:** `01AJ940` (x8 electrical, fits all PCIe cards)
* **Alternative Riser FRU:** `01AJ929`
* **Rear PCIe Metal Baffle:** `02YR497` or `01MN893`

#### Popular Community Tested PCIe Cards:
* **10 Gigabit SFP+ Networking:** Intel `X520-DA2`, Intel `X710-DA2`, Mellanox `ConnectX-3 (MCX311A-XCAT)`
* **Multi-Port Gigabit Ethernet:** Intel `I350-T4` (Quad-Port Gigabit RJ45), Intel `I225-V / I226-V` (2.5GbE)
* **Dedicated Low-Profile GPUs (M920x / P330 heatsink required):** AMD Radeon `RX 560 4GB`, Nvidia Quadro `P620`, Nvidia Quadro `P1000`, Nvidia `T400 / T600 / T1000`

### 2. Dual NVMe SSD Modding
* **M920x & P330 Tiny:** Both M.2 slots (Slot 1 White on top, Slot 2 Black on bottom) are fully populated with SMD connectors and power filtering from the factory.
* **M720q & M920q:** The second M.2 footprint on the PCB bottom has traces routed to the PCH (Page 46), but the physical M.2 connector and supporting capacitors are unpopulated on standard B360 boards.

### 3. External BIOS Recovery via CH341A Programmer
If the system is bricked from a failed BIOS update:
1. Locate the dual SOIC-8 flash chips on the bottom of the motherboard near the PCH (Page 20).
2. The primary 16MB BIOS chip holds the UEFI boot code.
3. Attach a 3.3V SOIC-8 test clip connected to a `CH341A` programmer or Raspberry Pi running `flashrom`.
4. Read flash contents twice to verify checksum parity before flashing.

---

## 🧰 Software for Opening Boardview & CAD Files

* **[OpenBoardView](https://openboardview.org/) (Recommended):** Free, open-source multi-platform boardview viewer supporting `.brd`, `.bvr`, `.fz`, and `.cad` files.
* **[BoardViewer](http://boardviewer.net/):** Lightweight Windows utility for `.asc`, `.bdv`, `.brd`, `.bv5`, and `.cad`.
* **Adobe Acrobat Reader / SumatraPDF / Foxit:** For searching schematic signal nets, components, and pin names across all 62 pages.

---

## ⚖️ Legal Disclaimer
*Lenovo, ThinkCentre, and ThinkStation are registered trademarks of Lenovo Group Limited. Intel is a registered trademark of Intel Corporation. All schematics and documentation provided in this repository are for educational, diagnostic, and hardware repair purposes under Fair Use.*
