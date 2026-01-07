# Nmap Aggressive Scan – Networking Project

## Project Overview
This project demonstrates the use of Nmap Aggressive Scan (-A) to identify open ports, running services, service versions, OS details, default Nmap scripts, and traceroute information.

## Tool Used
- Nmap
- Ubuntu Linux

## Command Used
nmap -A scanme.nmap.org

## What This Scan Shows

| Port | Service | Status | Version         |
| ---- | ------- | ------ | --------------- |
| 22   | SSH     | Open   | OpenSSH 6.6.1p1 |
| 80   | HTTP    | Open   | Apache 2.4.7    |

- Open ports and services
- Service versions (SSH, HTTP, etc.)
- OS detection
- Default Nmap script outputs
- Network behavior overview

## Common Nmap Commands Used

- `nmap <target>`  
  Basic scan to identify live hosts and open ports.

- `nmap -sS <target>`  
  TCP SYN scan used for fast and stealthy port scanning.

- `nmap -sV <target>`  
  Detects service versions running on open ports.

- `nmap -A <target>`  
  Aggressive scan enabling OS detection, version detection, and default scripts.

- `nmap -p 1-1000 <target>`  
  Scans specific port ranges instead of all ports.

- `nmap --script default <target>`  
  Runs default NSE scripts for additional service information.


## Why This Matters
For NOC and Security engineers, aggressive scanning helps quickly identify exposed services, verify system configurations, and detect potential security risks in live networks.

## Screenshots
### Default Nmap script Output
![image alt](https://github.com/manojk-network/Networking-projects/blob/30e89ece48e72228f85c0bc730c6e139c80e5391/Nmap/Screenshots/Default%20Nmap%20scripts%20output.png)
- This screenshot shows OS detection (Linux) and default Nmap script outputs, giving insight into the target system behavior.

### OS $ Service info
![image alt](https://github.com/manojk-network/Networking-projects/blob/9ecabd4e470472616ca878b42026e780d2921e12/Nmap/Screenshots/OS%20%26%20service%20info.png)
- This output highlights service versions such as OpenSSH and Apache HTTPD, useful for vulnerability assessment.

### Open ports & services
![image alt](https://github.com/manojk-network/Networking-projects/blob/b52dc1c460f8050c8025721a4fc0b8dbbe580b44/Nmap/Screenshots/Open%20ports%20%26%20services.png)
- This screenshot shows open TCP ports (22, 80) discovered using Nmap aggressive scan, indicating active SSH and HTTP services.
  
## Video Explanation
A 4-minute video explaining the scan and output is available here:
https://youtu.be/HFMdf0Cyu4s


