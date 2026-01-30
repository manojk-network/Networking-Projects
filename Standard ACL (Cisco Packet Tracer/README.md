# Standard ACL Configuration using Cisco Packet Tracer

## Project Overview
This project demonstrates the implementation of a Standard Access Control List (ACL) in Cisco Packet Tracer to control access to a server based on source IP addresses.

Standard ACLs are used to permit or deny traffic by evaluating only the source IP address and are typically placed close to the destination network.

---

## Project Objective
- Allow PC0 from LAN 1 to access the Server in LAN 2
- Block PC1 from accessing the Server
- Leave PC2 unaffected (dummy host)
- Apply Standard ACL using Cisco-recommended practices

---

## Network Topology Overview
LAN 1:
- PC0
- PC1
- Switch
- Router0

LAN 2:
- PC2 (dummy)
- Server
- Switch
- Router1

Interconnection:
- Router0 and Router1 connected using Gigabit Ethernet crossover cable

---

## IP Addressing Table

### LAN 1
+---------+---------------+-------------------+------------------+
| Device  | IP Address    | Subnet Mask       | Default Gateway  |
+---------+---------------+-------------------+------------------+
| PC0     | 192.168.10.1  | 255.255.255.0     | 192.168.10.10   |
| PC1     | 192.168.10.2  | 255.255.255.0     | 192.168.10.10   |
| Router0 | 192.168.10.10 | 255.255.255.0     | N/A             |
+---------+---------------+-------------------+------------------+

### LAN 2
+---------+-----------+---------------+------------------+
| Device  | IP Address| Subnet Mask   | Default Gateway  |
+---------+-----------+---------------+------------------+
| PC2     | 10.0.0.1  | 255.0.0.0     | 10.0.0.10       |
| Server  | 10.0.0.2  | 255.0.0.0     | 10.0.0.10       |
| Router1 | 10.0.0.10 | 255.0.0.0     | N/A             |
+---------+-----------+---------------+------------------+

### Router-to-Router Link
+------------+---------------+---------------+
| Interface  | IP Address    | Subnet Mask   |
+------------+---------------+---------------+
| R0 G0/1    | 172.16.10.1   | 255.255.0.0   |
| R1 G0/1    | 172.16.10.2   | 255.255.0.0   |
+------------+---------------+---------------+

---

## Configuration Steps

### Step 1: PC and Server Configuration
- All PCs and Server are configured using GUI
- Static IP addressing is used
- DNS and HTTP services are enabled on the server

---

## Router Configuration

### Router0 Configuration
enable
configure terminal
hostname Router0

interface gigabitEthernet0/0
 ip address 192.168.10.10 255.255.255.0
 no shutdown
 exit

interface gigabitEthernet0/1
 ip address 172.16.10.1 255.255.0.0
 no shutdown
 exit

ip route 10.0.0.0 255.0.0.0 172.16.10.2
exit

---

### Router1 Configuration
enable
configure terminal
hostname Router1

interface gigabitEthernet0/0
 ip address 10.0.0.10 255.0.0.0
 no shutdown
 exit

interface gigabitEthernet0/1
 ip address 172.16.10.2 255.255.0.0
 no shutdown
 exit

ip route 192.168.10.0 255.255.255.0 172.16.10.1
exit

---

## Standard ACL Configuration (Professor Method)
Objective:
- Permit PC0 (192.168.10.1)
- Deny PC1 (192.168.10.2)
- Apply ACL outbound on Router1 LAN interface

Commands:
enable
configure terminal

ip access-list standard 10
10 permit 192.168.10.1 0.0.0.0
exit

ip access-list standard 10
20 deny 192.168.10.2 0.0.0.0
exit

interface gigabitEthernet0/0
 ip access-group 10 out
 exit

exit

---

## ACL Verification
show ip access-list

Expected Output:
Standard IP access list 10
    10 permit host 192.168.10.1
    20 deny host 192.168.10.2

---

## Verification Results
+-------+-------------+----------+
| Source| Destination | Result   |
+-------+-------------+----------+
| PC0   | Server      | Allowed  |
| PC1   | Server      | Blocked  |
| PC2   | Server      | Allowed  |
+-------+-------------+----------+

---

## Video Demo
https://youtu.be/tEOGbLSww2Y

---

## Conclusion
This project demonstrates how Standard ACLs can be used to enforce basic network security by controlling access based on source IP addresses. It serves as a foundation for advanced security concepts such as Extended ACLs and firewall configurations.

