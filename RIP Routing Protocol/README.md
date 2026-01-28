# RIP Routing Protocol – Cisco Packet Tracer Lab
## Overview
This project demonstrates dynamic routing using RIP version 2 between two routers, each connected to its own LAN.
All router configurations are done via CLI, while PCs are configured via GUI. End-to-end connectivity is verified using ICMP ping.
________________________________________
## Topology Summary
•	Router0 → LAN 1 (192.168.1.0/24)
•	Router1 → LAN 2 (192.168.2.0/24)
•	Routers interconnected via GigabitEthernet interfaces
•	Routing protocol: RIP v2
•	Cable connection: Automatic
________________________________________
## IP Addressing
### Router0
Interface	IP Address	Subnet Mask
G0/0 (LAN)	192.168.1.1	255.255.255.0
G0/1 (WAN)	10.0.0.1	255.255.255.252
### Router1
Interface	IP Address	Subnet Mask
G0/0 (LAN)	192.168.2.1	255.255.255.0
G0/1 (WAN)	10.0.0.2	255.255.255.252
________________________________________
### PCs
### LAN 1
PC	IP Address	Subnet Mask	Default Gateway
PC0	192.168.1.2	255.255.255.0	192.168.1.1
PC1	192.168.1.3	255.255.255.0	192.168.1.1

### LAN 2
PC	IP Address	Subnet Mask	Default Gateway
PC2	192.168.2.2	255.255.255.0	192.168.2.1
PC3	192.168.2.3	255.255.255.0	192.168.2.1
________________________________________
### Router Configuration
## Router0
- enable
- configure terminal
  
- interface gigabitEthernet0/0
- ip address 192.168.1.1 255.255.255.0
- no shutdown

- interface gigabitEthernet0/1
- ip address 10.0.0.1 255.255.255.252
- no shutdown

- router rip
- version 2
- no auto-summary
- network 192.168.1.0
- network 10.0.0.0

- end
- write memory
  
## Router1
- enable
- configure terminal

- interface gigabitEthernet0/0
- ip address 192.168.2.1 255.255.255.0
- no shutdown

- interface gigabitEthernet0/1
- ip address 10.0.0.2 255.255.255.252
- no shutdown

- router rip
- version 2
- no auto-summary
- network 192.168.2.0
- network 10.0.0.0

- end
- write memory
________________________________________
### Verification
•	Connectivity: Use ICMP ping between PCs across LANs
•	RIP Verification: View router CLI showing router rip configuration
End-to-end connectivity confirms that RIP routing is working correctly.
________________________________________
## Screenshots 
### 1.	Network Topology Overview
![img alt](https://github.com/manojk-network/Networking-Projects/blob/cdda954c9d9e890d6ca048b4479755726fc83f92/RIP%20Routing%20Protocol/Screenshots/Topology.png)

### 2.	Router0 – RIP v2 Configuration (CLI)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/CLI%20of%20Router0.png)

### 3.	Router1 – RIP v2 Configuration (CLI)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/CLI%20of%20Router1.png)

### 4.	PC0 & PC1 IP Configuration (LAN 1)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/PC0.png)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/PC1.png)

### 5.	PC2 & PC3 IP Configuration (LAN 2)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/PC2.png)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/PC3.png)

### 6.	Inter-LAN Ping Test (Successful)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/f11e9d322a2bcf20f9515f3d2a5342416aa87ee2/RIP%20Routing%20Protocol/Screenshots/Ping%20Test.png)

## Video Demo
https://youtu.be/cpv3PIr43Dc?si=wJc4KnbKDeFMj2ZA
________________________________________
## Key Learnings
•	Configured RIP v2 dynamic routing
•	Learned automatic route exchange between routers
•	Verified end-to-end connectivity using ICMP ping
•	Practiced CLI-based router configuration and PC GUI IP assignment


