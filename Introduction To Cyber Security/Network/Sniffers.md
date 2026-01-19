# 🐶 Sniffers & Protocol Analyzers

## 📌 Overview
**Sniffers** are essential tools in networking and cybersecurity used to capture network traffic.  
They allow security engineers and network administrators to analyze, troubleshoot, and monitor network communications at a low level.

---

## 🧠 What is a Sniffer?

A **Sniffer** is a software tool that:
> Captures network packets that are visible to a specific **network interface**.

- It captures **raw packets** (headers + payload)
- It does **not interpret** the packet contents by itself

---

## 📡 Importance of Network Interface Selection

A device may have multiple network interfaces, such as:
- Ethernet
- Wi-Fi
- Virtual interfaces

⚠️ **A sniffer only captures traffic that passes through the selected interface**.  
Choosing the wrong interface means missing important packets.

---

## 📍 Deployment Example

### Sniffer on a Perimeter Firewall
If a sniffer is placed on a **perimeter firewall**:
- It captures traffic going **to the Internet**
- It captures traffic coming **from the Internet**
- Useful for:
  - Monitoring external attacks
  - Analyzing VPN and web traffic

📌 It will not capture internal traffic unless it passes through that firewall.

---

## 📦 What Do Sniffers Capture?

- Raw packets only
- No protocol decoding
- No human-readable interpretation

Think of it as:
> A raw recording without subtitles 🎧

---

## 🔍 Protocol Analyzer

A **Protocol Analyzer** is software that:
> Interprets raw packets and translates them into a human-readable format.

It understands protocols such as:
- TCP / UDP
- HTTP / HTTPS
- DNS
- ARP
- ICMP

And displays:
- Source & Destination IPs
- Port numbers
- Flags
- Sessions
- Requests and responses

---

## 🔗 Relationship Between Sniffer & Analyzer

| Component | Function |
|--------|----------|
| Sniffer | Captures raw packets |
| Protocol Analyzer | Decodes and interprets packets |

---

## 🦈 Wireshark

**Wireshark** is both:
- A **Sniffer**
- A **Protocol Analyzer**

It:
- Captures packets
- Decodes them
- Displays results in a human-readable format

📌 What you see in Wireshark is the result of **protocol analysis**, not raw data.

---

## ⚡ tcpdump

**tcpdump** is a command-line-based tool that:
- Acts as a sniffer and protocol analyzer
- Is faster and lighter than GUI-based tools
- Is ideal for servers and firewalls

Example:
```bash
tcpdump -i eth0
```
## ⚖️ Wireshark vs tcpdump

| Feature | Wireshark | tcpdump |
|------|----------|---------|
| Interface | GUI | CLI |
| Performance | Moderate | High |
| Server Friendly | ❌ | ✅ |
| Learning Curve | Easy | Advanced |
| Analysis Capability | Excellent | Excellent |

---

## 🔐 Common Use Cases

- Network troubleshooting
- Packet analysis
- Incident response
- Malware investigation
- IDS/IPS rule verification
- Learning networking protocols

---

## ⚠️ Legal Notice

Using sniffers without proper authorization is **illegal and unethical**.
