# UDP (User Datagram Protocol)

## What is UDP?

UDP is a transport layer protocol that sends data quickly without establishing a connection. Its main goal is **speed**, not **reliability**.

<img width="586" height="264" alt="image" src="https://github.com/user-attachments/assets/77593735-e6df-4fcc-8412-2158ca6359c3" />

---

## Key Features

* **Connectionless:** No handshake like TCP.
* **Very fast:** No retransmission or waiting for acknowledgments.
* **Small header:** Only 8 bytes.
* **Ideal for applications where losing some data is acceptable.**

---

## Drawbacks

* No guarantee that packets arrive.
* No ordering of packets.
* No retransmission.
* Any reliability must be implemented by the application.

---

## Common Use Cases

* Streaming (Video/Audio)
* VoIP (Voice over IP)
* Online gaming
* DNS queries
* DHCP
* Multicast & Broadcast

---

## UDP Header Structure

The header is **8 bytes** long and consists of:

* **Source Port** (2 bytes)
* **Destination Port** (2 bytes)
* **Length** (2 bytes)
* **Checksum** (2 bytes)

<img width="768" height="387" alt="image" src="https://github.com/user-attachments/assets/819ba41c-26a1-48a1-a23b-3c6df295be40" />

---

## UDP vs TCP

| Feature        | UDP                    | TCP                           |
| -------------- | ---------------------- | ----------------------------- |
| Connection     | Connectionless         | Connection-Oriented           |
| Reliability    | None                   | Guaranteed delivery and order |
| Speed          | Faster                 | Slower                        |
| Retransmission | No                     | Yes                           |
| Typical Use    | Streaming, gaming, DNS | File transfer, web, email     |

---

## Summary

UDP is perfect when **speed** is essential and occasional data loss is acceptable. For full reliability, TCP is the better choice.


