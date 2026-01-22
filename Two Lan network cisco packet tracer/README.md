# Two LAN Inter-LAN Routing using Cisco Packet Tracer

## Project Overview
This project demonstrates how to design and configure two separate Local Area Networks (LANs) using a router, switches, and PCs in Cisco Packet Tracer. The router is configured using CLI to enable communication between both LANs (inter-LAN routing). Connectivity is verified using ping tests.

This project focuses on fundamental networking concepts and serves as a foundation for advanced topics such as VLANs, inter-VLAN routing, and cloud networking.

---

## Network Topology
- 1 Router (Cisco 2901)
- 2 Switches (Cisco 2960)
- 4 PCs (2 PCs per LAN)

Each LAN is connected to the router through a dedicated router interface.

---

## IP Addressing Scheme

### LAN 1
- Router Interface (Gi0/0): 192.168.1.1 /24
- PC0: 192.168.1.2 /24
- PC1: 192.168.1.3 /24
- Default Gateway: 192.168.1.1

### LAN 2
- Router Interface (Gi0/1): 192.168.2.1 /24
- PC2: 192.168.2.2 /24
- PC3: 192.168.2.3 /24
- Default Gateway: 192.168.2.1

---

## Router Configuration (CLI Commands)

enable
configure terminal
hostname R1

interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface GigabitEthernet0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit


Explanation:
- `enable` → enters privileged mode
- `configure terminal` → enters configuration mode
- `hostname R1` → sets router name
- `interface` → selects router interface
- `ip address` → assigns IP and subnet mask
- `no shutdown` → activates interface

---

## PC Configuration
Each PC is manually configured from:
Desktop → IP Configuration

- IP Address
- Subnet Mask
- Default Gateway (router interface IP)

---

## Verification and Testing

### Ping Tests Used

#### Intra-LAN Test
From PC0:
ping 192.168.1.3


From PC2:
ping 192.168.2.3


#### Inter-LAN Test
From PC0:
ping 192.168.2.2


From PC3:
ping 192.168.1.2


All ping tests were successful, confirming proper inter-LAN routing.

---

## Screenshots Included
The following screenshots are added to demonstrate the working project:
- ## Network topology view
![img alt](https://github.com/manojk-network/Networking-Projects/blob/8dc2a857027c635872619ef2e4f312088687f53f/Two%20Lan%20network%20cisco%20packet%20tracer/Screenshots/Screenshot%202026-01-22%20202557.png)
- ## Successful ping test results
![img alt](https://github.com/manojk-network/Networking-Projects/blob/8dc2a857027c635872619ef2e4f312088687f53f/Two%20Lan%20network%20cisco%20packet%20tracer/Screenshots/Screenshot%202026-01-22%20202655.png)
- ## Router CLI configuration
![img alt](https://github.com/manojk-network/Networking-Projects/blob/8dc2a857027c635872619ef2e4f312088687f53f/Two%20Lan%20network%20cisco%20packet%20tracer/Screenshots/Screenshot%202026-01-22%20202745.png)

---

## Video Demo
The project was demonstrated in Cisco Packet Tracer by:
- Configuring router interfaces using CLI
- Assigning IP addresses to PCs
- Testing connectivity using ping commands

https://youtu.be/6dFjcC3I2lI

---

## Conclusion
In this project, two separate LANs were successfully configured and connected using a router. Inter-LAN communication was enabled through proper IP addressing and router interface configuration. This project strengthens the understanding of basic networking, routing concepts, and real-world network troubleshooting.

---

## Tools Used
- Cisco Packet Tracer

---

