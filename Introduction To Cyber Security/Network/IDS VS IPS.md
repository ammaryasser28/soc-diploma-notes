# 🔐 IDS & IPS – Intrusion Detection and Prevention Systems

## 📌 Overview
In modern network security architectures, **IDS** and **IPS** play a critical role in detecting and preventing cyber attacks.  
They work alongside firewalls to provide deeper inspection and smarter threat handling.

This document explains **IDS** and **IPS** in a clear, practical, and professional way.

---

## 🕵️ IDS (Intrusion Detection System)

### 🔍 What is IDS?
An **Intrusion Detection System (IDS)** is a security system designed to **monitor network or host activity** and detect suspicious behavior or known attack patterns.

> IDS detects attacks but **does NOT block them**.

---

### ⚙️ How IDS Works
- Monitors all incoming (and sometimes outgoing) packets
- Compares traffic against:
  - Known attack signatures
  - Abnormal behavior patterns
- Generates:
  - Logs
  - Alerts
  - Notifications to the security team

---

### 🧠 Detection Techniques

#### 1️⃣ Signature-Based Detection
- Matches traffic against known attack signatures
- Very accurate for known attacks
- ❌ Cannot detect zero-day attacks

#### 2️⃣ Behavior-Based (Anomaly-Based) Detection
- Learns normal network behavior
- Flags deviations as suspicious
- ✔ Can detect unknown attacks
- ❌ May generate false positives

---

### 🧩 Types of IDS

#### 🌐 Network-based IDS (NIDS)
- Deployed on the network
- Monitors traffic between devices
- Detects:
  - Port scanning
  - DDoS attacks
  - Brute force attempts
  - ARP spoofing

#### 💻 Host-based IDS (HIDS)
- Installed on a specific host or server
- Monitors:
  - File integrity
  - System logs
  - Running processes
- Detects:
  - Malware
  - Unauthorized system changes

---

## 🛑 IPS (Intrusion Prevention System)

### 🚨 What is IPS?
An **Intrusion Prevention System (IPS)** is an evolution of IDS.

> IPS detects attacks **and actively blocks them**.

---

### ⚙️ How IPS Works
1. Inspects packets in real time
2. Detects malicious traffic (same methods as IDS)
3. Takes immediate action:
   - Drop packets
   - Block IP addresses
   - Reset connections
   - Rate-limit traffic

📌 **An attack must be detected before it can be prevented**, which is why IPS acts as IDS first.

---

### 🧠 Key Difference Between IDS & IPS

| Feature | IDS | IPS |
|------|----|----|
| Detection | ✅ Yes | ✅ Yes |
| Prevention | ❌ No | ✅ Yes |
| Traffic Mode | Passive | Inline |
| Action | Alert only | Block + Alert |
| Risk Level | Low | Medium (due to false positives) |

---

## ⚠️ False Positives (Critical Concept)

A **false positive** occurs when:
- Legitimate traffic is mistakenly classified as malicious
- IPS blocks valid traffic

### ❌ Impact
- Service outage
- Website downtime
- Business disruption

### ✔ Best Practice
- Carefully tune IPS rules
- Test rules before deploying in production
- Monitor logs continuously

---

## 🧾 Rule Engines

IDS/IPS rules are commonly written using:
- **Snort**
- **Suricata**

Example rule:
```text
alert tcp any any -> any 80 (msg:"Suspicious HTTP Traffic"; content:"malicious"; sid:1001;)
```
- IDS → Alert only
- IPS → Alert + Block

## 🧠 IDS vs IPS – Simple Analogy

- **IDS** = Security Camera 👀  
- **IPS** = Armed Guard 🚔  

**IDS** sees the attack.  
**IPS** sees the attack **and stops it immediately**.

---

## 🏗️ Deployment Best Practices

- Use **IDS** for visibility and monitoring
- Use **IPS** for prevention in controlled environments
- Combine IDS and IPS with:
  - Firewalls
  - DMZ
  - SIEM
- Always follow the **Defense in Depth** security strategy

---

## 🎯 Real-World Example

### Scenario: Port Scanning Attack

#### 🔍 IDS
- Detects the port scan
- Sends an alert to the security team

#### 🛑 IPS
- Detects the port scan
- Blocks the attacker IP instantly
