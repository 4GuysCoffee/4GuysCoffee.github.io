# Networking & IT Infrastructure

### Overview

The network architecture adopts a best-in-class approach by implementing a 3-tier hierarchical design for the headquarters and a relatively simple design for the branches, widely acknowledged as an industrial best practice for creating reliable, scalable, and cost-effective networks (GeeksforGeeks, 2022). This design optimises network performance, facilitates seamless scalability to accommodate future growth, and ensures cost efficiency in network management and maintenance. The hierarchical structure provides a clear separation of functions, enhancing overall network reliability and robustness.

#### Distribution & Core Layer

* The network infrastructure is designed with a robust and resilient architecture, featuring a single HQ-router complemented by two multilayer switches for efficient inter-VLAN routing and enhanced redundancy through HSRP configuration. An EtherChannel is implemented between the switches to optimise bandwidth and load balancing, significantly boosting overall network performance. The utilisation of subnets and VLANs in tandem forms a multilayer security approach, strategically addressing vulnerabilities in both Layers 2 and 3.

* To future-proof the network for business growth, subnet selection follows Cisco's addressing guide recommendations, employing VLSM while allowing space for growth /16 and /24 for the HQ and various departments, ensuring scalability. Layer 2 security is prioritised with measures like PortFast, BPDUguard, port security, and auto-trunking disabling to fortify against potential attacks.

* Routing is achieved through OSPF, chosen for its compatibility with heterogeneous networks, as opposed to EIGRP, which is limited to homogeneous networks. WLAN security is bolstered with RADIUS server authentication, providing users with unique username and password combinations for heightened access control. For secure site-to-site connections, IPSec VPNs are implemented.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Network Diagram

IMG (Network Diagram)

### Network Specifications

#### Subnet Assignments

IMG (t2.1 & t2.2)

#### IP Addressing Scheme

The devices in the network are assigned the following IP Address range as defined in Table 2.3.

IMG (t2.3)

### System Configurations

#### HQ - Switches & Routers

##### Basic Device Configuration (VLAN Creation for HQ switches)

IMG (Figure 2.1 & 2.2)

##### Multilayer Switch configurations - VLANs, OSPF & HSRP

IMG (Figure 2.3, 2.4 & 2.5)

##### EtherChannel Configuration & Verification

IMG (Figure 2.6, 2.7, 2.8, 2.9, 2.10)

##### WLC Configuration & RADIUS Server Authentication

IMG (Figure 2.11 - 2.18)

#### Branch - Switches & Routers

##### Switch VLANs

table 4, fig 2.19

##### Router

###### SVIs on Router for Inter-VLAN routing

Figure 2.20, 2.21

###### Router as DHCP

Figure 2.22, 2.23

###### Router OSPF verification

Figure 2.24

##### Access Points Configuration

Figure 2.25 - 2.26

##### Access Points Configuration

###### Connectivity between different VLANs

###### HQ LAN

figure 2.27

###### Branch LAN

figure 2.28

###### Connectivity Across LAN

figure 2.29

###### Site-to-site VPN

figure 2.30 - 2.32

###### VPN Verification

figure 2.33