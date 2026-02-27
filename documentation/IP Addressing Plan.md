# IP Addressing Plan

## VLAN Networks

| VLAN | Purpose | Subnet         | Default Gateway (HSRP VIP) |
| ---- | ------- | -------------- | -------------------------- |
| 10   | Users   | 192.168.1.0/24 | 192.168.1.254              |
| 20   | Users   | 192.168.2.0/24 | 192.168.2.254              |

---

## Distribution Switch IPs

| Device | VLAN    | IP Address    |
| ------ | ------- | ------------- |
| DSW1   | VLAN 10 | 192.168.1.253 |
| DSW2   | VLAN 10 | 192.168.1.252 |
| DSW1   | VLAN 20 | 192.168.2.253 |
| DSW2   | VLAN 20 | 192.168.2.252 |

---

## Routed Transit Links (/30)

| Link        | Subnet         |
| ----------- | -------------- |
| DSW1 ↔ Core | 10.10.1.0/30   |
| DSW2 ↔ Core | 10.10.2.0/30   |
| Core ↔ Edge | 10.10.3.0/30   |
| Edge ↔ ISP  | 203.0.113.0/30 |

---

## NAT Configuration

Inside Networks:

- 192.168.1.0/24
- 192.168.2.0/24

Translated using PAT on Edge ISP-facing interface.
