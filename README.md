# Enterprise Network Architecture & Migration

### Project Overview
This repository contains the architecture, configuration, and documentation for a highly available, multi-vendor enterprise network. The project demonstrates end-to-end network engineering, specifically focusing on the deployment and management of a dual-stack (IPv4 and IPv6) environment. It highlights the transition from and integration of legacy IPv4 setups with modern IPv6 architectures, alongside enterprise-grade monitoring and redundancy protocols.

### Core Technologies
*   **Routing Protocols:** OSPFv2 (IPv4), OSPFv3 (IPv6), EIGRP, Mutual Route Redistribution, Route Summarization
*   **Layer 2/3 Switching:** VLAN & SVI (Switched Virtual Interface) Provisioning
*   **High Availability:** GLBP (Gateway Load Balancing Protocol)
*   **Infrastructure & Services:** DHCP/DHCPv6, SNMP, NTP, Syslog
*   **Network Management:** LibreNMS
*   **Vendor Platforms:** Cisco Systems (ISRs, 3750X series), HP (48G switches), Juniper Networks 

### Technical Achievements
*   **Dual-Stack Infrastructure:** Engineered a seamless transit core that successfully routed both IPv4 and IPv6 traffic concurrently, ensuring legacy IPv4 system compatibility while establishing a scalable IPv6 footprint.
*   **Multi-Vendor Integration:** Integrated Cisco and Juniper hardware, utilizing multi-area OSPFv2/OSPFv3 and EIGRP to establish scalable, loop-free routing domains. 
*   **Advanced Route Redistribution:** Successfully configured mutual redistribution between OSPF and EIGRP domains across the dual-stack topology, ensuring full cross-network reachability and optimized routing paths.
*   **Layer 3 Redundancy:** Deployed GLBP to provide both active gateway redundancy and dynamic load balancing, ensuring continuous network uptime for end-users during hardware failure simulations.
*   **Infrastructure Visibility:** Provisioned LibreNMS alongside SNMP, NTP, and Syslog services to establish comprehensive monitoring, logging, and time-synchronization across all network nodes.
*   **Technical Documentation:** Authored detailed deployment configurations, dual-stack topology diagrams, and formal recommendations to facilitate clear communication and future network scaling.

### Troubleshooting & Problem Solving
*   **DHCP & IP Allocation:** Diagnosed and resolved both IPv4 and IPv6 address assignment failures by tracing packet flows. Corrected neighbor discovery, VLAN/SVI assignments, and relay agent misconfigurations to successfully restore automated client provisioning.
*   **Firewall Policy Alignment:** Audited and restructured firewall access control lists (ACLs) that were inadvertently dropping multi-area OSPF routing multicast traffic. Reconfigured security policies to permit dynamic routing updates while maintaining a strict, deny-by-default boundary security posture.
*   **OSPF Route Summarization:** Identified routing table bloat and optimized network performance by implementing manual route summarization at the network boundaries for both OSPFv2 and OSPFv3. This significantly reduced processor overhead and memory utilization on the core transit routers.

### Value Proposition
> **Business Impact:** 
> This project demonstrates the ability to independently design, deploy, and troubleshoot complex, real-world network infrastructure. By successfully managing a dual-stack environment, prioritizing load balancing (GLBP), and proactively monitoring assets (LibreNMS), this architecture aligns with industry best practices for maintaining high-availability, fault-tolerant enterprise networks during major technology migrations.
