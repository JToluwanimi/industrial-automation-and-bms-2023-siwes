# ABB Distribution Panel — HDL Buspro Wiring

## Panel Layout

```
+----------------------------------------------------------+
|                    ABB DISTRIBUTION PANEL                |
|                                                          |
|  +-----------------------------------------------------+ |
|  | HDL Buspro Gateway (HDL-MBUS01IP.431)               | |
|  | - RS485 bus connection                              | |
|  | - Ethernet (UDP/IP)                                 | |
|  +-----------------------------------------------------+ |
|                                                          |
|  +-----------------------------------------------------+ |
|  | HDL Relay Modules (HDL-MR0816.432) - 8/12 channel   | |
|  +-----------------------------------------------------+ |
|                                                          |
|  +-----------------------------------------------------+ |
|  | HDL Dimmer Modules (HDL-MD0403.432) - 4 channel     | |
|  +-----------------------------------------------------+ |
|                                                          |
|  +-----------------------------------------------------+ |
|  | ABB Circuit Breakers (Main + MCBs + RCDs)           | |
|  +-----------------------------------------------------+ |
|                                                          |
|  +-----------------------------------------------------+ |
|  | HDL Power Supply (MSP750.431) - 24V DC              | |
|  +-----------------------------------------------------+ |
|                                                          |
|  +-----------------------------------------------------+ |
|  | Terminal Blocks - D+ / D- / COM / +24V              | |
|  +-----------------------------------------------------+ |
+----------------------------------------------------------+
```

## RS485 Bus Wiring

| Parameter | Value |
|-----------|-------|
| Cable | HDL Buspro/KNX专用电缆 (twisted pair) |
| Impedance | 120 Ohm |
| Topology | Daisy-chain (hand-in-hand) |
| Max length | 1,200 m per subnet |
| Termination | 120 Ohm at both ends |
| Protocol | CSMA/CD |

## My Involvement

- Assisted with DIN-rail mounting of HDL modules
- Traced RS485 bus lines through terminal blocks
- Observed panel layout and power distribution
- Documented wiring for future reference
```
