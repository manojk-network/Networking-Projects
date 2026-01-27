# Single-Area OSPF Configuration – Cisco Packet Tracer

## Project Overview
This project demonstrates the configuration of **single-area OSPF (Open Shortest Path First)** in Cisco Packet Tracer.  
Three routers are used to connect three separate LANs using serial point-to-point links.  
All router configurations are done using the **CLI**, while PCs are configured using the **GUI**.

---

## Network Topology
- 3 Routers (Cisco 2901)
- 3 Switches (2960)
- 3 PCs
- Serial links between routers
- One LAN per router

All routers participate in **OSPF Area 0**.

---

## IP Addressing Scheme

### LAN Networks
| Router | Interface | IP Address | Subnet Mask |
|------|---------|-----------|------------|
| R0 | G0/0 | 192.168.10.10 | 255.255.255.0 |
| R1 | G0/0 | 192.168.20.10 | 255.255.255.0 |
| R2 | G0/0 | 192.168.30.10 | 255.255.255.0 |

### Serial Networks
| Link | Network | Subnet |
|----|-------|--------|
| R0–R1 | 192.168.40.0 | /30 |
| R1–R2 | 192.168.50.0 | /30 |
| R0–R2 | 192.168.60.0 | /30 |

---

## PC Configuration (GUI)

| PC | IP Address | Subnet Mask | Default Gateway |
|--|-----------|-------------|----------------|
| PC1 | 192.168.10.1 | 255.255.255.0 | 192.168.10.10 |
| PC2 | 192.168.20.1 | 255.255.255.0 | 192.168.20.10 |
| PC3 | 192.168.30.1 | 255.255.255.0 | 192.168.30.10 |

---

## Router Configuration

### Router 0
- enable
- configure terminal
- hostname R0

- interface g0/0
- ip address 192.168.10.10 255.255.255.0
- no shutdown

- interface s0/0/0
- ip address 192.168.40.1 255.255.255.252
- clock rate 64000
- no shutdown

- interface s0/0/1
- ip address 192.168.60.1 255.255.255.252
- clock rate 64000
- no shutdown

- router ospf 1
- router-id 1.1.1.1
- network 192.168.10.0 0.0.0.255 area 0
- network 192.168.40.0 0.0.0.3 area 0
- network 192.168.60.0 0.0.0.3 area 0

---

### Router 1
- enable
- configure terminal
- hostname R1

- interface g0/0
- ip address 192.168.20.10 255.255.255.0
- no shutdown

- interface s0/0/0
- ip address 192.168.40.2 255.255.255.252
- no shutdown

- interface s0/0/1
- ip address 192.168.50.1 255.255.255.252
- clock rate 64000
- no shutdown

- router ospf 1
- router-id 2.2.2.2
- network 192.168.20.0 0.0.0.255 area 0
- network 192.168.40.0 0.0.0.3 area 0
- network 192.168.50.0 0.0.0.3 area 0


---

### Router 2
- enable
- configure terminal
- hostname R2

- interface g0/0
- ip address 192.168.30.10 255.255.255.0
- no shutdown

- interface s0/0/0
- ip address 192.168.50.2 255.255.255.252
- no shutdown

- interface s0/0/1
- ip address 192.168.60.2 255.255.255.252
- no shutdown

- router ospf 1
- router-id 3.3.3.3
- network 192.168.30.0 0.0.0.255 area 0
- network 192.168.50.0 0.0.0.3 area 0
- network 192.168.60.0 0.0.0.3 area 0

---

## Verification Commands
- show ip ospf neighbor
- show ip route ospf
- ping <destination-ip>

Successful OSPF neighbors and `O` routes confirm correct configuration.

---
Screenshots
- ### Topology-with-labels
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0c5ef7fec2488eb996116366fc1bd301a6647c26/Single-Area%20OSPF%20Configuration/Screenshots/Topology%20with%20labels.png)

- ### PC0-IP-Configuration
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0c5ef7fec2488eb996116366fc1bd301a6647c26/Single-Area%20OSPF%20Configuration/Screenshots/PC0%20GUI%20config.png)

- ### PC1-IP-Configuration
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0c5ef7fec2488eb996116366fc1bd301a6647c26/Single-Area%20OSPF%20Configuration/Screenshots/PC0%20GUI%20config.png)

- ### PC2-IP-Configuration
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0c5ef7fec2488eb996116366fc1bd301a6647c26/Single-Area%20OSPF%20Configuration/Screenshots/PC0%20GUI%20config.png)

- ## OSPF Neighbors
![img alt](https://github.com/manojk-network/Networking-Projects/blob/bc65df56ef27250ac65a0f4b4e6bce67f3e745ce/Single-Area%20OSPF%20Configuration/Screenshots/OSPF%20neighbors.png)

- ## Ping Test
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0c5ef7fec2488eb996116366fc1bd301a6647c26/Single-Area%20OSPF%20Configuration/Screenshots/PC-to-PC%20Ping.png)

Youtube Video
https://youtu.be/6Kq6Pc4xXaY

## Conclusion
In this project, a single-area OSPF network was successfully implemented using three routers and three LANs.  
Dynamic routing allowed all networks to learn routes automatically, and end-to-end connectivity was verified through ping tests.  
This lab demonstrates a fundamental enterprise routing setup using OSPF and serial point-to-point links.

---
