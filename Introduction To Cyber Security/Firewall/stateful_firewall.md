# 🔐 Stateful Firewalls

## 📌 Overview
A **Stateful Firewall** is one of the most commonly used firewall types today.  
It includes all the capabilities of a **Stateless Firewall**, with an important enhancement:  
👉 **It tracks active network sessions using a state table**.

This allows the firewall to understand whether traffic belongs to a legitimate, established connection or not.

---

## 🧠 Key Concept: State Table

### 🔹 What is a State Table?
The **state table** is an internal table maintained by the firewall to track all active connections.

Each entry typically contains:
- Source IP address
- Destination IP address
- Source port
- Destination port
- Protocol (TCP / UDP)
- Connection state (SYN_SENT, ESTABLISHED, FIN_WAIT, etc.)

<img width="947" height="98" alt="image" src="https://github.com/user-attachments/assets/42742c7a-82cf-495a-a6fb-fe0ad97af070" />

This enables the firewall to make smarter decisions about traffic.

---

## 🔁 How Stateful Firewalls Work

Stateful firewalls monitor the **TCP 3-way handshake** to verify that a connection is legitimate.

### TCP States Tracked:
1. `SYN_SENT`
2. `ESTABLISHED`
3. `FIN / RST` (connection termination)

Stateless firewalls cannot track or understand these states.

---

## 🚫 Preventing Random Packets

### Example: Random ACK Packet

- **Stateless Firewall**:
  - Inspects the packet header
  - If it matches a rule → allows it ❌

- **Stateful Firewall**:
  - Checks the state table
  - No active session found
  - Drops the packet 🛑

This protects the network from spoofed or malicious packets.

---

## 🔄 Step-by-Step TCP Session Handling

### 1️⃣ Client Initiates Connection
A PC wants to connect to a web server over port 80.

- The PC sends a **TCP SYN** packet to destination port `80`.

#### Firewall Actions:
- Inspects the packet
- Identifies it as outbound traffic (inside → internet)
- Checks the state table:
  - No existing entry (new connection)
- Checks firewall rules (ACL):
  - Finds a rule allowing HTTP traffic
- Allows the packet
- Creates a new entry in the state table:
  - State: `SYN_SENT`

---

### 2️⃣ Server Responds (SYN/ACK)
- The web server replies with a **SYN/ACK** packet.

#### Firewall Actions:
- Inspects the packet
- Matches it against the state table entry
- Verifies:
  - Source and destination IPs
  - Port numbers
- Updates the state:
  - `ESTABLISHED`
- Allows the packet

---

### 3️⃣ Data Transfer
- All subsequent packets:
  - Are checked against the **state table only**
  - Do NOT need to be evaluated against firewall rules (ACL)

This improves both performance and security.

---

### 4️⃣ Session Termination
- When the firewall detects a:
  - `FIN` packet
  - or `RST` packet

#### Firewall Actions:
- Identifies that the session has ended
- Removes the corresponding entry from the state table

---

## 🆚 Stateless vs Stateful Firewalls

| Feature | Stateless Firewall | Stateful Firewall |
|------|------------------|------------------|
| Session Tracking | ❌ | ✅ |
| TCP Handshake Awareness | ❌ | ✅ |
| State Table | ❌ | ✅ |
| Random Packet Protection | ❌ | ✅ |
| Rule Checking | Every packet | First packet only |
| Security Level | Basic | Moderate / High |

