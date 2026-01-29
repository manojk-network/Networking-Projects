# Multi-Area OSPF Configuration – Cisco Packet Tracer

## 📌 Project Overview
This project demonstrates a **Multi-Area OSPF (Open Shortest Path First) implementation** using Cisco Packet Tracer.  
The lab is designed to simulate a **real-world enterprise routing environment** with multiple OSPF areas, ABRs, and a backbone (Area 0).

The objective is to show how large networks are logically segmented using OSPF areas to improve **scalability, stability, and convergence performance**.

---

## 🧠 Why Multi-Area OSPF?
Multi-Area OSPF is used in enterprise and service-provider networks to:
- Reduce routing table size
- Minimize SPF recalculations
- Improve convergence time
- Isolate topology changes
- Scale large networks efficiently

---

## 🗺️ Network Topology
- **Area 1**: LAN + Router0  
- **Area 0 (Backbone)**: Core routers  
- **Area 2**: LAN + Router4  
- **ABRs** connect non-backbone areas to Area 0  
- **Serial WAN links** used between routers  
- **FastEthernet** used for LAN connectivity  

---

## 📊 IP Addressing & Interfaces

### Router Interface Table

| Router  | Interface   | IP Address        | OSPF Area |
|--------|------------|-------------------|----------|
| Router0 | Fa0/0       | 192.168.10.10     | Area 1   |
| Router0 | S0/0/0      | 172.16.10.1       | Area 1   |
| Router1 | S0/0/0      | 172.16.10.2       | Area 1   |
| Router1 | S0/0/1      | 172.17.10.1       | Area 0   |
| Router2 | S0/0/0      | 172.17.10.2       | Area 0   |
| Router2 | S0/0/1      | 172.18.10.1       | Area 0   |
| Router3 | S0/0/0      | 172.18.10.2       | Area 0   |
| Router3 | S0/0/1      | 172.19.10.1       | Area 2   |
| Router4 | Fa0/0       | 192.168.20.10     | Area 2   |
| Router4 | S0/0/0      | 172.19.10.2       | Area 2   |

---

### PC Configuration Table

| PC  | IP Address       | Default Gateway   |
|----|------------------|------------------|
| PC1 | 192.168.10.1     | 192.168.10.10     |
| PC2 | 192.168.20.1     | 192.168.20.10     |

---

## ⚙️ Configuration Example (Router0)

```bash
enable
configure terminal
hostname Router0

interface FastEthernet0/0
 ip address 192.168.10.10 255.255.255.0
 no shutdown
exit

interface Serial0/0/0
 ip address 172.16.10.1 255.255.255.252
 clock rate 64000
 no shutdown
exit

router ospf 1
 router-id 1.1.1.1
 network 192.168.10.0 0.0.0.255 area 1
 network 172.16.10.0 0.0.0.3 area 1
exit
```
## Screenshots
### PC0 Config
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/PC0%20config.png)

### PC1 Config
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/PC1%20Config.png)

### Ping
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/Ping.png)

### R0 OSPF Config
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/R0%20OSPF%20config.png)

### R1 OSPF Config
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/R1%20OSPF%20config.png)

### show ip Route
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/Show%20ip%20route%20OSPF.png)

### Topology
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2210cb675413c9d277219176d1357a1075512755/Multi-Area%20OSPF%20Configuration/Screenshots/Topology.png)

## Video Demo
https://youtu.be/ra0WtPv3EKo

