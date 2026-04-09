# Scanning-Local-Network-for-Open-Ports

Local Network Reconnaissance & Port Analysis
(Cybersecurity Internship - Task 1)
Project Overview
This project focuses on the fundamental phase of the cyber attack lifecycle: Reconnaissance. The goal was to perform a controlled scan of a local area network (LAN) to identify active hosts, discover open ports, and analyze the security posture of connected devices using industry-standard tools like Nmap and Wireshark.

Objective
Identify active IP addresses within the 192.168.1.0/24 range.

Conduct a TCP SYN (Stealth) Scan to map open ports.

Analyze the difference between TCP and UDP scanning methodologies.

Understand the security implications of exposed services (HTTP, SSH, RDP, etc.).

Tools Used
Nmap: For network discovery and security auditing.

Wireshark: For packet-level analysis of the TCP three-way handshake.

Linux/Command Line: For executing network commands and managing output files.

Technical Implementation
1. Network Discovery
Identified the local IP range and gateway using ipconfig / ip addr.

2. Stealth Scanning
Executed a TCP SYN scan to identify open ports without establishing a full connection, minimizing the footprint on target logs.

Bash
# Command used for stealth scanning the local subnet
sudo nmap -sS 192.168.1.0/24 -oN scan_results.txt
3. Packet Analysis
Captured traffic in Wireshark during the scan to observe the SYN -> SYN/ACK -> RST sequence, confirming the "half-open" nature of the scan.

Key Findings & Outcomes
Active Hosts: [Insert number of devices found, e.g., 5 devices].

Critical Ports Found: * Port 80/443: Web management interfaces for networking gear.

Port 22: SSH service detected on a Linux workstation.

Risk Assessment: Identified [mention a risk, e.g., an unencrypted Telnet port or an open RDP port] which could be leveraged for unauthorized access.

Final Outcome
The successful completion of this task resulted in a Network Security Baseline. This document serves as a reference for "normal" network state, allowing for the detection of "shadow IT" or unauthorized services added to the network in the future.
