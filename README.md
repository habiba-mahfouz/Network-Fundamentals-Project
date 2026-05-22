## Project Overview

This project simulates a real-world enterprise network for a company with one **main headquarters (HQ)** and **two branches**, all implemented using Cisco Packet Tracer.

---
## Network Topology
<img width="1886" height="625" alt="Network" src="https://github.com/user-attachments/assets/8728f2ae-ecf8-4cca-b63c-35472cfa4064" />

## Network Architecture

### Inter-Site Communication (WAN)
The three routers communicate with each other using **Static Routing** over two WAN links:
- HQ ↔ Branch-1: `200.0.1.0/30`
- HQ ↔ Branch-2: `200.0.2.0/30`

### Intra-Site Communication (LAN)
Inside each router, the internal subnets communicate using **Dynamic Routing (RIP v2)**.

---

## HQ — Main Headquarters
The HQ hosts the company's main server and two internal departments:

- **Server** → configured with **Static NAT** for secure, fixed public access
- **IT Department & HR Department** → configured with **Dynamic NAT (PAT with overload)** for shared internet access
- **Private Network:** `172.16.0.0/26` — Subnetting by Host
- **Public Network:** `200.0.0.0/24`

## Branch-1 & Branch-2
Both branches follow the same design:
- Two internal departments, each on a separate subnet
- Dynamic Routing (RIP v2) between internal subnets
- Static Route to HQ as the default gateway

## Topics Covered
- IP Classes (A, B, C)
- Subnetting by Network & by Host
- Switching (Layer 2)
- Static Routing
- Dynamic Routing (RIP v2)
- Static NAT
- Dynamic NAT (PAT with overload)

## Network Design
| Location | Class | Network | Subnetting Type |
|---|---|---|---|
| HQ | Class B | 172.16.0.0/26 | By Host |
| Branch-1 | Class C | 192.168.1.0/27 | By Network |
| Branch-2 | Class A | 10.0.0.0/28 | By Host |
| WAN Links | Class C | 200.0.x.0/30 | By Network |

## Files
- `Final.pkt` — Cisco Packet Tracer file
- `Network_Subnetting_Documentation.docx` — IP & Subnetting details
- `Routing_NAT.pdf` — Routing & NAT verification
- `Show.pdf` — Show commands output

## Tools Used
- Cisco Packet Tracer 8.x
