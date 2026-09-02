# Troubleshooting approach

The most effective workflow was to isolate the first failing layer rather than changing multiple devices at once.

- Verify physical/interface state and addressing first.
- Validate VLAN membership and trunks before routing.
- Confirm each routing protocol works independently before debugging redistribution.
- Check the local routing table before testing remote forwarding.
- Validate HSRP/GLBP group IDs, virtual IPs, priorities, and preemption.
- Test one hop at a time with ping/traceroute and route lookups.
- Re-check DHCP relay, DNS, and management-service reachability after topology changes.
