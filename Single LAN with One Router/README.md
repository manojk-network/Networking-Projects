# Single LAN Network Configuration (Cisco Packet Tracer)
## Project Overview

This project demonstrates a basic Single LAN setup using Cisco Packet Tracer.
The goal is to configure a router, switch, and two PCs so that all devices can communicate within the same local network.

## This project covers:

Basic IP addressing

Router interface configuration

End-to-end connectivity testing

## Network Topology

Devices used:

1 Router

1 Switch

2 PCs

## Connections:

Router ↔ Switch : Copper Straight-Through

Switch ↔ PCs : Copper Straight-Through

## 🌐 IP Addressing Scheme

| Device  | Interface | IP Address     | Subnet Mask       | Default Gateway |
|--------|----------|---------------|------------------|----------------|
| Router0 | G0/0     | 192.168.1.1   | 255.255.255.0    | —              |
| PC0     | NIC      | 192.168.1.2   | 255.255.255.0    | 192.168.1.1    |
| PC1     | NIC      | 192.168.1.3   | 255.255.255.0    | 192.168.1.1    |

## Router Configuration (CLI)
- enable
- configure terminal
- hostname Router0
- interface gigabitEthernet0/0
- ip address 192.168.1.1 255.255.255.0
- no shutdown
- exit
- show ip interface brief
## Expected result:
- Interface status should be up/up

## PC Configuration
### PC0

IP Address: 192.168.1.2

Subnet Mask: 255.255.255.0

Default Gateway: 192.168.1.1

### PC1

IP Address: 192.168.1.3

Subnet Mask: 255.255.255.0

Default Gateway: 192.168.1.1

(Insert PC IP configuration screenshots here)

## Verification & Testing
From Router0:
ping 192.168.1.2
ping 192.168.1.3

From PC0:
ping 192.168.1.1
ping 192.168.1.3

From PC1:
ping 192.168.1.1
ping 192.168.1.2


All pings should return Reply confirming successful LAN connectivity.

## Screenshots
### Topology 
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0842c29a7190fe2d8488078600fd91e73f1b05e6/Single%20LAN%20with%20One%20Router/Screenshots/Screenshot%202026-01-24%20220916.png)
### Router config 
![img alt](https://github.com/manojk-network/Networking-Projects/blob/0842c29a7190fe2d8488078600fd91e73f1b05e6/Single%20LAN%20with%20One%20Router/Screenshots/Screenshot%202026-01-24%20221110.png)
### PC IP config
img ![alt](https://github.com/manojk-network/Networking-Projects/blob/833edf7e55c3c041cb064d28d613d4811233d64b/Single%20LAN%20with%20One%20Router/Screenshots/PC%20Config.png) 
### Ping test 
![img alt](https://github.com/manojk-network/Networking-Projects/blob/833edf7e55c3c041cb064d28d613d4811233d64b/Single%20LAN%20with%20One%20Router/Screenshots/Ping.png)
## Video Demo

A short video demo was recorded showing:

Network topology

Router configuration

PC IP configuration

Successful ping tests

https://youtu.be/zbVyYQ_lMYg

🧠 Key Learning Outcomes

Understanding Single LAN architecture

Basic router interface configuration

Importance of default gateway

Verifying network connectivity using ping
