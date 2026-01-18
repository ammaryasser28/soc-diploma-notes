# 🛡️ Deep Packet Inspection (DPI)

## 📌 Overview
Firewalls are a fundamental component of network security. Traditional firewalls rely on **Shallow Packet Inspection**, which inspects only packet headers. However, modern cyber threats require deeper visibility into network traffic.  
This is where **Deep Packet Inspection (DPI)** becomes essential.

This document explains:
- Shallow vs Deep Packet Inspection
- Why DPI is important
- A real-world SMB protocol example

---

## 📦 Packet Structure
Each network packet consists of two main parts:

### 🔹 Header
Contains routing and control information:
- Source IP Address
- Destination IP Address
- Source Port
- Destination Port
- Protocol (TCP / UDP)

### 🔹 Payload
- The actual transmitted data
- Application-level information

---

## 🟡 Shallow Packet Inspection (SPI)

### 🔹 Definition
Shallow Packet Inspection is the traditional firewall filtering technique that analyzes **only packet header information**.

### 🔹 Filtering Criteria
Firewalls using SPI can filter traffic based on:
- IP addresses
- Port numbers
- Transport protocol (TCP / UDP)

### 🔹 Example Rule
- ALLOW TCP
- FROM 10.0.10.0/24
- TO 10.0.30.10
- PORT 445


If the IP addresses, port, and protocol match, the traffic is allowed.

### ❗ Limitation
SPI cannot identify:
- The application type
- The application version

For example:
- Port `445` is used for **SMB**
- SMB has multiple versions:
  - **SMBv1** (deprecated and insecure)
  - **SMBv2 / SMBv3** (secure)

Using shallow inspection, the firewall cannot distinguish between these versions.

---

## 🔴 Deep Packet Inspection (DPI)

### 🔹 Definition
Deep Packet Inspection analyzes:
- Packet headers **and**
- Packet payload (actual data)

This allows the firewall to understand the **application layer (Layer 7)**.

### 🔹 Capabilities
- Application identification
- Application version detection
- Granular security policy enforcement
- Blocking insecure or malicious traffic

---

## 🧪 Real-World Example: SMB Traffic

### Scenario
A firewall rule allows:
- TCP traffic
- From `10.0.10.0/24`
- To `10.0.30.10`
- On port `445`

### 🚫 Without DPI
- All SMB traffic is allowed
- SMBv1 traffic passes
- Network is exposed to known SMBv1 vulnerabilities

### ✅ With DPI
The firewall:
1. Validates IP, port, and protocol
2. Inspects the payload
3. Identifies the SMB version
4. Allows **SMBv2 / SMBv3**
5. Blocks **SMBv1**

---

## 🔐 Why Deep Packet Inspection Matters
- Prevents exploitation of outdated protocols
- Improves application-level visibility
- Enhances overall network security
- Core feature of **Next-Generation Firewalls (NGFW)**

---

## 🆚 Comparison

| Feature | Shallow Inspection | Deep Packet Inspection |
|------|------------------|------------------------|
| Header Analysis | ✅ | ✅ |
| Payload Analysis | ❌ | ✅ |
| Application Awareness | ❌ | ✅ |
| Version Detection | ❌ | ✅ |
| Se
