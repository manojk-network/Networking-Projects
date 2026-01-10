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




## Video 

## Conclusion

This project provided hands-on experience in capturing and analyzing real network traffic using Wireshark

