# HDL Buspro Home Automation System

## Overview

The HDL Buspro system is a modular building automation solution operating on a dedicated RS485 bus. It manages lighting, blinds, HVAC, TV, background music, home theater, security, irrigation, and power metering.

## Key Technical Features

- **Field Bus:** RS485 twisted-pair cable
- **Backbone:** UDP/IP standard network
- **Subnet Addressing:** `Subnet/Device` (e.g., "1/2")
- **Max Subnets:** 254
- **Max Devices per Subnet:** 63
- **Max Bus Length:** 1,200 m per subnet

## Component Categories

### Control Panels
- Touch screen panels
- Multi-function LCD panels
- Mechanical button panels
- Granite Display (top-tier)

### Controllers / Actuators
- Relay modules (4/8/12 channel)
- LED dimmers
- Curtain controllers
- HVAC controllers
- Logic controllers

### Sensors
- Air quality sensors
- Light sensors
- Multifunctional PIR + LUX + Temp

### Gateways
- HDL system gateway
- KNX-Buspro gateway
- RS232/RS485 converters

### Audio/Video
- Background music player
- Ceiling speakers

### Software
- System software
- HDL ON mobile app
- Commercial building monitoring software

## Wiring Topologies

### Single Subnet

Devices connect in daisy-chain (hand-in-hand) topology. This is the recommended topology for reliability.

### Multi-Subnet

Multiple subnets connect via Ethernet backbone. Each subnet has its own gateway.

## Presentation Evidence

I studied the HDL Buspro system during SIWES 2023 and delivered a technical presentation on its architecture. See: [hdl-buspro-building-automation](https://github.com/YOUR-USERNAME/hdl-buspro-building-automation) for detailed analysis.

## My Involvement

- **Studied:** Architecture and RS485 protocol
- **Assisted:** DIN-rail mounting of modules on ABB panel
- **Observed:** Granite Display configuration
- **Presented:** Delivered technical presentation to peers and supervisors
```
