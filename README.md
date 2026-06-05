<div align="center">

<svg width="100%" viewBox="0 0 860 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%"   stop-color="#071a0e"/>
      <stop offset="40%"  stop-color="#0d3b1e"/>
      <stop offset="100%" stop-color="#1b5e20"/>
    </linearGradient>
    <pattern id="stripes" width="24" height="24" patternUnits="userSpaceOnUse" patternTransform="rotate(-45)">
      <rect width="24" height="24" fill="none"/>
      <rect width="12" height="24" fill="rgba(255,255,255,0.025)"/>
    </pattern>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Base gradient -->
  <rect width="860" height="200" rx="10" fill="url(#bg)"/>
  <!-- Stripe overlay -->
  <rect width="860" height="200" rx="10" fill="url(#stripes)"/>
  <!-- Radial glows -->
  <ellipse cx="180" cy="100" rx="200" ry="100" fill="rgba(46,125,50,0.18)"/>
  <ellipse cx="700" cy="100" rx="180" ry="90"  fill="rgba(27,94,32,0.22)"/>
  <!-- Network node decorations -->
  <g opacity="0.35" stroke="#4caf50" stroke-width="1" fill="none">
    <circle cx="60"  cy="40"  r="6"/>
    <circle cx="120" cy="70"  r="5"/>
    <circle cx="60"  cy="40"  r="6"/>
    <line x1="60" y1="40" x2="120" y2="70"/>
    <circle cx="800" cy="160" r="6"/>
    <circle cx="760" cy="130" r="5"/>
    <line x1="800" y1="160" x2="760" y2="130"/>
    <circle cx="820" cy="50"  r="4"/>
    <circle cx="760" cy="130" r="5"/>
    <line x1="820" y1="50" x2="760" y2="130"/>
  </g>
  <!-- Horizontal accent line -->
  <line x1="200" y1="140" x2="660" y2="140" stroke="rgba(76,175,80,0.3)" stroke-width="1"/>
  <!-- Main title -->
  <text x="430" y="88" text-anchor="middle" font-family="Segoe UI, Arial, sans-serif"
        font-size="30" font-weight="700" fill="#ffffff" filter="url(#glow)"
        letter-spacing="-0.5">Multi-Site Cisco Network Design</text>
  <!-- Subtitle -->
  <text x="430" y="118" text-anchor="middle" font-family="Segoe UI, Arial, sans-serif"
        font-size="14" fill="rgba(255,255,255,0.72)" letter-spacing="0.5">
    Subnetting · OSPF Routing · VLANs · DHCP · Port Security · Wireless
  </text>
  <!-- Tags -->
  <g font-family="Courier New, monospace" font-size="11" fill="rgba(76,175,80,0.9)">
    <rect x="193" y="149" width="80" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="233" y="162" text-anchor="middle">Cisco PT</text>
    <rect x="283" y="149" width="60" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="313" y="162" text-anchor="middle">TCP/IP</text>
    <rect x="353" y="149" width="50" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="378" y="162" text-anchor="middle">OSPF</text>
    <rect x="413" y="149" width="50" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="438" y="162" text-anchor="middle">VLANs</text>
    <rect x="473" y="149" width="82" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="514" y="162" text-anchor="middle">Port Security</text>
    <rect x="565" y="149" width="82" height="18" rx="4" fill="rgba(76,175,80,0.12)" stroke="rgba(76,175,80,0.35)" stroke-width="1"/>
    <text x="606" y="162" text-anchor="middle">Wireless LAN</text>
  </g>
  <!-- Bottom wave -->
  <path d="M0 185 Q215 175 430 185 Q645 195 860 185 L860 200 L0 200 Z" fill="rgba(0,0,0,0.25)"/>
</svg>

