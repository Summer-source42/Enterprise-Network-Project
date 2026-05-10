# Cisco Network Design & Implementation Projects

**CCNA Certified** | Designed, configured, and verified from scratch using Cisco Packet Tracer

This repository documents two end-to-end network design and implementation projects. Each one starts from a real-world business scenario with a defined set of requirements — I handled everything from topology design and IP addressing to full device configuration and connectivity verification.

The goal isn't just to show that I passed an exam. It's to show that I can take a problem, plan a solution, and actually build it.

---

## Projects

| # | Project | Complexity | Key Protocols & Features |
|---|---------|------------|--------------------------|
| 1 | [SOHO Network Network](./SOHO%20Network) | Foundational | VLANs, Inter-VLAN Routing, DHCP, Wireless |
| 2 | [Vic Modern Hotel - Multi-Floor Network](./) | Intermediate | OSPF, SSH, Port Security, VLANs, DHCP, Wireless |

---

## What Each Project Covers

### Design Phase
- Analyzed business requirements and translated them into a network topology
- Selected appropriate devices (routers, switches, access points)
- Performed manual subnetting from a given base network
- Allocated IP address ranges per department/VLAN

### Implementation Phase
- Built the full topology in Cisco Packet Tracer
- Configured VLANs, trunk ports, and access ports on switches
- Configured inter-VLAN routing using router-on-a-stick
- Set up DHCP server on routers with per-VLAN address pools
- Configured wireless access points with WPA2-PSK authentication
- (Project 2) Connected routers via serial DCE cables with clock rate
- (Project 2) Deployed OSPF across all three routers
- (Project 2) Configured SSH for secure remote login on all routers
- (Project 2) Implemented port security with sticky MAC and shutdown violation

### Verification Phase
- Confirmed DHCP address assignment across all VLANs
- Tested inter-VLAN and inter-floor connectivity via ping
- Verified OSPF adjacency formation and route propagation
- Tested SSH remote login from IT department Test PC
- Verified port security via `show port-security`

---

## Tools & Environment

- **Cisco Packet Tracer**  network simulation and verification
- **Devices used:** Cisco 2911 Router, Cisco 2960 Switch, generic access points
- **Protocols:** VLANs (802.1Q), OSPF, DHCP, SSH, WPA2-PSK, STP 

---

## Certifications

- **Cisco Certified Network Associate (CCNA)**

---

## Repository Structure

```
cisco-networking-labs/
│
├── README.md
│
├── SOHO-network/
│   ├── README.md
│   ├── SOHO.pkt
│   └── configs/
│       ├── router-config.txt
│       └── switch-config.txt
│
└── hotel-network/
    ├── README.md
    ├── Hotel_Management.pkt
    └── configs/
        ├── floor1-router.txt
        ├── floor2-router.txt
        ├── floor3-router.txt
        └── switches/
            ├── floor1-switch.txt
            ├── floor2-switch.txt
            └── floor3-switch.txt
```

> `.pkt` Packet Tracer files are included inside each project folder alongside the README.
