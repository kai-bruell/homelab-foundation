# Homelab Foundation

This repository documents the physical hardware setup and the network topology of my home lab.

## Core Architecture
The network is built around an **OPNsense** firewall using a **FritzBox 7590** as a DSL modem via PPPoE-Passthrough to avoid Double-NAT, while maintaining analog telephony functions.

### Network Topology (Physical & Logical)

| From (Device) | Port | To (Device) | Port | VLAN / Mode | Purpose |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Wall (TAE)** | – | **FritzBox** | **DSL** | – | DSL Signal Input |
| **FritzBox** | **LAN 1** | **Switch** | **Port 1** | **70 (Modem)** | Raw DSL Bridge to Firewall |
| **OPNsense** | **WAN** | **Switch** | **Port 2** | **70 (Modem)** | PPPoE Dial-in (Public IP) |
| **OPNsense** | **LAN** | **Switch** | **Port 3** | **10 (LAN)** | Firewall Gateway Output |
| **FritzBox** | **WAN** | **Switch** | **Port 4** | **10 (LAN)** | IP-Client for Telephony |
| **FritzBox** | **FON 1/2**| **Analog Phone**| – | – | Analog Handset |

### Key Configurations
- **FritzBox 7590:** Set to "IP-Client" mode via WAN port; PPPoE-Passthrough enabled.
- **VLAN 70:** Isolated "Outside" segment for DSL synchronization.
- **VLAN 10:** Internal trusted network for clients and management.
- **OPNsense Outbound NAT:** Static Port enabled for FritzBox IP to ensure VoIP stability.

## Hardware Components
* **Modem/AP:** AVM FritzBox 7590
* **Firewall:** [Dein OPNsense Hardware Modell hier einfügen]
* **Switch:** [Dein Managed Switch Modell hier einfügen]
