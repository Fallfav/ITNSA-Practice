# 🔧 Cisco Practice

Documentation and hands-on practice for Cisco networking configurations using **Cisco Packet Tracer** — covering essential topics for ITNSA competition.

---

## 📋 Topics Covered

| Topic | Status |
|---|:---:|
| Static Routing | ✅ |
| OSPF | ✅ |
| EIGRP | ✅ |
| VLAN | ✅ |
| Trunking | ✅ |
| STP (Spanning Tree Protocol) | ✅ |
| ACL (Access Control List) | ✅ |
| NAT (Network Address Translation) | ✅ |

---

## 🗺️ Routing

### Static Routing
Manually defining routes between networks.

**Key Concepts:**
- Default route (`ip route 0.0.0.0 0.0.0.0`)
- Next-hop vs exit interface
- Floating static route (backup route)

### OSPF (Open Shortest Path First)
Link-state routing protocol using Dijkstra's algorithm.

**Key Concepts:**
- OSPF single area (Area 0)
- OSPF multi-area
- Router ID, DR/BDR election
- `network` command & wildcard mask
- Passive interface

### EIGRP (Enhanced Interior Gateway Routing Protocol)
Cisco's advanced distance-vector routing protocol.

**Key Concepts:**
- EIGRP autonomous system number
- Successor & Feasible Successor
- `network` command & wildcard mask
- Passive interface
- EIGRP metric (bandwidth, delay)

**Practice Files:**
```
routing/
├── static/
│   └── static-routing.pkt
├── ospf/
│   ├── ospf-single-area.pkt
│   └── ospf-multi-area.pkt
└── eigrp/
    └── eigrp-basic.pkt
```

---

## 🔀 Switching

### VLAN (Virtual Local Area Network)
Logically segmenting a network at Layer 2.

**Key Concepts:**
- Creating & naming VLANs
- Assigning ports to VLANs (access mode)
- Inter-VLAN routing (Router-on-a-Stick)
- Voice VLAN

### Trunking
Carrying multiple VLANs over a single link.

**Key Concepts:**
- 802.1Q encapsulation
- Trunk port configuration
- Native VLAN
- Allowed VLANs on trunk

### STP (Spanning Tree Protocol)
Preventing Layer 2 loops in switched networks.

**Key Concepts:**
- Root Bridge election
- Port states (Blocking, Listening, Learning, Forwarding)
- PortFast & BPDU Guard
- RSTP (Rapid STP)

**Practice Files:**
```
switching/
├── vlan/
│   ├── vlan-basic.pkt
│   └── inter-vlan-routing.pkt
├── trunking/
│   └── trunk-config.pkt
└── stp/
    └── stp-rstp.pkt
```

---

## 🛡️ ACL (Access Control List)

Filtering network traffic based on rules.

**Key Concepts:**
- Standard ACL (filter by source IP only) — numbered 1–99
- Extended ACL (filter by source, destination, protocol, port) — numbered 100–199
- Named ACL
- Inbound vs Outbound placement
- `permit` / `deny` / implicit deny

**Practice Files:**
```
acl/
├── standard-acl.pkt
├── extended-acl.pkt
└── named-acl.pkt
```

---

## 🌐 NAT (Network Address Translation)

Translating private IP addresses to public IP addresses.

**Key Concepts:**
- Static NAT — one-to-one mapping
- Dynamic NAT — pool of public IPs
- PAT / NAT Overload — many-to-one (most common)
- Inside Local, Inside Global, Outside Local, Outside Global

**Practice Files:**
```
nat/
├── static-nat.pkt
├── dynamic-nat.pkt
└── pat-overload.pkt
```

---

## 🗂️ Full Directory Structure

```
Cisco-Practice/
├── routing/
│   ├── static/
│   ├── ospf/
│   └── eigrp/
├── switching/
│   ├── vlan/
│   ├── trunking/
│   └── stp/
├── acl/
├── nat/
└── README.md
```

---

## 🛠️ Tools

![Cisco](https://img.shields.io/badge/Cisco-1BA0D7?style=flat&logo=cisco&logoColor=white)
![Packet Tracer](https://img.shields.io/badge/Packet_Tracer-1BA0D7?style=flat&logo=cisco&logoColor=white)

> Semua file simulasi menggunakan format `.pkt` (Cisco Packet Tracer)

---

## 📌 Quick Reference — Basic IOS Commands

```bash
# Masuk privileged mode
enable

# Masuk global config
configure terminal

# Save konfigurasi
write memory
# atau
copy running-config startup-config

# Lihat routing table
show ip route

# Lihat VLAN
show vlan brief

# Lihat interface status
show ip interface brief

# Lihat OSPF neighbors
show ip ospf neighbor

# Lihat NAT translations
show ip nat translations

# Lihat ACL
show access-lists
```

---

> *"In networking, every packet has a path — make sure you know it."*
