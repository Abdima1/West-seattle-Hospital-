Hospital Network Project Documentation
🏥 Project Title

Secure Hospital Network with Site-to-Site VPN, Redundancy, and Layer 3 Switching

📌 Overview

This project simulates a hospital enterprise network connecting a main site (HQ) with a branch site using secure WAN technologies. The design ensures:

Secure communication (IPsec VPN)
High availability (redundant links)
Efficient bandwidth usage (QoS)
Centralized logging (Syslog)
Network segmentation (VLANs)
🧱 Network Architecture

The topology consists of:

Core Layer (Layer 3 Switches)
Access Layer (Layer 2 Switches)
WAN Routers (Site-to-Site connectivity)
Server Farm (Web, File, DNS, DHCP)
Key Components:
Layer 3 Switches (Inter-VLAN routing)
Access Switches (end devices)
Routers (WAN + VPN)
Servers (central services)
🌐 IP Addressing Scheme
LAN (VLANs)
VLAN	Network	Gateway
VLAN 5	192.168.1.0/26	192.168.1.1
VLAN 10	192.168.1.64/26	192.168.1.65
VLAN 15	192.168.1.128/26	192.168.1.129
VLAN 20	192.168.2.0/26	192.168.2.1
VLAN 25	192.168.2.64/26	192.168.2.65
VLAN 30	192.168.2.128/26	192.168.2.129
WAN Links (/30)
Link	Network
R1–R2	10.0.0.0/30
R1–R3	10.0.0.4/30
R2–R4	10.0.0.8/30
R3–R4	10.0.0.12/30
🔐 Implemented Technologies
🔹 1. VLAN & Inter-VLAN Routing
VLAN segmentation for departments
Routing handled by Layer 3 switches using SVIs

Example:

interface vlan 5
ip address 192.168.1.1 255.255.255.192
no shutdown
🔹 2. EtherChannel (Link Aggregation)
Combined multiple physical links into one logical link
Increased bandwidth + redundancy
interface range fa0/4-5
channel-group 1 mode active
🔹 3. OSPF (Dynamic Routing)
Enabled routing between sites
Fast convergence
router ospf 1
network 10.0.0.0 0.0.0.255 area 0
🔹 4. Site-to-Site IPsec VPN
Secures communication between HQ and branch
Encrypts sensitive hospital data

Key features:

ISAKMP (Phase 1)
IPsec (Phase 2)
Pre-shared key authentication
🔹 5. QoS (Quality of Service)
Prioritized critical traffic (e.g., medical systems, VoIP)
Reduced latency for important services
🔹 6. Syslog (Monitoring)
Central logging server for network events
Helps in troubleshooting and auditing
logging host 192.168.x.x
🔹 7. SSH (Secure Remote Access)
Secure device management
Disabled Telnet
ip domain-name hospital.local
crypto key generate rsa
transport input ssh
🖥️ Server Infrastructure
Server	Function
Web Server	Internal hospital portal
File Server	Medical records storage
DNS Server	Name resolution
DHCP Server	Automatic IP assignment
🔁 Redundancy & High Availability
Multiple WAN paths between routers
EtherChannel between switches
OSPF for dynamic failover
🔒 Security Features
IPsec VPN encryption
SSH for secure management
VLAN segmentation
Controlled trunking
✅ Testing & Verification
✔ Ping between VLANs
✔ VPN tunnel verification
✔ OSPF neighbor adjacency
✔ EtherChannel status
✔ SSH access
✔ Syslog messages received
🚀 Conclusion

This project demonstrates a real-world enterprise hospital network with:

Secure communication (VPN)
Scalable design
High availability
Efficient traffic management
