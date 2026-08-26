# Multi-Vendor Network Infrastructure

## 📌 Project Overview
This repository contains the configuration files, device deployments, and network traffic captures for a multi-vendor enterprise network infrastructure project. Designed as part of the CNIT 345 coursework at Purdue University, this lab demonstrates the implementation of advanced IPv6 routing, IPv4 routing, switching, and management protocols across Cisco and HP enterprise hardware.

The architecture features a robust hierarchical design utilizing OSPFv3, RIP, IGRP and EIGRP for IPv6 and IPv4, alongside extensive VLAN segmentation and SNMPv2c management

## 🏗️ Network Topology & Architecture
The network relies on both a IPv6 space (`FD00:C345:13::/48`) and an IPv4 space (`44.36.13.0/24`) divided across multiple routing domains and VLANs [cite: 1].

### Routing Domains
*   **OSPFv3 (Area 0, 13, 113, 213):** Core routing protocol linking the ISR routers (ISRA, ISRB, ISRC) and Catalyst switches [cite: 1].
*   **EIGRP for IPv6 (AS 113):** Utilized for specific transit links and distribution layer routing on `cisco3750b` and `ISRB` [cite: 1].
*   **Route Redistribution:** Mutual redistribution between OSPF 1 and EIGRP 113 is configured on the ASBR (`ISRB`) to ensure full end-to-end reachability [cite: 1].

### VLAN Segmentation
The Layer 2/Layer 3 switching environment is segmented to isolate traffic and broadcast domains [cite: 1]:
*   **VLAN 1:** Native Management VLAN
*   **VLAN 131, 132, 133:** Access VLANs configured on the Cisco 2911 router environment [cite: 1].
*   **VLAN 1301, 1302, 1303:** Primary user/access VLANs spanning the Cisco 3750-X and HP 2920/48G switches [cite: 1]. 

## 🛠️ Hardware & Device Inventory
This repository contains the running-configurations for the following physical devices [cite: 1]:

**Routers:**
*   `ISRA` (Cisco ISR 4331) - Area 0 Boundary [cite: 1]
*   `ISRB` (Cisco ISR 4331) - Area 113 ASBR [cite: 1]
*   `ISRC` (Cisco ISR) [cite: 1]
*   `Cisco2911` (Cisco 2911) [cite: 1]

**Switches:**
*   `Cisco-3750A` (Cisco Catalyst 3750X-48P) [cite: 1]
*   `cisco3750b` (Cisco Catalyst 3750X-48P) [cite: 1]
*   `3750C` (Cisco Catalyst 3750X-48P) [cite: 1]
*   `HP-2920-24G` (HP ProCurve/Aruba 24-port Gigabit) [cite: 1]
*   `HP48` (HP 48-port Gigabit) [cite: 1]

## 📦 Repository Contents
*   `/Config/`: Contains raw text backups of the `show running-config` output for all Cisco routers/switches and HP switch configurations [cite: 1].
*   `345lab1networkPacketCapture.pcapng`: A Wireshark packet capture detailing the network traffic, DHCPv6 relay exchanges, and OSPF/EIGRP hello packets across the wire. Captured via Dumpcap 4.6.0 on Windows 11 [cite: 1].

## ⚙️ Core Configurations & Features
*   **IPv6 DHCP Relay:** Implemented across distribution switches to forward requests to the centralized DHCPv6 server (`FD00:C345:13::2`) [cite: 1].
*   **SNMPv2c Management:** Extensive SNMP trap generation is enabled for environmental monitoring, link states, OSPF/EIGRP state changes, and hardware tracking, reporting to the management server (`44.36.13.11`) [cite: 1].
*   **Time Synchronization:** NTP is configured pointing to local stratum servers (`tick.cit.lcl` and `tock.cit.lcl`) [cite: 1].
*   **Rapid PVST+:** Spanning tree is optimized for the Cisco Catalyst environment, with HP switches configured with edge ports for rapid deployment [cite: 1].

---

## 🚀 Recommended Additions for Repository Readers
*If you are cloning this repository for review or deployment, please note the following:*

1.  **Network Diagram (Missing):** Add a visual topology (Visio or Draw.io) to the repository root. Mapping the physical interfaces (e.g., GigabitEthernet0/0/1 to trunk ports) will greatly improve the readability of these configurations.
2.  **IP Addressing Table:** A documented spreadsheet mapping the `FD00:C345` IPv6 subnets to their respective VLANs and loopback interfaces.
3.  **Secrets & Keys:** Note that Type 5 and Type 9 passwords are included in the configurations. These should be sanitized or stripped out if repurposed for a production environment. 
4.  **PCAP Analysis:** Providing a brief markdown summary with Wireshark screenshots of the `.pcapng` file would highlight the specific protocol behaviors (like EIGRP Update packets or OSPF LSAs) captured during the lab.

---
*Authored by Lindsay Keough for CNIT 345 - Group 13.*
README.md
Displaying README.md.
