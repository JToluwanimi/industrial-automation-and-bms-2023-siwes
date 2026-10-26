# Industrial Automation & Building Management Systems (SIWES 2023)

> **Status:** Hands-on Implementation / Assisted / Studied
> **Author:** Toluwanimi Jesusina
> **Company:** H&O Automation Systems Ltd., Gbagada, Lagos
> **Duration:** 22 Weeks (April 2023 – September 2023)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Completed-green)]()

---

## 1. What is this?

A technical documentation repository based on my 22-week Students' Industrial Work Experience Scheme (SIWES) at H&O Automation Systems Ltd. It details the architecture, installation, configuration, and integration of CCTV, Access Control, Fire Alarm, and Home Automation systems for commercial and residential buildings.

**Note on Responsibility Levels:** This repository distinguishes between:
- **Hands-on Implementation** — I personally installed/configured
- **Assisted Implementation** — I helped under supervision
- **Observed** — I watched and learned
- **Studied** — I analyzed documentation and theory

---

## 2. Why was it built?

To document real-world exposure to large-scale commercial security and building management systems. This repository serves as a knowledge base for industrial communication protocols (RS485, UDP/IP) and system integration, bridging academic theory with practical field experience.

---

## 3. Objectives

| # | Objective | Status |
|---|-----------|--------|
| 1 | Understand CCTV installation lifecycle (survey → mounting → VMS) | ✅ Completed |
| 2 | Study Access Control hardware and software integration | ✅ Completed |
| 3 | Document Addressable Fire Alarm wiring and loop configuration | ✅ Completed |
| 4 | Explore HDL Buspro Home Automation architecture | ✅ Completed |

---

## 4. System Architectures Documented

