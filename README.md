# Cybersecurity Week 1 - NAT Network & Wireshark Labs
By Sumboty | Networkwalks Academy

## Overview
This repo contains Week 1 labs: VirtualBox NAT Network configuration and Wireshark packet analysis including SOC investigation.

## Lab 01 - NAT Network 10.0.0.0/24
- **Topology:** Kali 10.0.0.2/24, Windows Host 10.0.0.10, Android 10.0.0.9, Gateway 10.0.0.1
- **Challenges Fixed:**
    - Kali stuck on 10.0.0.4 - Error "IP configuration could not be reserved"
    - Android black screen when minimized
- **Solutions:**
    - Clean Kali install, set NatNetwork 10.0.0.0/24, static IP 10.0.0.2/24 gw 10.0.0.1 dns 8.8.8.8
    - Android: Video Memory 128MB, Graphics Controller VMSVGA, 3D Acceleration OFF, RAM 2048MB
- **Verification:** Bidirectional pings 10.0.0.2 <-> 10.0.0.10 <-> 10.0.0.9 = 0% loss, Internet 8.8.8.8 reachable.

## Lab 02 - Wireshark Live Capture
- Website: networkwalks.com
- Website IP: 192.232.216.135
- Filter: dns.qry.name == "networkwalks.com"
- Findings: SNI=networkwalks.com, Port 443, TLSv1.3

## Lab 03 - Wireshark PCAP Analysis
- File: Wireshark_Lab2_Microsoft_DNS_v2.pcap
- Laptop: 192.168.0.105, DNS: 8.8.8.8
- Microsoft IPs: 20.70.246.20, 20.76.201.171, 20.112.250.133, 20.231.239.246, 20.236.44.162
- Port 443, TLSv1.3

## Lab 04 - SOC Lab: Identify Attacker IP (Extra Project)
- **Platform:** https://networkwalks.com/wireshark-lab3/
- Total Packets: 309
- SYN Packets: 73 (filter tcp.flags.syn == 1)
- **Attacker:** 192.168.10.66
- **Target:** 192.168.10.20 (Web Server)
- Source Port: 52311
- Ports Probed: 40, Open: 22,80,443, Closed: 37 (RST,ACK reply)
- Attack Type: Port Scan

## Screenshots
All screenshots in respective folders.

## Tools
VirtualBox, Kali Linux, Wireshark, NAT Network
