# DHCP LAN Project

## 📌 Project Overview
This project demonstrates a **LAN with DHCP server** using Cisco Packet Tracer.  
The goal is to configure a router, switch, DHCP server, and two PCs so that IPs are **automatically assigned** and all devices can communicate.

**Skills Learned:**  
- DHCP server configuration  
- LAN setup  
- Router interface configuration  
- Connectivity verification  

---

## 🧱 Network Topology
**Devices used:**
- 1 Router (Router0)  
- 1 Switch (Switch0)  
- 1 DHCP Server  
- 2 PCs (PC0, PC1)  

**Connections:**
- Router ↔ Switch → Copper Straight-Through  
- Switch ↔ PCs / DHCP Server → Copper Straight-Through
  
![img alt](https://github.com/manojk-network/Networking-Projects/blob/988fa6abc6b36eafbf8cd253d56cdae96e41a7f1/DHCP%20LAN/Screenshots/Topology.png)

## 🌐 IP Address Plan

| Device      | Interface | IP Address           | Subnet Mask       | Default Gateway |
|------------|-----------|-------------------|-----------------|----------------|
| Router0    | G0/0      | 192.168.1.1        | 255.255.255.0    | —              |
| DHCP Server| NIC       | 192.168.1.10       | 255.255.255.0    | 192.168.1.1    |
| PC0        | NIC       | 192.168.1.20       | 255.255.255.0    | 192.168.1.1    |
| PC1        | NIC       | 192.168.1.21       | 255.255.255.0    | 192.168.1.1    |

---

## Router Configuration (CLI)

- enable
- configure terminal
- hostname Router0
- interface g0/0
- ip address 192.168.1.1 255.255.255.0
- no shutdown
- exit
  
![img alt](https://github.com/manojk-network/Networking-Projects/blob/356a461ed1bd1d01f9d096392eb651957af345c4/DHCP%20LAN/Screenshots/Router%20CLI.png)

## DHCP Server Configuration

Click DHCP Server → Config → DHCP
- Create pool:

- Pool Name: LAN2
- Default Gateway: 192.168.1.1
- DNS Server: 8.8.8.8
- Start IP: 192.168.1.20
- Max Users: 50
- Subnet Mask: 255.255.255.0
- Enable DHCP

![img alt](https://github.com/manojk-network/Networking-Projects/blob/988fa6abc6b36eafbf8cd253d56cdae96e41a7f1/DHCP%20LAN/Screenshots/DHCP%20Config.png)

## PC Configuration
- PC0 → IP Configuration → DHCP → Assigned: 192.168.1.20
![img alt](https://github.com/manojk-network/Networking-Projects/blob/988fa6abc6b36eafbf8cd253d56cdae96e41a7f1/DHCP%20LAN/Screenshots/PC0%20Confg.png)

- PC1 → IP Configuration → DHCP → Assigned: 192.168.1.21
![img alt](https://github.com/manojk-network/Networking-Projects/blob/988fa6abc6b36eafbf8cd253d56cdae96e41a7f1/DHCP%20LAN/Screenshots/PC1.png)

## Verification & Testing

### From PC0:
- ping 192.168.1.1       # Router
- ping 192.168.1.21      # PC1
- ping 192.168.1.10      # DHCP Server
  
![img alt](https://github.com/manojk-network/Networking-Projects/blob/988fa6abc6b36eafbf8cd253d56cdae96e41a7f1/DHCP%20LAN/Screenshots/Ping%20Test.png)

## YouTube Video Demo

https://youtu.be/fJkizMJ5P1A
