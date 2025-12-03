---

# 🌐 **Networking Fundamentals — Complete Cloud & DevOps Reference**

<p align="center">
  <img src="https://img.shields.io/badge/Networking-Fundamentals-blue" />
  <img src="https://img.shields.io/badge/Cloud-Ready-orange" />
  <img src="https://img.shields.io/badge/DevOps-Engineer_Level-success" />
  <img src="https://img.shields.io/badge/Status-Updated_2025-brightgreen" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-black?logo=github" />
  </a>
</p>

A **concise**, **practical**, and **highly visual** reference guide covering everything you actually use in **Cloud**, **DevOps**, **SRE**, and **Infrastructure Engineering**.

---

# 📘 **Table of Contents**


1. [🌍 IP Addressing](#-ip-addressing)
2. [📐 CIDR & Subnetting](#-cidr--subnetting)
3. [🧱 OSI Model (7 Layers)](#-osi-model-7-layers)
4. [📡 TCP/IP Model](#-tcpip-model)
5. [🌐 DNS Deep Dive](#-dns-deep-dive)
6. [🔒 HTTP vs HTTPS](#-http-vs-https)
7. [🚏 Routing, NAT & Gateways](#-routing-nat--gateways)
8. [🛠️ Network Troubleshooting](#️-network-troubleshooting)
9. [❓ Interview Questions](#-interview-ready-networking-questions)
10. [👤 Author](#-author)
11. [❤️ Footer](#️-footer)

---

# 🌍 **IP Addressing**

## 🔹 **IPv4**

* 32-bit
* Example → `192.168.1.10`
* Format → **Network + Host**
* Types:

  * **Public** (Internet reachable)
  * **Private** (VPC/LAN)
  * **Static** / **Dynamic**

### **Private IPv4 Ranges**

```
10.0.0.0/8
172.16.0.0 – 172.31.255.255
192.168.0.0/16
```

---

## 🔹 **IPv6**

* 128-bit
* Example → `2001:db8::7334`
* Benefits:

  * No NAT
  * Auto-configuration
  * Insanely huge address pool
  * Modern, scalable, future-proof

---

# 📐 **CIDR & Subnetting**

### 🔹 **CIDR Notation**

Defines number of network bits.
Example: `/24`, `/26`.

---

## 🔢 **Host Calculation Formula**

```
Hosts = 2^(32 - CIDR) - 2
```

### Usable Hosts Table

| CIDR | Hosts |
| ---- | ----- |
| /24  | 254   |
| /25  | 126   |
| /26  | 62    |
| /27  | 30    |
| /28  | 14    |
| /29  | 6     |

---

## 📘 **Subnet Masks**

| CIDR | Mask            |
| ---- | --------------- |
| /8   | 255.0.0.0       |
| /16  | 255.255.0.0     |
| /24  | 255.255.255.0   |
| /25  | 255.255.255.128 |
| /26  | 255.255.255.192 |
| /27  | 255.255.255.224 |

---

## 🔍 **Subnet Range Example**

```
IP    : 192.168.1.130
CIDR  : /26
Block : 64
```

### Result

* Network → **192.168.1.128**
* First Host → **192.168.1.129**
* Last Host → **192.168.1.190**
* Broadcast → **192.168.1.191**

---

# 🧱 **OSI Model (7 Layers)**

```
7 — Application     → HTTP, DNS, SSH  
6 — Presentation    → SSL/TLS  
5 — Session         → Authentication, connections  
4 — Transport       → TCP/UDP  
3 — Network         → IP routing  
2 — Data Link       → MAC, ARP  
1 — Physical        → Cables, WiFi, signals
```

---

## 🎯 **Layer Summary**

| Layer | Purpose                      |
| ----- | ---------------------------- |
| 7     | End-user protocols           |
| 6     | Encryption & formatting      |
| 5     | Session lifecycle            |
| 4     | Reliable (TCP) vs Fast (UDP) |
| 3     | Routing + IP addressing      |
| 2     | LAN-level communication      |
| 1     | Physical transmission        |

---

# 📡 **TCP/IP Model**

```
Application     → HTTP, DNS, SMTP  
Transport       → TCP, UDP  
Internet        → IP, ICMP  
Network Access  → Wi-Fi, Ethernet
```

---

# 🌐 **DNS Deep Dive**

### 🔹 **What DNS Does**

Resolves **domain → IP**

```
example.com → 93.184.216.34
```

---

## 📘 **DNS Record Types**

| Type  | Purpose                 |
| ----- | ----------------------- |
| A     | IPv4 address            |
| AAAA  | IPv6 address            |
| CNAME | Alias                   |
| MX    | Mail servers            |
| TXT   | SPF, DKIM, verification |

---

# 🔒 **HTTP vs HTTPS**

## 🌐 HTTP

* Port: **80**
* Not encrypted
* Vulnerable

## 🔐 HTTPS

* Port: **443**
* Encrypted (SSL/TLS)
* Secure, mandatory today

---

### 🔹 Common HTTP Methods

`GET`, `POST`, `PUT`, `DELETE`, `PATCH`

### 🔹 Status Codes

* **200** OK
* **301** Redirect
* **401** Unauthorized
* **403** Forbidden
* **404** Not Found
* **500** Server Error

---

# 🚏 **Routing, NAT & Gateways**

### 🔹 Router

Moves packets between networks (Layer 3).

### 🔹 Switch

LAN communication using MAC (Layer 2).

### 🔹 Internet Gateway

Allows VPC to access the Internet.

### 🔹 NAT (Network Address Translation)

Enables **private** subnets to access the internet **without public IPs**.

---

# 🛠️ **Network Troubleshooting**

### 🔧 Commands Reference

| Goal           | Command                  |
| -------------- | ------------------------ |
| Connectivity   | `ping`                   |
| Path tracing   | `traceroute` / `tracert` |
| DNS lookup     | `nslookup`, `dig`        |
| Port check     | `telnet <IP> <PORT>`     |
| Endpoint test  | `curl http://ip:port`    |
| Packet capture | `tcpdump`                |

---

## ⚠ Common Issues

* Wrong route table
* Overlapping CIDRs
* Security group blocking
* NACL denies
* Wrong DNS record
* NAT misconfiguration

---

# ❓ **Interview-Ready Networking Questions**

## 🔥 IPv4/IPv6 & Subnetting

1. Why do private IPs exist?
2. Impact of overlapping VPC CIDRs?
3. Difference between `/24` and `/16` in actual networks?
4. Subnet range for `/26`?
5. Why subtract **2** in host count?

---

## 🔥 OSI & TCP/IP

6. SSL/TLS works at which OSI layer?
7. Layer 3 vs Layer 4 failures?
8. Why UDP is unreliable?
9. ARP workflow?

---

## 🔥 Routing & Gateways

10. What is a default route?
11. What is a blackhole route?
12. NAT Gateway vs Internet Gateway?
13. Why private subnets can't use IGW?
14. What is asymmetric routing?

---

## 🔥 DNS

15. What is recursive DNS?
16. Why no CNAME at root domain?
17. A vs CNAME vs ALIAS?
18. How MX works?

---

## 🔥 Troubleshooting

19. Ping works but SSH fails — why?
20. DNS resolves but site unreachable — next steps?
21. Traceroute stops mid-path — meaning?
22. Packet drop debugging steps?

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
