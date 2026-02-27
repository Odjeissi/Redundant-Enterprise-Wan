# OSPF Design

OSPF Area 0 is used across the Distribution, Core, and Edge layers.

---

## Design Approach

- Single Area (Area 0) to simplify lab topology
- Loopback interfaces used for stable router IDs
- OSPF enabled only on necessary interfaces
- Default route injected from Edge router

---

## Route Propagation

- VLAN networks are advertised from Distribution switches
- Core router redistributes transit links
- Edge router advertises default route (0.0.0.0/0)

---

## Validation Commands

- show ip ospf neighbor

![OSPF](/screenshots/neighbor.png)

- show ip route

![OSPF](/screenshots/route.png)

- show ip protocols

![OSPF](/screenshots/protocol.png)

Expected Result:

- Full adjacency between all Layer 3 devices
- Internal VLAN routes visible across topology
- Default route learned via OSPF
