# Layer 2 design

VLANs separated endpoint networks and trunks transported multiple VLANs between switches and routed devices.

Representative Cisco pattern:

```text
vlan 1301
 name USERS_A
vlan 1302
 name USERS_B

interface GigabitEthernet1/0/1
 switchport trunk encapsulation dot1q
 switchport mode trunk
 switchport trunk allowed vlan 1301,1302,1303

interface GigabitEthernet1/0/10
 switchport mode access
 switchport access vlan 1301
 spanning-tree portfast
```

Validation focused on VLAN membership, trunk allowed lists, spanning-tree state, and routed gateway reachability.
