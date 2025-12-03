# 🖧 ICMP Protocol

## 📌 Overview
The **Internet Protocol (IP)** is a **best-effort protocol**, meaning:

- **Connectionless**: No prior connection is established before sending packets.
- **Unreliable**: IP does not guarantee delivery.
- **Unacknowledged**: No acknowledgment of receipt.

> IP relies on **higher OSI layers** for reliability.  
> **ICMP** provides a mechanism to report errors and issues in IP transmission.

---

## ⚙️ ICMP Protocol Function
- ICMP **does not carry user data**.
- It reports **errors and network issues** back to the sender.
- Common scenarios:
  - `Network unreachable`
  - `Host unreachable`
  - `TTL exceeded`

---

## 📝 ICMP Examples

### 1️⃣ Time-to-Live (TTL) Exceeded
```text
- Each IP packet has a TTL (Time-To-Live) field.
- TTL decreases by 1 at every router hop.
- If TTL reaches 1, the router sends back:
  "Time to live exceeded in transit"
- Prevents packets from circulating endlessly.
```
### 2️⃣ Destination Unreachable
```text
- If a router cannot forward a packet due to routing issues:
  "Destination unreachable, Network unreachable"
- If the packet reaches the correct network but the host is unreachable:
  "Destination unreachable, Host unreachable"
```
---

## ✅ Summary

- IP: Sends data without guarantee.

- ICMP: Supports IP by reporting errors during transmission.

- Essential for network troubleshooting and understanding packet delivery failures.
