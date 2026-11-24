# Network Topology

## CCTV Network

See [CCTV_System_Architecture.md](CCTV_System_Architecture.md) for the full topology diagram.

## HDL Buspro Network

See [HDL_Buspro_Home_Automation.md](HDL_Buspro_Home_Automation.md) for the RS485 bus topology.

## Network Parameters (Sanitized)

Client-specific IP addresses and configurations have been removed. The following are generic defaults used in Dahua deployments:

- Subnet: 192.168.1.0/24 (typical)
- Camera IPs: 192.168.1.101–120
- NVR IP: 192.168.1.200

## Structured Cabling

- **Cat6 Ethernet** for IP cameras and PoE
- **Fire-rated cable** for fire alarm loops
- **RS485 twisted pair** for Buspro bus
- **Conduit** for cable protection in exposed areas

## Notes

- All equipment rack-mounted in a single server cabinet
- UPS-backed power for NVR and alarm panels
- Cable management: labelled at both ends
```
