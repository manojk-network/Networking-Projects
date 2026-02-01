# Extended ACL Project – Cisco Packet Tracer

## Project Overview
This project demonstrates how to configure **Extended Access Control Lists (ACLs)** to control traffic between two LANs.  

**Goal:**  
- Allow **PC1 and PC2** (LAN1) to access the **server** (LAN2).  
- Deny **PC1 and PC2** from accessing **PC3** (LAN2).  
- PC3 is not blocked from server; it acts as a dummy host.  

This simulates a real-world scenario for **network security, traffic control, and segmentation**.

---

## Network Topology
```
LAN1: PC1, PC2 → Switch → Router0
LAN2: PC3, Server → Switch → Router1
Router0 ↔ Router1 via WAN link (Gigabit/Crossover)
```

---

## IP Addressing Table

```bash
# LAN1
Device      Interface       IP Address       Subnet Mask       Gateway
PC1         NIC             192.168.10.1    255.255.255.0    192.168.10.10
PC2         NIC             192.168.10.2    255.255.255.0    192.168.10.10
Router0     Gig0/0          192.168.10.10   255.255.255.0

# LAN2
Device      Interface       IP Address       Subnet Mask       Gateway
PC3         NIC             10.0.0.1        255.0.0.0        10.0.0.10
Server      NIC             10.0.0.2        255.0.0.0        10.0.0.10
Router1     Gig0/0          10.0.0.10       255.0.0.0

# Router-to-Router Link
Router0     Gig0/1          172.16.10.1     255.255.0.0
Router1     Gig0/1          172.16.10.2     255.255.0.0
Step 1 – Configure PCs and Server

```
```
# LAN1 PCs
PC1> IP: 192.168.10.1   Subnet: 255.255.255.0  Gateway: 192.168.10.10
PC2> IP: 192.168.10.2   Subnet: 255.255.255.0  Gateway: 192.168.10.10

# LAN2
PC3> IP: 10.0.0.1       Subnet: 255.0.0.0      Gateway: 10.0.0.10
Server> IP: 10.0.0.2    Subnet: 255.0.0.0      Gateway: 10.0.0.10

```
```
Step 2 – Router Configuration
# Router0
enable
configure terminal
hostname Router0

interface GigabitEthernet0/0
ip address 192.168.10.10 255.255.255.0
no shutdown
exit

interface GigabitEthernet0/1
ip address 172.16.10.1 255.255.0.0
no shutdown
exit

# Static route to LAN2
ip route 10.0.0.0 255.0.0.0 172.16.10.2
exit
```
```
# Router1
enable
configure terminal
hostname Router1

interface GigabitEthernet0/0
ip address 10.0.0.10 255.0.0.0
no shutdown
exit

interface GigabitEthernet0/1
ip address 172.16.10.2 255.255.0.0
no shutdown
exit
```
```
# Static route to LAN1
ip route 192.168.10.0 255.255.255.0 172.16.10.1
exit
```
```
Step 3 – Extended ACL Configuration
# Router0 – ACL toward Router1
enable
configure terminal

ip access-list extended 101
10 permit ip 192.168.10.0 0.0.0.255 host 10.0.0.2
20 deny ip 192.168.10.0 0.0.0.255 host 10.0.0.1
30 permit ip any any
exit

interface GigabitEthernet0/1
ip access-group 101 out
exit
```
Explanation:

Rule 10: Allows PC1 & PC2 to reach server.

Rule 20: Denies PC1 & PC2 from reaching PC3.

Rule 30: Permits all other traffic to avoid network block.
```
Step 4 – Verification
# Show ACL
show access-lists
```
```
# Test Pings
PC1> ping 10.0.0.2  # Success
PC2> ping 10.0.0.2  # Success
PC1> ping 10.0.0.1  # Blocked
PC2> ping 10.0.0.1  # Blocked
Step 5 – Verification Table
Source   Destination   Result
PC1      Server        Success
PC2      Server        Success
PC1      PC3           Blocked
PC2      PC3           Blocked
```
## Screenshots 
### Topology

![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/Topology.png)

### PC Configurations

![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/PC0%20Config.png)

![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/PC1%20Config.png)

![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/PC2%20Config.png)

### Router0 
![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/Router0%20CLI.png)

### Ping Test Results
![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/PC1%20Config.png)

![img alt](https://github.com/manojk-network/Networking-Projects/blob/4149f4263105fd939fb9456386f763a5299d27b8/Extended%20ACL/Screenshots/PC0%20Ping.png)

## Video Demo
https://youtu.be/HOil-XHJ4F0

## Conclusion
"Extended ACL allows fine-grained control of traffic between hosts and networks. This is essential for network security, traffic management, and segmenting networks in enterprise environments."


