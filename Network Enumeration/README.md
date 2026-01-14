# Network Enumeration Using Nmap

## Project Summary

This project demonstrates network enumeration using Nmap in an Ubuntu Linux Virtual Machine running on VirtualBox.
Network enumeration is a critical skill for NOC engineers, network administrators, and cybersecurity professionals, as it helps identify active hosts, open ports, running services, and network paths.

## In this lab, I performed:

Discovery of live hosts on the local network.

Port scanning to identify which services are accessible.

Detection of service types and versions.

OS fingerprinting, traceroute analysis, and running default Nmap scripts.

The purpose is to simulate real-world network monitoring and security auditing in a safe lab environment.

## Objectives

Discover all active devices on a LAN.

Identify open ports on hosts to understand available network services.

Detect services running on ports along with version numbers.

Apply OS detection to identify the operating system of hosts.

Perform traceroute analysis to visualize network paths.

Utilize default Nmap scripts for basic vulnerability and service checks.

Gain hands-on experience with Nmap, a fundamental tool in network enumeration.

## Tools Used

Nmap – Network scanning and enumeration tool.

Ubuntu Linux – Virtual environment for safe network testing.

VirtualBox – Virtual machine manager to simulate multiple hosts and networks.

## Commands Used

### ip a – Displays the IP address of the Ubuntu VM, which identifies the local machine on the network.
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2cd5e7db449d5411ac04c38ca5eccb0a40b41107/Network%20Enumeration/Screenshots/ip%20a.png)

### nmap -sn 10.0.2.0/24 – Performs a ping scan to detect all live hosts in the subnet.
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2cd5e7db449d5411ac04c38ca5eccb0a40b41107/Network%20Enumeration/Screenshots/nmap%20-sn%2010.0.2.15.png)

### nmap 10.0.2.15 – Basic port scan on a single host to see which ports are open or closed.


### nmap -sV 10.0.2.15 – Detects services running on the open ports and identifies their versions.
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2cd5e7db449d5411ac04c38ca5eccb0a40b41107/Network%20Enumeration/Screenshots/Nmap%20-sV%20%2010.0.2.15.png)

### sudo nmap -A 10.0.2.15 – Aggressive scan combining:
![img alt](https://github.com/manojk-network/Networking-Projects/blob/2cd5e7db449d5411ac04c38ca5eccb0a40b41107/Network%20Enumeration/Screenshots/sudo%20nmap%20-A%2010.0.2.15.png)

## Key Learnings

Learned to enumerate hosts on a network using Nmap.

Understood port scanning basics and identifying open services.

Practiced OS detection and analyzing network paths via traceroute.

Applied default Nmap scripts for quick service and vulnerability checks.

Gained experience in using Linux commands and executing network tools in a VM safely.

## Conclusion

Network enumeration is a core skill for monitoring and securing networks.
This project helped me:

Understand the structure of local networks and connected devices.

Identify live hosts, open ports, and service versions, which is crucial for troubleshooting and security audits.

Gain confidence using Nmap as a professional tool for network analysis.

Prepare for NOC engineer tasks and future cloud/network security projects.

