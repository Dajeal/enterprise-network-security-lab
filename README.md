# enterprise-network-security-lab
# Enterprise Network Security & Infrastructure Lab

## Project Overview

Designed and implemented a **segmented enterprise network in Cisco Packet Tracer** for a simulated business environment supporting internal users, public-facing services, remote access, Active Directory, database services, and controlled Internet connectivity.

The project demonstrates hands-on networking and infrastructure skills applicable to **Systems Administrator, Junior Network Administrator, and IT Infrastructure** roles, including **TCP/IP, IPv4 subnetting, routing, switching, NAT/PAT, firewall ACLs, network segmentation, DMZ architecture, and high-availability planning**.

A complete technical design proposal is included in this repository documenting the network architecture, addressing scheme, routing, NAT, firewall rules, server placement, and high-availability recommendations.

---

## Skills Demonstrated

- **TCP/IP & IPv4 Networking**
- **IPv4 Subnetting / VLSM**
- **Static & Default Routing**
- **Cisco Routing & Switching**
- **NAT / PAT**
- **Firewall ACL Configuration**
- **Network Segmentation**
- **DMZ Architecture**
- **TCP/UDP Port & Application Traffic Analysis**
- **Active Directory Network Integration**
- **Remote Access / RDP Architecture**
- **Network Troubleshooting**
- **High Availability & Redundancy**
- **Spanning Tree Protocol (STP)**
- **Firewall Clustering / Failover**
- **Enterprise Network Documentation**

---

## Technologies & Protocols

| Category | Technologies / Concepts |
|---|---|
| Network Simulation | Cisco Packet Tracer |
| Networking | TCP/IP, IPv4, VLSM, Static Routing, Default Routes |
| Switching | Layer 2 Switching, STP, Switch Management |
| Security | ACLs, DMZ, Network Segmentation, Least Privilege |
| Address Translation | NAT, PAT |
| Enterprise Services | Active Directory, RDP Gateway, PostgreSQL, Web Proxy |
| Application Protocols | HTTPS, HTTP, LDAP, RDP, PostgreSQL |
| Availability | Redundant Links, Virtual IPs, Active/Passive Failover |

---

## Network Architecture

The environment uses a **Dual-Path Dual-Layer firewall architecture** separating inbound and outbound traffic across multiple security zones.

```text
                         INTERNET
                       /          \
                  Red Rail      Green Rail
                     |              |
                  Firewall       Firewall
                     |              |
                    DMZ          Intranet
                     |              |
                  Firewall       Firewall
                      \             /
                       \           /
                       Internal LAN
                            |
                    Employee Systems
```

The network was segmented into five IPv4 subnets within the `10.53.0.0/16` address space:

| Network | Subnet | Purpose |
|---|---|---|
| Internal | `10.53.1.0/24` | Employee workstations and APs |
| DMZ | `10.53.2.0/26` | Public-facing services |
| Intranet | `10.53.2.64/26` | Protected enterprise servers |
| Red Transit | `10.53.2.128/29` | Inbound network infrastructure |
| Green Transit | `10.53.2.136/29` | Outbound network infrastructure |

Subnet sizes were selected based on host requirements while minimizing unnecessary address consumption.

---

## Project Highlights

### Enterprise Network Design

Designed a multi-segment network supporting up to **200 wired workstations, 20 wireless access points, 100 wireless users, and multiple enterprise servers**, including Active Directory, database, HR, e-commerce, remote-access, and web-security services.

### Routing & Switching

Configured and documented:

- Router and firewall interface addressing
- Static routes
- Default routes
- Layer 2 switching
- Switch management addressing
- Infrastructure capacity requirements

### Network Security

Implemented a segmented security model using **four firewalls** and application-specific ACLs.

Traffic controls were designed around business requirements using protocols including:

```text
HTTPS       TCP/443
HTTP        TCP/80
LDAP        TCP/389
RDP         TCP/3389
PostgreSQL  TCP/5432
```

The design restricts unnecessary communication between the Internet, DMZ, internal clients, and protected enterprise services.

### NAT / PAT

Designed NAT and PAT rules allowing:

- Public HTTPS access to the e-commerce server
- Remote employee connectivity through an RDP Gateway
- Outbound employee Internet access
- Multiple private systems to share limited public IPv4 addresses

### High Availability

Evaluated infrastructure improvements to eliminate single points of failure, including:

- Redundant switches and network links
- Spanning Tree Protocol
- Virtual IP addressing
- Firewall clustering
- Active/Active vs. Active/Passive failover

Recommended an **Active/Passive firewall architecture** to provide predictable failover while minimizing operational complexity.

---

## System Administration Relevance

Although this project focuses heavily on networking, it also demonstrates infrastructure knowledge directly applicable to systems administration.

The environment required designing network connectivity for:

- **Active Directory authentication**
- **Database services**
- **Remote Desktop access**
- **Internal web applications**
- **Public-facing servers**
- **Secure Internet access**

The project reinforced how server availability depends on correctly configured **IP addressing, DNS-aware network design, routing, NAT, firewall policies, TCP/UDP ports, and network segmentation**.

---

## Project Files

```text
enterprise-network-security-lab/
│
├── README.md
├── documentation/
│   └── Network-Design-Proposal.pdf
└── packet-tracer/
    └── design-project.pkt
```

### Technical Documentation

For detailed architecture, subnet calculations, device addressing, server placement, NAT rules, static routes, firewall rules, and high-availability analysis, see:

**[Network Design Proposal](documentation/Network-Design-Proposal.pdf)**

### Packet Tracer Implementation

The Cisco Packet Tracer project containing the implemented network topology and device configurations is available here:

**[Packet Tracer Lab](packet-tracer/design-project.pkt)**

---

## Key Takeaways

This project strengthened my ability to design, configure, document, and troubleshoot the network infrastructure that enterprise systems depend on.

Key areas of practical experience include:

**TCP/IP • Subnetting • Routing • Switching • NAT/PAT • Firewall ACLs • Network Segmentation • DMZs • Active Directory Connectivity • RDP • High Availability • Infrastructure Troubleshooting**