<br/>

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco_Packet_Tracer-Lab_File_Included-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white)](./Mubarak_Capstone_Project_Topology.pkt)
[![Network](https://img.shields.io/badge/Assigned_Network-10.1.1.0%2F24-2e7d32?style=for-the-badge&logo=cisco&logoColor=white)](#)
[![Sites](https://img.shields.io/badge/Topology-3_Sites_%7C_9_Subnets-1b5e20?style=for-the-badge)](#)
[![Routing](https://img.shields.io/badge/Routing_Protocol-OSPFv2-4caf50?style=for-the-badge)](#)

</div>

---

<div align="center">

## 📌 Project Overview

</div>

This capstone project demonstrates the **end-to-end design and configuration of a 3-site enterprise network** using Cisco Packet Tracer. Starting from a blank canvas, I planned the full IP addressing scheme, subnetting strategy, routing architecture, DHCP design, VLAN segmentation, and security — then implemented and verified every component through CLI configuration and live connectivity testing.

**Assigned Network Block:** `10.1.1.0/24`

---

<div align="center">

## 🗺️ Network Topology

</div>

The network spans three geographically separate sites connected via WAN links, each with distinct roles and requirements:

```
                    ┌─────────────────────────────────┐
                    │         SITE A  (HQ)            │
                    │  SiteA_Router  10.1.1.97        │
                    │  SiteA_Switch1 10.1.1.98        │
                    │  SiteA_Switch2 10.1.1.99        │
                    │  VLAN 10  │  VLAN 20  │  Wired  │
                    └──────────────┬──────────────────┘
                     WAN /30       │       10.1.1.248–251
          ┌──────────────────────────────────────────────┐
          │              SITE B  (Data Centre)           │
          │   SiteB_Router  10.1.1.113                   │
          │   SiteB_Switch  10.1.1.114                   │
          │   DNS Server    10.1.1.115  ← central DHCP   │
          └──────────────┬───────────────────────────────┘
                WAN /30  │       10.1.1.252–255
          ┌──────────────────────────────────────────────┐
          │              SITE C  (Branch Office)         │
          │   SiteC_Router  10.1.1.1                     │
          │   SiteC_Switch  10.1.1.2                     │
          │   Wireless AP   10.1.1.3 / 10.1.1.65         │
          │   Wired PCs + Laptops (wireless DHCP)        │
          └──────────────────────────────────────────────┘
```

---

<div align="center">

## 📐 Subnet Design

</div>

<div align="center">

**Assigned Block: `10.1.1.0/24`** — Variable-length subnetting (VLSM) applied to minimize address waste

</div>

| Subnet Name | Hosts Needed | Block Size | CIDR | Network Address | Broadcast | Subnet Mask |
|---|:---:|:---:|:---:|---|---|---|
| **Site C — Wired** | 32 | 64 | `/26` | `10.1.1.0` | `10.1.1.63` | `255.255.255.192` |
| **Site C — Wireless** | 18 | 32 | `/27` | `10.1.1.64` | `10.1.1.95` | `255.255.255.224` |
| **Site A — Wired** | 12 | 16 | `/28` | `10.1.1.96` | `10.1.1.111` | `255.255.255.240` |
| **Site B — Wired** | 10 | 16 | `/28` | `10.1.1.112` | `10.1.1.127` | `255.255.255.240` |
| **Site A — VLAN 10** | 4 | 8 | `/29` | `10.1.1.128` | `10.1.1.135` | `255.255.255.248` |
| **Site A — VLAN 20** | 4 | 8 | `/29` | `10.1.1.136` | `10.1.1.143` | `255.255.255.248` |
| **WAN: Site A → Site B** | 2 | 4 | `/30` | `10.1.1.248` | `10.1.1.251` | `255.255.255.252` |
| **WAN: Site B → Site C** | 2 | 4 | `/30` | `10.1.1.252` | `10.1.1.255` | `255.255.255.252` |

> **Subnetting approach:** Largest subnets allocated first (Site C Wired /26) down to smallest (WAN /30 links) to avoid address overlap and ensure efficient use of the /24 block.

---

<div align="center">

## 🖥️ Device IP Assignments

</div>

### Site A — HQ

| Device | Interface | Assignment | IP Address |
|---|---|---|---|
| SiteA_Router | `gi0/0` | Static | `10.1.1.97` |
| SiteA_Router | `gi0/1` (WAN→B) | Static | `10.1.1.249/30` |
| SiteA_Switch1 | `vlan 1` | Static | `10.1.1.98` |
| SiteA_Switch2 | `vlan 1` | Static | `10.1.1.99` |
| PCs (wired) | `fa0/1` | DHCP | `10.1.1.100–110` |
| VLAN 10 PC1 | `Sw1 fa0/10` | Static | `10.1.1.130/29` |
| VLAN 10 PC2 | `Sw2 fa0/10` | Static | `10.1.1.131/29` |
| VLAN 20 PC1 | `Sw1 fa0/20` | Static | `10.1.1.138/29` |
| VLAN 20 PC2 | `Sw2 fa0/20` | Static | `10.1.1.139/29` |

### Site B — Data Centre

| Device | Interface | Assignment | IP Address |
|---|---|---|---|
| SiteB_Router | `gi0/1/0` | Static | `10.1.1.113` |
| SiteB_Router | `gi0/0` (WAN→A) | Static | `10.1.1.250/30` |
| SiteB_Router | `gi0/2` (WAN→C) | Static | `10.1.1.253/30` |
| SiteB_Switch | `vlan 1` | Static | `10.1.1.114` |
| DNS Server | `fa0/2` | Static | `10.1.1.115` |
| PCs | `fa0/1` | DHCP | `10.1.1.116–126` |

### Site C — Branch Office

| Device | Interface | Assignment | IP Address |
|---|---|---|---|
| SiteC_Router | `gi0/1` | Static | `10.1.1.1` |
| SiteC_Router | `gi0/0` (WAN→B) | Static | `10.1.1.254/30` |
| SiteC_Switch | `vlan 1` | Static | `10.1.1.2` |
| Wireless AP | `fa0/2` | Static | `10.1.1.3` / `10.1.1.65` |
| Wired PCs | `fa0/1` | DHCP | `10.1.1.4–62` |
| Wireless Laptops | wireless | DHCP | `10.1.1.65–94` |

---

<div align="center">

## 🔀 OSPF Routing Configuration

</div>

OSPFv2 was configured across all three routers to enable **dynamic route advertisement** and inter-site routing without manual static routes. All routers are placed in **Area 0** (backbone).

| Router | Interface | IP Address | Process | Wildcard Mask | Area | IP Helper |
|---|---|---|:---:|---|:---:|---|
| SiteA_Router | `gi0/0` | `10.1.1.97` | 1 | `0.0.0.15` | 0 | `10.1.1.113` |
| SiteA_Router | `gi0/1` | `10.1.1.249` | 1 | `0.0.0.3` | 0 | — |
| SiteB_Router | `gi0/0` | `10.1.1.250` | 2 | `0.0.0.3` | 0 | — |
| SiteB_Router | `gi0/1/0` | `10.1.1.113` | 2 | `0.0.0.15` | 0 | — |
| SiteB_Router | `gi0/2` | `10.1.1.253` | 2 | `0.0.0.3` | 0 | — |
| SiteC_Router | `gi0/0` | `10.1.1.254` | 3 | `0.0.0.3` | 0 | — |
| SiteC_Router | `gi0/1` | `10.1.1.1` | 3 | `0.0.0.63` | 0 | `10.1.1.113` |

> **IP Helper Address (`10.1.1.113`)** configured on Site A and Site C routers to forward DHCP broadcast requests to the centralized DHCP server at Site B.

---

<div align="center">

## ⚙️ DHCP Configuration

</div>

DHCP is centralized on **SiteB_Router**, serving all three sites via IP helper addresses. Excluded addresses ensure static-IP devices are never overwritten.

```
ip dhcp excluded-address 10.1.1.113  10.1.1.115   ← Site B infrastructure
ip dhcp excluded-address 10.1.1.1    10.1.1.3     ← Site C infrastructure
ip dhcp excluded-address 10.1.1.97   10.1.1.100   ← Site A infrastructure

ip dhcp pool SiteA
  network 10.1.1.96  255.255.255.240
  default-router 10.1.1.97
  dns-server 10.1.1.115

ip dhcp pool SiteB
  network 10.1.1.112  255.255.255.240
  default-router 10.1.1.113
  dns-server 10.1.1.115

ip dhcp pool SiteC
  network 10.1.1.0  255.255.255.192
  default-router 10.1.1.1
  dns-server 10.1.1.115
```

---

<div align="center">

## 🌐 DNS Records

</div>

| DNS Name | IP Address |
|---|---|
| `SiteA_Router` | `10.1.1.97` |
| `SiteA_Switch1` | `10.1.1.98` |
| `SiteA_Switch2` | `10.1.1.99` |
| `SiteB_Router` | `10.1.1.113` |
| `SiteB_Switch` | `10.1.1.114` |
| `DNS Server` | `10.1.1.115` |
| `SiteC_Router` | `10.1.1.1` |
| `SiteC_Switch` | `10.1.1.2` |

---

<div align="center">

## 🔒 Security — Port Security & VLANs

</div>

**Port Security** was implemented on Site A switches to restrict unauthorized device access:
- Maximum MAC addresses per port defined and enforced
- Violation modes configured (shutdown / restrict)
- Results verified and documented via `show port-security` output

**VLANs** segment Site A traffic:
- `VLAN 10` — dedicated subnet `10.1.1.128/29` with static PC assignments
- `VLAN 20` — dedicated subnet `10.1.1.136/29` with static PC assignments
- Inter-VLAN routing handled at the router level

---

<div align="center">

## 📡 Wireless LAN

</div>

Site C is configured with a **wireless router** serving laptop clients:
- Wireless interface: `10.1.1.65` (gateway for wireless subnet `10.1.1.64/27`)
- DHCP pool: `10.1.1.65–94`
- Laptops assigned wireless addresses via DHCP
- Web page access verified through the wireless connection

---

<div align="center">

## ✅ Verification Tests Performed

</div>

| Test | Method | Result |
|---|---|---|
| End-to-end connectivity across all sites | `ping` — cross-site | ✅ Successful |
| DHCP address assignment (not on DHCP router) | `ipconfig` on client PC | ✅ Address assigned |
| Routing table completeness | `show ip route` | ✅ All networks visible |
| Port security enforcement | `show port-security` | ✅ Violations handled |
| Wireless connectivity | Laptop association + ping | ✅ Connected |
| Web page access | Browser on wireless laptop | ✅ Page loaded |
| Telnet remote management | CLI session to network device | ✅ Session established |
| Expected failures (blocked routes) | `ping` to blocked segments | ✅ Correctly failed |

---

<div align="center">

## 📂 How to Open the Project

</div>

1. **Download** [Cisco Packet Tracer](https://www.netacad.com) — free with a Cisco NetAcad account
2. **Clone** this repository or download the `.pkt` file
3. **Open** `Mubarak_Capstone_Project_Topology.pkt` in Packet Tracer
4. **Explore** device CLIs — all configurations are live and testable
5. **Run** your own `ping` tests to verify connectivity across sites

---

<div align="center">

## 📸 Screenshots

</div>

| Screenshot | Description |
|---|---|
| `screenshots/subnet-worksheet.png` | Full VLSM subnet planning worksheet |
| `screenshots/topology-green-links.png` | Complete 3-site topology — all links green |
| `screenshots/routing-table.png` | OSPF routing table showing all 8 networks |
| `screenshots/dhcp-config.png` | DHCP pool config with excluded addresses |
| `screenshots/dhcp-assignment.png` | PC receiving DHCP address from remote site |
| `screenshots/ping-results.png` | Successful and expected-failure pings |
| `screenshots/port-security.png` | Port security output and violation results |
| `screenshots/wireless-laptop.png` | Laptop connected to wireless router |
| `screenshots/webpage-access.png` | Web page loaded over the network |
| `screenshots/telnet-session.png` | Telnet remote management session |

---

<div align="center">

## 💡 Key Concepts Demonstrated

</div>

<div align="center">

`VLSM Subnetting` · `OSPF Dynamic Routing` · `Centralized DHCP with IP Helper` · `VLAN Segmentation` · `Inter-VLAN Routing` · `Port Security` · `Wireless LAN Configuration` · `DNS Name Resolution` · `WAN Point-to-Point Links` · `Telnet Remote Management` · `End-to-End Connectivity Verification`

</div>

---

<div align="center">

## 🔗 Connect

**Mubarak Murtadoh** — IT Support Specialist | Lagos, Nigeria

[![Portfolio](https://img.shields.io/badge/Portfolio-mmurtadoh.github.io-4caf50?style=for-the-badge&logo=githubpages&logoColor=white)](https://mmurtadoh.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-mubarak--murtadoh-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mubarak-murtadoh)
[![GitHub](https://img.shields.io/badge/GitHub-mmurtadoh-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mmurtadoh)

<br/>

<svg width="100%" viewBox="0 0 860 80" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="footer-bg" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#071a0e"/>
      <stop offset="50%" stop-color="#1b5e20"/>
      <stop offset="100%" stop-color="#071a0e"/>
    </linearGradient>
    <pattern id="footer-stripes" width="20" height="20" patternUnits="userSpaceOnUse" patternTransform="rotate(-45)">
      <rect width="20" height="20" fill="none"/>
      <rect width="10" height="20" fill="rgba(255,255,255,0.025)"/>
    </pattern>
  </defs>
  <path d="M0 30 Q215 15 430 25 Q645 35 860 20 L860 80 L0 80 Z" fill="url(#footer-bg)"/>
  <path d="M0 30 Q215 15 430 25 Q645 35 860 20 L860 80 L0 80 Z" fill="url(#footer-stripes)"/>
</svg>

</div>
