# 🏥 Hospital Network Simulation Project

---

## ✔️ **Overview**
This project simulates a **secure and scalable hospital network** connecting a **main site (HQ)** with a **branch site**.

✔️ Secure communication (IPsec VPN)  
✔️ Redundancy and failover  
✔️ Traffic optimization (QoS)  
✔️ Network segmentation (VLANs)  

---

## ✔️ **Network Topology**

[![Topology]
(./images/topology.png)](./images/topology.png)<img width="620" height="292" alt="image" src="https://github.com/user-attachments/assets/68f703fd-51eb-4aff-bb42-26a833dfccde" />

✔️ Click the image to view full size

---

## ✔️ **Network Architecture**

✔️ Core Layer → Layer 3 Switches (Inter-VLAN Routing)  
✔️ Access Layer → Layer 2 Switches  
✔️ WAN Layer → Redundant routers  
✔️ Server Farm → Centralized services  

---

## ✔️ **IP Addressing Scheme**

### ✔️ **VLANs**

| ✔️ VLAN | ✔️ Network | ✔️ Gateway |
|--------|-----------|-----------|
| 5  | 192.168.1.0/26   | 192.168.1.1 |
| 10 | 192.168.1.64/26  | 192.168.1.65 |
| 15 | 192.168.1.128/26 | 192.168.1.129 |
| 20 | 192.168.2.0/26   | 192.168.2.1 |
| 25 | 192.168.2.64/26  | 192.168.2.65 |
| 30 | 192.168.2.128/26 | 192.168.2.129 |

---

### ✔️ **WAN Links (/30)**

| ✔️ Link | ✔️ Network |
|--------|-----------|
| R1–R2 | 10.0.0.0/30 |
| R1–R3 | 10.0.0.4/30 |
| R2–R4 | 10.0.0.8/30 |
| R3–R4 | 10.0.0.12/30 |

---

## ✔️ **Technologies Implemented**

### ✔️ **VLAN & Inter-VLAN Routing**

interface range fa0/4-5
 channel-group 1 mode active

interface vlan 5
 ip address 192.168.1.1 255.255.255.192

✔️ Site-to-Site IPsec VPN

✔️ Secure communication between HQ and branch
✔️ Data encryption using IPsec
✔️ Pre-shared key authentication

✔️ QoS (Quality of Service)

✔️ Prioritized critical hospital traffic
✔️ Reduced latency for important services
✔️ Syslog
logging host 192.168.x.x
✔️ SSH Configuration
ip domain-name hospital.local
crypto key generate rsa
line vty 0 4
 transport input ssh
✔️ Server Infrastructure
✔️ Server	✔️ Role
Web Server	Internal portal
File Server	Medical records
DNS Server	Name resolution
DHCP Server	IP assignment
✔️ Redundancy Features

✔️ Multiple WAN links
✔️ EtherChannel (link aggregation)
✔️ OSPF dynamic failover

✔️ Security Features

✔️ IPsec VPN
✔️ SSH secure access
✔️ VLAN segmentation

✔️ Testing & Verification

✔️ Inter-VLAN connectivity
✔️ VPN tunnel verification
✔️ OSPF adjacency
✔️ EtherChannel status
✔️ SSH access
✔️ Syslog logs

✔️ Conclusion

✔️ Built a real-world enterprise hospital network
✔️ Implemented security, scalability, and redundancy
✔️ Strengthened practical networking skills

✔️ Author

Abdimalik Rashid
🔗 (https://www.linkedin.com/in/abdimalik-mohamed-rashid-7427b9328/)
