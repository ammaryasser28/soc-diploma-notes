# Port Scanning – Fundamentals

## 📌 What is Port Scanning?
**Port Scanning** is the process of identifying **open ports (services)** running on a target system.

Each open port represents a **running service**, and each service can potentially be a **point of entry** for an attacker.

---

## 🎯 Why Port Scanning is Important for Attackers
To attack a system remotely, an attacker must:

1. Identify the **IP address** of the target system
2. Scan for **open ports**
3. Determine the **service and application** running on each open port

📌 Knowing the open port helps the attacker identify the application:
- Port **80** → HTTP
- Port **443** → HTTPS
- Port **22** → SSH

---

## 🛠 Common Port Scanning Tool – Nmap
Attackers (and defenders) commonly use **Nmap** for port scanning.

Nmap can detect:
- Open ports
- Running services
- Service versions
- Operating system (OS detection)
- Additional service details

⚠️ **Why Service Version Matters**
Knowing the exact version of a service allows attackers to search for **known vulnerabilities** that exist in that specific version.

---

## 🔐 Security Principle – Least Privilege
Due to the existence of port scanning tools:
> Only **necessary ports** should be open.

Every open port increases the **attack surface** of the system.

---

## 🔍 How Does a Port Scanner Detect Open Ports?

---

## 🔹 TCP Port Scanning

TCP uses the **3-Way Handshake** mechanism.

### Process:
1. Scanner sends a **TCP SYN** packet to a specific port
2. The target system responds:

### Responses:
| Response | Meaning |
|--------|--------|
| `SYN / ACK` | Port is **OPEN** |
| `RST` | Port is **CLOSED** |

📌 The scanner usually does **not complete the handshake** to remain stealthy.

---

## 🔹 UDP Port Scanning

UDP does **not** use:
- SYN
- ACK
- RST
- Handshakes

So a different method is used.

### Process:
1. Scanner sends a **UDP packet** to the target IP and port
2. The Operating System checks the port status

### Responses:
| Response | Meaning |
|--------|--------|
| `ICMP Destination Unreachable (Port Unreachable)` | Port is **CLOSED** |
| No Response | Port is **OPEN or FILTERED** |

📌 Some UDP services (e.g. **DNS on port 53**) may respond with a reply if the port is open.

---

## 📡 Role of ICMP in UDP Scanning
Since UDP cannot report errors:
- The OS uses **ICMP** to report delivery errors
- ICMP informs the sender that the **port is unreachable**

ICMP is designed to report errors for protocols such as **UDP and TCP**.

---

## 🧠 Summary
- Port Scanning identifies open ports and running services
- TCP Scanning:
  - `SYN / ACK` → Open
  - `RST` → Closed
- UDP Scanning:
  - `ICMP Port Unreachable` → Closed
  - No response → Open or Filtered
- Nmap is a powerful port scanning tool
- Always follow the **Least Privilege** principle


