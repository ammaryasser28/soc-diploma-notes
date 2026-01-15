# SYN Flood Attack

## Overview
The **SYN Flood Attack** is a classic **Denial of Service (DoS / DDoS)** attack that exploits a weakness in the **TCP 3-Way Handshake** mechanism.  
By abusing how servers manage half-open connections, an attacker can exhaust server resources and deny service to legitimate users.

---

## TCP 3-Way Handshake (Normal Operation)
A normal TCP connection is established using three steps:

1. **Client → Server : SYN**  
   The client requests to start a connection.

2. **Server → Client : SYN/ACK**  
   The server acknowledges the request and reserves resources.

3. **Client → Server : ACK**  
   The client confirms, and the connection becomes fully established.

Once completed, data transfer can begin.

---

## The Vulnerability
When a server receives a **SYN** packet:
- It allocates memory for the connection.
- It stores session information.
- It waits for the final **ACK** (typically up to 30 seconds).

This design allows parallel connections but introduces a vulnerability.

---

## How the SYN Flood Attack Works
The attacker exploits this behavior as follows:

1. Sends a massive number of **SYN packets**.
2. Never completes the 3-way handshake.
3. For each SYN packet:
   - The server allocates memory.
   - The server waits for an ACK that never arrives.
4. The server’s connection table becomes full.
5. Legitimate users are denied access.

This results in a **Denial of Service**.

---

## Botnets and Scale of the Attack
The attacker does **not** need one device per connection.

Instead:
- The attacker controls a **botnet** (zombie machines).
- Each zombie sends thousands or millions of SYN packets.
- The attack scales by packet rate, not number of devices.

---

## IP Spoofing
Each SYN packet contains a **spoofed (fake) source IP address**:

- The IP address is unassigned or unused.
- The victim server replies with **SYN/ACK**.
- No host receives the response.
- The final **ACK** is never sent.
- The connection remains half-open until timeout.

This makes the attack difficult to trace and highly effective.

---

## Impact on the Server
- Memory exhaustion
- Connection table overflow
- Increased CPU usage
- Legitimate connections dropped
- Service unavailability

---

## Mitigation Techniques

### 1. Reduce SYN Timeout
- Reduces the waiting time for half-open connections.
- Limited effectiveness against strong attacks.

### 2. SYN Cookies
- The server does not allocate memory until the handshake is completed.
- One of the most effective defenses.

### 3. Firewall and Proxy-Based Protection
- Firewalls proxy the TCP handshake.
- Only fully established connections reach the server.

### 4. IDS / IPS and Load Balancers
- Detect abnormal SYN rates.
- Filter or rate-limit malicious traffic.

---

## Summary
- SYN Flood exploits TCP’s stateful connection handling.
- Attackers send spoofed SYN packets at high rates.
- The server waits for ACKs that never arrive.
- Resources are exhausted, causing a denial of service.

---

## References
- RFC 793 – Transmission Control Protocol  
- RFC 4987 – TCP SYN Flooding Attacks and Common Mitigations  
- OWASP – Denial of Service Attacks


