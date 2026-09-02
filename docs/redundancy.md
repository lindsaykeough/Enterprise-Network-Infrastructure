# First-hop redundancy

HSRP and GLBP were implemented during the project to provide resilient virtual default gateways.

HSRP validation:

```text
show standby brief
```

GLBP validation:

```text
show glbp brief
```

Failover testing should confirm virtual-gateway reachability before and after disabling the preferred router or path, then verify recovery/preemption behavior after restoration.
