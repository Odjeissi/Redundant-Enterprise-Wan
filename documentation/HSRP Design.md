# HSRP Design

HSRP is implemented at the Distribution layer to provide gateway redundancy for user VLANs.

---

## VLAN 10

- Virtual IP: 192.168.1.254
- DSW1 configured as Active
- DSW2 configured as Standby

## VLAN 20

- Virtual IP: 192.168.2.254
- DSW2 configured as Active
- DSW1 configured as Standby

---

## Design Decision

Active roles are split between switches to balance traffic load.

Preemption is enabled to ensure the preferred switch regains Active status after recovery.

---

## Validation Commands

- show standby brief

![HSRP](/screenshots/HSRP.png)

Failover Test:

- Shut down Active SVI
- Confirm Standby becomes Active
- Verify users maintain connectivity
