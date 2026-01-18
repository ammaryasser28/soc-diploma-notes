# 🔐 Stateless Firewalls (Packet Filtering)

## 📌 Overview
A **Stateless Firewall** is the most basic type of firewall. It filters network traffic by examining each packet **independently**, without tracking any connection or session state.

Routers can perform basic packet filtering using **Access Control Lists (ACLs)**. When configured this way, a router effectively acts as a stateless firewall.

---

## 🔁 Router as a Stateless Firewall
Routers are primarily used for routing traffic. However, when packet filtering rules are applied, they can also function as **stateless firewalls**.

These rules define:
- Which traffic is allowed
- Which traffic is denied

---

## 📜 Access Control Lists (ACLs)

### 🔹 What is an ACL?
An **Access Control List (ACL)** is a set of rules used to control network traffic.  
Each rule specifies:
- Action (Allow / Deny)
- Source IP address
- Destination IP address
- Source and/or destination port
- Protocol (TCP / UDP)

### 🔹 Example ACL Rule
- ALLOW TCP
- FROM 192.168.1.0/24
- TO 10.0.0.10
- PORT 80

This rule allows HTTP traffic from the internal network to a web server.

---

## 🧠 How Stateless Firewalls Work
A stateless firewall:
- Inspects **each packet separately**
- Does **not** remember previous packets
- Does **not** track sessions or connections

Because of this, both incoming and outgoing traffic must be explicitly allowed by rules.

---

## 🔍 Inspection Scope

### 🔹 OSI Layers
Stateless firewalls inspect:
- **Layer 3 (Network Layer)**
  - Source IP
  - Destination IP
- **Layer 4 (Transport Layer)**
  - Source Port
  - Destination Port
  - Protocol (TCP / UDP)

### 🔹 What is NOT inspected
- Application type
- Application data
- Packet payload
- Connection state

This makes stateless firewalls equivalent to **Shallow Packet Inspection**.

---

## ⚠️ Limitations
- No session awareness
- Cannot distinguish legitimate traffic from spoofed packets
- Requires many rules for bidirectional traffic
- Lower security compared to stateful and next-generation firewalls

---

## ✅ Advantages
- Very fast processing
- Low resource usage
- Simple configuration
- Suitable for basic filtering and high-speed networks

---

## 🆚 Summary Table

| Feature | Stateless Firewall |
|------|----------------|
| Session Tracking | ❌ |
| Packet Header Inspection | ✅ |
| Payload Inspection | ❌ |
| ACL-Based Filtering | ✅ |
| Security Level | Basic |


