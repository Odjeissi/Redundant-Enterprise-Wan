# NAT & ACL Design

## NAT (PAT Overload)

Configured on the Edge router.

Inside Interface:

- Connected to Core (10.10.3.0/30)

Outside Interface:

- Connected to ISP (203.0.113.0/30)

Inside networks translated:

- 192.168.1.0/24
- 192.168.2.0/24

PAT allows multiple internal hosts to share a single public IP.

![NAT](/screenshots/NAT.png)

---

## Outbound ACL Policy

Applied inbound on the Edge router’s inside interface.

Allowed Services:

- HTTP (80)
- HTTPS (443)
- DNS (UDP/TCP 53)
- Email services (SMTP, POP3)
- FTP

Denied:

- Telnet (TCP 23)

![ACL](/screenshots/ACL.png)

Purpose:

- Restrict insecure protocols
- Allow standard business internet services
