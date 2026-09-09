# Technical Documentation

This directory contains the detailed technical documentation for the **Enterprise Network Security & Infrastructure Lab**.

The full Network Design Proposal documents the architecture, addressing, routing, security controls, and high-availability considerations used to design the simulated enterprise network.

## Network Design Proposal

📄 **[View the Full Network Design Proposal](https://github.com/Dajeal/enterprise-network-security-lab/blob/main/documentation/Network_Design_Proposal_DWP.pdf)**

The proposal contains the complete technical analysis and design decisions behind the Cisco Packet Tracer implementation.

---

## Documentation Contents

### 1. Network Architecture

The proposal documents the overall **Dual-Path Dual-Layer network architecture**, including:

- Red Rail for inbound Internet traffic
- Green Rail for outbound Internet traffic
- Internal employee network
- DMZ
- Protected Intranet
- Four-firewall security architecture
- Enterprise server connectivity

---

### 2. IPv4 Addressing & Subnet Design

The network was designed within:

`10.53.0.0/16`

The documentation includes subnet calculations and capacity planning for:

| Network | Address |
|---|---|
| Internal | `10.53.1.0/24` |
| DMZ | `10.53.2.0/26` |
| Intranet | `10.53.2.64/26` |
| Red Transit | `10.53.2.128/29` |
| Green Transit | `10.53.2.136/29` |

Subnet sizes were selected according to device and infrastructure requirements while conserving IPv4 address space.

---

### 3. Infrastructure Addressing

The proposal includes addressing assignments for:

- Routers
- Firewalls
- Switch management interfaces
- Servers
- Gateways
- Internal clients

Static addressing was used for network infrastructure and enterprise servers.

---

### 4. Switching & Capacity Planning

Switch requirements were calculated based on expected:

- Employee workstations
- Wireless access points
- Servers
- Router interfaces
- Firewall interfaces
- Infrastructure management interfaces

The design supports an enterprise environment containing hundreds of potential endpoints.

---

### 5. Enterprise Server Placement

The proposal explains the security and connectivity requirements used to determine placement for:

- Active Directory Server
- PostgreSQL Database Server
- HR Server
- E-Commerce / Sales Server
- Remote Desktop Gateway
- Web Security Appliance Gateway

Public-facing services were separated from protected internal services using DMZ and Intranet security zones.

---

### 6. NAT / PAT Design

The network was designed around two public IPv4 addresses.

The proposal documents translation requirements for:

- Public HTTPS access to the e-commerce server
- Remote employee access
- Outbound employee Internet connectivity
- Private-to-public address translation

---

### 7. Static Routing

Detailed routing tables document how traffic moves between:

`Internet → Routers → Firewalls → DMZ/Intranet → Internal Network`

The design uses both static and default routes while intentionally limiting unnecessary routes between security zones.

---

### 8. Firewall ACL Design

The documentation contains the complete firewall rulesets for all four firewalls.

Rules were designed around specific application requirements and include:

| Service | Port |
|---|---:|
| HTTP | TCP 80 |
| HTTPS | TCP 443 |
| LDAP | TCP 389 |
| RDP | TCP 3389 |
| PostgreSQL | TCP 5432 |

The ACL design follows a least-privilege approach by allowing required application traffic and denying unauthorized communication.

---

### 9. High Availability

The proposal evaluates modifications designed to reduce single points of failure.

Topics include:

- Redundant switches
- Redundant network links
- Spanning Tree Protocol (STP)
- Virtual IP services
- Firewall clustering
- Active/Active firewall architecture
- Active/Passive firewall architecture
- Firewall failover

The final design recommends **Active/Passive firewall clustering** to provide redundancy while maintaining predictable failover and manageable operational complexity.

---

## Supporting Lab

The corresponding Cisco Packet Tracer implementation can be found in:

**[Packet Tracer Lab](../packet-tracer/design-project.pkt)**

The `.pkt` file contains the network topology and device configurations used to implement the design.

---

## Return to Project Overview

**[← Back to Main README](../README.md)**
