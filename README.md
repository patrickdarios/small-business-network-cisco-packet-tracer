# Design and Implementation of a Small Business Network Using Cisco Packet Tracer

A small business network designed and implemented in Cisco Packet Tracer using VLAN segmentation, VLSM subnetting, inter-VLAN routing, DHCP, static routing, NAT/PAT, basic device security, and simulated Internet connectivity.

## Project Overview

This project simulates a small company's network infrastructure consisting of an ISP Router, Company Router, Company Switch, Administration PCs, Sales PCs, IT PCs, an internal Server, and a Network Printer.

The network uses VLANs to separate departments and VLSM to efficiently allocate IPv4 addresses based on host requirements.

## Network Topology

The network consists of:

- 1 ISP Router
- 1 Company Router
- 1 Company Switch
- 5 Administration PCs
- 8 Sales PCs
- 3 IT PCs
- 1 Internal Server
- 1 Network Printer

### VLANs

| VLAN | Name | Purpose |
|------|------|---------|
| 10 | ADMINISTRATION | Administration PCs |
| 20 | SALES | Sales PCs |
| 30 | IT | IT PCs |
| 40 | SERVICES | Server and Printer |

### VLSM Addressing

| VLAN | Network | Mask | Gateway |
|------|---------|------|---------|
| 20 | 192.168.10.0/28 | 255.255.255.240 | 192.168.10.14 |
| 10 | 192.168.10.16/29 | 255.255.255.248 | 192.168.10.22 |
| 30 | 192.168.10.24/29 | 255.255.255.248 | 192.168.10.30 |
| 40 | 192.168.10.32/29 | 255.255.255.248 | 192.168.10.38 |

The last usable address of each subnet is used as the default gateway.

## Technologies Implemented

- IPv4 addressing
- VLSM subnetting
- VLAN segmentation
- Router-on-a-Stick
- Inter-VLAN routing
- DHCP
- Static routing
- NAT/PAT
- Basic device security
- Internal web/file server
- Network printer
- Simulated Internet connectivity

## Internet Simulation

The ISP Router uses a Loopback interface configured as:

    8.8.8.8/32

This simulates an Internet destination inside Cisco Packet Tracer.

Internet connectivity can therefore be tested from a company PC using:

    ping 8.8.8.8

## Verification Commands

Important Cisco IOS verification commands include:

    show ip interface brief
    show ip route
    show ip dhcp binding
    show ip nat translations
    show vlan brief
    show interfaces trunk
    show running-config

## Project Files

- `packet-tracer/` - Cisco Packet Tracer topology
- `configs/` - Device configurations
- `screenshots/` - Configuration and connectivity evidence

## Author

Patrick

## Disclaimer

This project was created for educational and laboratory purposes using Cisco Packet Tracer. The Internet connection is simulated using an ISP Router and a Loopback interface representing 8.8.8.8.
