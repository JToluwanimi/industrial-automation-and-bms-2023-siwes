# CCTV System Architecture

## Components

### Cameras
- **Bullet** — Outdoor perimeter
- **Dome** — Indoor ceilings
- **PTZ** — Pan-tilt-zoom for wide areas

### Recording
- **NVR:** Dahua DHI-DSS7016DR-S2 (16 bays)
- **Drives:** Seagate EXOS enterprise HDDs (16 TB per drive, assumed)

### Network
- **PoE Switch:** Dahua 24-port
- **Cabling:** Cat6 Ethernet
- **Backbone:** Gigabit Ethernet

### Software
- **VMS:** Dahua DSS

## Installation Lifecycle

1. **Site survey** — Identify blind spots, entry/exit points
2. **Camera selection** — Match resolution/range to area
3. **Wiring plan** — Cable routes, conduit, PoE budget
4. **Mounting** — Brackets, poles, weatherproofing
5. **Connection** — Patch panel → PoE switch → NVR
6. **Configuration** — IP addresses, recording schedules
7. **Testing** — Live view, playback, remote access
8. **Maintenance** — Firmware updates, drive health checks

## My Involvement

- **Hands-on:** Assisted with NVR rack installation, hard drive installation and labeling, PoE switch deployment
- **Assisted:** Field camera mounting on outdoor poles
- **Observed:** DSS software configuration for multi-camera grid
- **Studied:** Dahua proprietary management interface
```
