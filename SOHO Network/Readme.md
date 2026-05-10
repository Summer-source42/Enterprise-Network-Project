XYZ Company Branch Office Network

Business Scenario
XYZ Company is a fast growing business based in eastern Australia with over 2 million customers. All operations were running from a single headquarters, and the company decided to open a branch office near a local village called Bon Alba to reduce load on HQ and serve customers in the area.
The branch network was required to operate completely independently from HQ separate addressing, separate infrastructure. I was brought in as the network engineer to design and implement it from scratch.

##Requirements

#### One Cisco router, one Cisco switch
#### Three departments, each isolated in its own VLAN
#### Wireless access in every department via access points
#### All end devices must receive IP addresses automatically (DHCP)
#### All departments must be able to communicate with each other (inter-VLAN routing)
#### Base network assigned by ISP: 192.168.1.0
