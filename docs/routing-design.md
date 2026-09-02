# Routing design

## OSPF / OSPFv3

OSPF was used across the routed core and expanded into multiple areas. IPv6 routing also used OSPFv3.

Useful validation commands:

```text
show ip ospf neighbor
show ip route ospf
show ip ospf interface brief
show ipv6 ospf neighbor
show ipv6 route ospf
```

## EIGRP

Separate EIGRP routing domains were used in portions of the topology.

```text
show ip eigrp neighbors
show ip eigrp topology
show ip route eigrp
```

## Redistribution

OSPF/EIGRP redistribution provided reachability between routing domains. Troubleshooting followed this order: validate each protocol independently, verify the redistribution router has both route sets, check redistributed prefixes/metrics, then test forwarding end to end.
