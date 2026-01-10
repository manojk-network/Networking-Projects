# Wireshark Network Traffic Analysis (Ubuntu)

## Objective
- To analyze real network traffic using Wireshark and understand normal TCP, DNS, and HTTP communication in a Linux virtual machine environment.

## Tools Used
- Wireshark
- Ubuntu Linux (VirtualBox)
- Host machine network access

## Lab Environment
- Operating System: Ubuntu Linux
- Virtualization: VirtualBox
- IP Address (Ubuntu VM): 10.0.2.15

## What I Did
- Captured live network traffic using Wireshark
- Applied protocol filters to isolate specific traffic
- Analyzed TCP communication between client and server

### Observed DNS queries and responses
- Inspected HTTP request and response packets
- Identified source and destination IP addresses and ports

## Wireshark Filters Used
- tcp
- dns
- http
- ip.addr == 10.0.2.15

## Key Observations
- TCP packets showed reliable, connection-oriented communication
- DNS traffic resolved domain names to IP addresses
- HTTP traffic revealed request and response headers
- Normal packet flow was observed with no abnormal behavior

## Skills Demonstrated
- Packet capturing and filtering
- TCP traffic analysis
- DNS query analysis
- HTTP protocol inspection
- Linux networking fundamentals
- Virtual machine lab setup

## Note
- This project focuses on understanding basic network traffic behavior, which is essential for NOC and Network Engineer roles.

## Screenshots
### Interface
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/Interface.png)
Wireshark interface showing the selected active network adapter used for packet capture on the Ubuntu system.

### Live Capture
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/Live%20capture.png)
Live packet capture in progress, displaying real-time network traffic generated during browsing and system activity.

### DNS Filter
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/DNS%20query.png)
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/DNS%20response.png)
DNS traffic analysis using display filters to observe domain name resolution requests and responses.

### TCP Stream
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/TCP%20Stream.png)
Follow TCP Stream view illustrating a complete TCP communication flow between client and server.

### HTTP Filter
![img alt](https://github.com/manojk-network/Networking-Projects/blob/3a0df4fe3a9d682675c62b58f2c5a6b69acbc9dc/Wireshark%20packet%20analysis/Screenshots/http%20%26%20https.png)
Highlighting visible plaintext data in HTTP and encrypted payload in HTTPS.

## Video Demo
https://youtu.be/BZFgJc8bkOQ

## Conclusion
This project provided hands-on experience in capturing and analyzing real network traffic using Wireshark