### 4.1 CCTV System

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           CCTV SYSTEM ARCHITECTURE                          │
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Bullet      │  │  Dome        │  │  PTZ         │  │  IP          │     │
│  │  Cameras     │  │  Cameras     │  │  Cameras     │  │  Cameras     │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                 │                 │                 │             │
│         └─────────────────┴─────────────────┴─────────────────┘             │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  PoE Switch       │                              │
│                          │  (Power + Data)   │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  NVR / DVR        │                              │
│                          │  (Recording)      │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  DSS Software     │                              │
│                          │  (Management)     │                              │ 
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Remote Access    │                              │
│                          │  (Web / Mobile)   │                              │
│                          └───────────────────┘                              │ 
└─────────────────────────────────────────────────────────────────────────────┘
```

**Key Components:**
- **Cameras:** Bullet, Dome, PTZ, IP
- **Recording:** NVR (Network Video Recorder) / DVR (Digital Video Recorder)
- **Cabling:** Cat6 Ethernet (PoE), Coaxial (analog)
- **Software:** Dahua DSS (Video Management System)
- **Remote Access:** Web client, mobile app

**My Involvement:** Assisted with camera mounting, cable routing, and DSS software configuration.

### 4.2 Access Control System

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        ACCESS CONTROL ARCHITECTURE                          │
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Card        │  │  Biometric   │  │  PIN         │  │  Turnstile   │     │
│  │  Reader      │  │  Scanner     │  │  Keypad      │  │  / Door      │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                 │                 │                 │             │
│         └─────────────────┴─────────────────┴─────────────────┘             │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Access Control   │                              │
│                          │  Panel            │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Software         │                              │
│                          │  (User Database,  │                              │
│                          │   Access Logs)    │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Electric Lock    │                              │
│                          │  / Turnstile      │                              │
│                          └───────────────────┘                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Types Studied:**
- Full Height Turnstile
- Radar Turnstile Swing Barrier
- Tripod Turnstile
- Biometric Full Height Turnstile

**My Involvement:** Observed installation, studied wiring, assisted with software setup.

### 4.3 Fire Alarm System (Addressable)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ADDRESSABLE FIRE ALARM ARCHITECTURE                      │
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Smoke       │  │  Heat        │  │  Manual      │  │  Flame       │     │
│  │  Detector    │  │  Detector    │  │  Call Point  │  │  Detector    │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                 │                 │                 │             │
│         └─────────────────┴─────────────────┴─────────────────┘             │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Loop Wiring      │                              │
│                          │  (Fire-Rated      │                              │
│                          │   Cable)          │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Gent Fire Alarm  │                              │
│                          │  Control Panel    │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Notification     │                              │
│                          │  (Horns, Strobes) │                              │
│                          └───────────────────┘                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Key Features:**
- Each device has a unique address
- Control panel identifies exact location of triggered device
- Loop configuration (not star)
- Fire-rated cables

**My Involvement:** Assisted with device mounting, cable routing, and loop wiring. Observed programming and commissioning.

### 4.4 HDL Buspro Home Automation System

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        HDL BUSPRO ARCHITECTURE                              │
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Lighting    │  │  Curtains    │  │  HVAC        │  │  Security    │     │
│  │  Control     │  │  Control     │  │  Control     │  │  Sensors     │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                 │                 │                 │             │
│         └─────────────────┴─────────────────┴─────────────────┘             │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  RS485 Bus        │                              │
│                          │  (Twisted Pair,   │                              │
│                          │   120 Ohm)        │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Buspro Gateway   │                              │
│                          │  (RS485 ↔ UDP/IP) │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Ethernet Switch  │                              │
│                          │  (UDP/IP Backbone)│                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Granite Display  │                              │
│                          │  / HDL ON App     │                              │
│                          └───────────────────┘                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Key Protocols:**
- **RS485:** Industry-standard twisted-pair cable for bidirectional data transmission
- **UDP/IP:** Backbone network for gateway communication
- **Subnet Addressing:** Devices identified as "Subnet/Device" (e.g., "1/2")

**My Involvement:** Studied architecture, documented components, delivered technical presentation.

---

## 5. Hardware & Software Documented

| System | Hardware | Software |
|--------|----------|----------|
| CCTV | Dahua Cameras, NVR, PoE Switch | Dahua DSS |
| Access Control | Card Readers, Biometrics, Turnstiles | Access Control Software |
| Fire Alarm | Gent Detectors, Control Panel | Gent Configuration Software |
| Home Automation | HDL Buspro Modules, Granite Display | Buspro Setup Tool, HDL ON |

---

## 6. Engineering Principles Observed

1. **Redundancy** — UPS for CCTV and Fire Alarm panels during power outages.
2. **Structured Cabling** — Proper cable management, Cat6 termination, RS485 twisted-pair wiring to minimize signal noise.
3. **Safety Compliance** — Fire alarm systems must adhere to local fire codes regarding detector spacing and emergency egress.
4. **Interoperability** — Systems from different manufacturers (Dahua, Gent, HDL) must integrate seamlessly.

---

## 7. Testing & Commissioning

| System | Test Procedure | Result |
|--------|---------------|--------|
| CCTV | Live stream latency, recording playback | ✅ Verified |
| Access Control | Card read, biometric scan, door release | ✅ Verified |
| Fire Alarm | Smoke test, loop communication | ✅ Verified |
| HDL Buspro | Lighting control, scene activation | ✅ Verified |

---

## 8. Limitations

1. **Documentation Only** — This repository documents systems I studied/assisted with, not systems I designed.
2. **No Custom Firmware** — I did not develop firmware for these commercial systems.
3. **Site-Specific** — Client details, IP addresses, and passwords are redacted.

---

## 9. Future Development

| Priority | Enhancement |
|----------|-------------|
| 1 | Integrate HDL Buspro with Home Assistant via RS485 |
| 2 | Study PLC programming (Siemens, Allen-Bradley) |
| 3 | Explore SCADA systems for industrial monitoring |
| 4 | Develop custom IoT gateway for legacy systems |

---

## 10. Lessons Learned

1. **Interoperability is Key** — Industrial automation requires seamless integration between hardware from different manufacturers.
2. **Documentation is Critical** — Maintaining accurate network diagrams and IP address logs is essential for troubleshooting.
3. **Safety First** — Fire alarm systems are life-critical; testing and commissioning must be rigorous.
4. **Protocol Hierarchy** — Understanding the difference between physical layer (RS485) and network layer (UDP/IP) is critical.

---

## 11. Media

*[Insert redacted site photos, Buspro cabinet, Fire Alarm panel]*

---

## 12. Repository Structure

```
industrial-automation-and-bms-2023-siwes/
├── README.md
├── LICENSE
├── docs/
│   ├── SIWES_Technical_Report_2023.pdf
│   ├── CCTV_System_Architecture.md
│   ├── Access_Control_Systems.md
│   ├── Fire_Alarm_Systems.md
│   └── HDL_Buspro_Home_Automation.md
├── media/
│   ├── site_photos/
│   ├── software_screenshots/
│   └── network_diagrams/
└── configs/
    └── RS485_Buspro_Wiring_Topology.md
```

---

## 13. License

MIT License — see [LICENSE](LICENSE) for details.

---

## 14. Contact

**Toluwanimi Jesusina**
- Email: [jesusinatoluwanimi@gmail.com](mailto:jesusinatoluwanimi@gmail.com)
- LinkedIn: [linkedin.com/in/toluwanimi-jesusina](https://linkedin.com/in/your-profile)
```
