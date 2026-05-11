# Small Office / Home Office (SOHO) Network Design & Implementation
 
Designed and implemented a small branch office network from scratch in Cisco Packet Tracer. The project covers everything from subnetting a given address space to configuring VLANs, inter-VLAN routing, DHCP, and wireless access all on a single router and switch.
 
---
 
## Scenario
 
XYZ Company is based in eastern Australia and handles all operations from a single headquarters serving over 2 million customers. To reduce the pressure on HQ and serve more customers locally, the company decided to open a branch office near a village called Bon Alba.
 
The branch network had to run completely separately from HQ, its own addressing, its own devices, nothing shared. I was given a base network by the ISP and a list of requirements, and built it end to end.
 
---
 
## Network Topology
 
```
            [ Cisco 2911 Router ]
                     |
               GigabitEthernet0/0
               (802.1Q trunk link)
                     |
            [ Cisco 2960 Switch ]
           /          |           \
      Fa0/2-4      Fa0/5-7      Fa0/8-10
      VLAN 10      VLAN 20       VLAN 30
         |            |              |
   [ Admin/IT ]  [ Finance/HR ]  [ CS/Reception ]
   PC, Printer,  PC, Printer,   PC, Printer,
   Access Point  Access Point   Access Point
```
 
> `![Network Topology]()`
 
---
 
## Requirements
 
- One Cisco router and one Cisco switch
- Three departments, each isolated in its own VLAN
- Wireless access in every department via access points
- All devices obtain IP addresses automatically via DHCP
- All departments must be able to communicate with each other
- Base network assigned: `192.168.1.0`
---
 
## IP Addressing & Subnetting
 
Three departments means three subnets. Starting from `192.168.1.0`, I needed to borrow bits from the host portion to create enough subnets. Borrowing 2 bits gives 4 possible subnets, enough to cover all three departments.
 
| Parameter | Value |
|-----------|-------|
| Base Network | 192.168.1.0 |
| Subnets Required | 3 |
| Bits Borrowed | 2 |
| Subnets Available | 2² = 4 |
| New Subnet Mask | 255.255.255.192 (/26) |
| Block Size | 64 |
 
### Subnet Allocation
 
| Department | VLAN | Network | Broadcast | Usable Range | Default Gateway |
|------------|------|---------|-----------|--------------|-----------------|
| Admin / IT | 10 | 192.168.1.0/26 | 192.168.1.63 | .1 – .62 | 192.168.1.1 |
| Finance / HR | 20 | 192.168.1.64/26 | 192.168.1.127 | .65 – .126 | 192.168.1.65 |
| Customer Service / Reception | 30 | 192.168.1.128/26 | 192.168.1.191 | .129 – .190 | 192.168.1.129 |
 
---
