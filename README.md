# cybersecurity-net-practical
# Multi-Zone DMZ Implementation Using Cisco Packet Tracer

## Overview
This practical demonstrates the design and implementation of a secure multi-zone network architecture using Cisco Packet Tracer. The network was divided into three zones:

- WAN (Public Network)
- DMZ (Web Server Zone)
- LAN (Internal Network)

Access Control Lists (ACLs) were configured on the router to enforce security policies and control communication between the different zones.

---

## Objectives
- Design a secure network using WAN, DMZ, and LAN zones
- Configure router interfaces and IP addressing
- Implement ACLs for traffic filtering
- Allow controlled communication between zones
- Prevent unauthorized access to internal resources

---

## Network Structure

| Zone | Network Address | Purpose |
|------|----------------|---------|
| WAN | 192.168.1.0/24 | External/Public Network |
| DMZ | 172.16.1.0/24 | Web Server Zone |
| LAN | 10.0.1.0/24 | Internal Database Network |

---

## Security Policies
The following rules were implemented:

- Allow HTTP/HTTPS traffic from WAN to DMZ
- Allow database communication from DMZ to LAN
- Block direct WAN access to LAN
- Restrict unnecessary DMZ outbound traffic

---

## Tools Used
- Cisco Packet Tracer
- Cisco Router
- Access Control Lists (ACLs)

---

## Router Configuration Example

```bash
access-list 100 permit tcp 192.168.1.0 0.0.0.255 172.16.1.10 eq 80
access-list 100 permit tcp 192.168.1.0 0.0.0.255 172.16.1.10 eq 443
access-list 100 permit tcp 172.16.1.10 0.0.0.0 10.0.1.10 eq 1433
access-list 100 deny ip 192.168.1.0 0.0.0.255 10.0.1.0 0.0.0.255
access-list 100 permit ip any any
