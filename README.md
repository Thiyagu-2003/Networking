---

# 🌐 Networking Fundamentals — Complete Cloud & DevOps Reference

![Networking](https://img.shields.io/badge/Networking-Fundamentals-blue)
![Cloud](https://img.shields.io/badge/Cloud-Ready-orange)
![DevOps](https://img.shields.io/badge/DevOps-Engineer_Level-success)
![Status](https://img.shields.io/badge/Status-Updated_2025-brightgreen)
 <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
</a>

A practical, visually clean, and real-world-focused guide to everything networking you actually need in **Cloud**, **DevOps**, **SRE**, and **Infrastructure** roles.

---

## 📘 Table of Contents

1. [🌍 IP Addressing](#-ip-addressing)
2. [📐 CIDR & Subnetting](#-cidr--subnetting)
3. [🧱 OSI Model](#-osi-model)
4. [📡 TCP/IP Model](#-tcpip-model)
5. [🌐 DNS Deep Dive](#-dns-deep-dive)
6. [🔒 HTTP vs HTTPS](#-http-vs-https)
7. [🚏 Routing, NAT & Gateways](#-routing-nat--gateways)
8. [🛠️ Network Troubleshooting](#️-network-troubleshooting)
9. [❓ Interview-Ready Networking Questions](#-interview-ready-networking-questions)
10. [🙋‍♂️ Author](#️-author)

---

# 🌍 IP Addressing

## 🔹 IPv4

* 32-bit → `192.168.1.10`
* Split into **Network + Host**
* Address types:

  * **Public** → internet reachable
  * **Private** → internal LAN/VPC
  * **Static/Dynamic**

### Private Ranges

* `10.0.0.0/8`
* `172.16.0.0 – 172.31.255.255`
* `192.168.0.0/16`

---

## 🔹 IPv6

* 128-bit → `2001:db8::7334`
* Designed to replace IPv4
* Advantages:

  * No NAT needed
  * Auto-configuration
  * Massive address pool
  * Built for scalable modern networks

---

# 📐 CIDR & Subnetting

### CIDR Notation

Example: `/24`, `/26` → defines network bits.

---

## 🔢 Host Calculation

```
Hosts = 2^(32 − CIDR) − 2
```

| CIDR | Usable Hosts |
| ---- | ------------ |
| /24  | 254          |
| /25  | 126          |
| /26  | 62           |
| /27  | 30           |
| /28  | 14           |
| /29  | 6            |

---

## 📘 Subnet Masks

| CIDR | Mask            |
| ---- | --------------- |
| /8   | 255.0.0.0       |
| /16  | 255.255.0.0     |
| /24  | 255.255.255.0   |
| /25  | 255.255.255.128 |
| /26  | 255.255.255.192 |
| /27  | 255.255.255.224 |

---

## 🔍 Subnet Range Example

```
IP     : 192.168.1.130
CIDR   : /26
Block  : 64
Ranges : 0–63, 64–127, 128–191, 192–255
```

Result:

* Network → `192.168.1.128`
* First Host → `192.168.1.129`
* Last Host → `192.168.1.190`
* Broadcast → `192.168.1.191`

---

# 🧱 OSI Model (All 7 Layers)

```
7 — Application     (HTTP, DNS, SSH)  
6 — Presentation    (SSL/TLS, compression)  
5 — Session         (connections, authentication)  
4 — Transport       (TCP/UDP)  
3 — Network         (IP routing)  
2 — Data Link       (MAC, switches, ARP)  
1 — Physical        (cables, signals, Wi-Fi)
```

---

## Layer Purpose Summary

| Layer | Role                                |
| ----- | ----------------------------------- |
| 7     | End-user protocols (HTTP, SSH, DNS) |
| 6     | Encryption/formatting (TLS)         |
| 5     | Session lifecycle                   |
| 4     | Reliable (TCP) vs fast (UDP)        |
| 3     | Routing + IP addressing             |
| 2     | LAN-level communication             |
| 1     | Physical media                      |

---

# 📡 TCP/IP Model

```
Application     → HTTP, DNS, SSH  
Transport       → TCP, UDP  
Internet        → IP, ICMP  
Network Access  → Ethernet, Wi-Fi
```

---

# 🌐 DNS Deep Dive

### What DNS Does

Maps a domain → IP
`example.com → 93.184.216.34`

---

## Record Types

| Record | Purpose                 |
| ------ | ----------------------- |
| A      | IPv4                    |
| AAAA   | IPv6                    |
| CNAME  | Alias                   |
| MX     | Mail server             |
| TXT    | SPF, DKIM, verification |

---

# 🔒 HTTP vs HTTPS

## HTTP

* Port **80**
* Unencrypted

## HTTPS

* Port **443**
* Encrypted via **SSL/TLS**

---

### Common HTTP Methods

`GET`, `POST`, `PUT`, `DELETE`, `PATCH`

### Status Codes

* `200` OK
* `301` Redirect
* `401` Unauthorized
* `403` Forbidden
* `404` Not Found
* `500` Server Error

---

# 🚏 Routing, NAT & Gateways

### Router

Moves traffic between networks

### Switch

LAN-level communication, uses MAC

### Internet Gateway

Entry/exit point from VPC

### NAT

Converts private ↔ public IP
Used for private-subnet internet access without exposing hosts.

---

# 🛠️ Network Troubleshooting

| Goal           | Command               |
| -------------- | --------------------- |
| Connectivity   | `ping`                |
| Path tracing   | `traceroute`          |
| DNS lookup     | `nslookup`, `dig`     |
| Port check     | `telnet <ip> <port>`  |
| Endpoint test  | `curl http://ip:port` |
| Packet capture | `tcpdump`             |

---

## Common Root Causes

* Wrong route table
* Overlapping CIDRs
* Security groups blocking
* NACL misalignment
* DNS misconfigured
* NAT not set up correctly

---

# ❓ Interview-Ready Networking Questions

## 🔥 IPv4/IPv6 & Subnetting

1. Why do private IP ranges exist?
2. What happens if two VPCs have overlapping CIDRs?
3. Explain the difference between `/24` and `/16` in real-world usage.
4. How do you find the subnet range for `/26`?
5. Why do we subtract **2** in host calculations?

---

## 🔥 OSI & TCP/IP

6. Which OSI layer does SSL/TLS operate at?
7. What’s the difference between Layer 3 & Layer 4 failures?
8. Why does UDP not guarantee delivery?
9. How does ARP work?

---

## 🔥 Routing & Gateways

10. What is a default route?
11. What is a blackhole route?
12. How does NAT Gateway differ from Internet Gateway?
13. Why can't private-subnet EC2 instances use an IGW directly?
14. What is asymmetric routing, and why is it dangerous?

---

## 🔥 DNS

15. How does recursive DNS work internally?
16. Why is CNAME never used at the root domain?
17. Difference between A, CNAME, and ALIAS?
18. How do MX records work?

---

## 🔥 Troubleshooting

19. Ping works but SSH doesn’t — what's the cause?
20. DNS resolves but site unreachable — what checks next?
21. Traceroute stops halfway — what does that indicate?
22. How do you diagnose packet drops?

---

# 👤 **Author**

```
Name: Thiyagu S
Role: Cloud & DevOps Learner
Location: India 🇮🇳
GitHub: Thiyagu-2003
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---
