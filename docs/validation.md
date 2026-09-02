# Validation checklist

1. **Interfaces:** expected links are up/up and use the correct address/mask.
2. **Layer 2:** VLAN membership and trunks match the design.
3. **Routing:** OSPF/EIGRP adjacencies are established and expected routes are installed.
4. **Redistribution:** prefixes cross routing-domain boundaries as intended.
5. **Redundancy:** HSRP/GLBP virtual gateways are reachable and fail over correctly.
6. **Services:** DHCP, DNS, NTP, SSH, and TFTP are reachable from intended networks.
7. **End to end:** test client-to-gateway, inter-VLAN, inter-domain, and WAN paths.
