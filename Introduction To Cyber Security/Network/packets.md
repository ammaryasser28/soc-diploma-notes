# 📦 Understanding Network Packets

Data on a network **does not travel all at once**. Instead, it moves in small pieces called **Packets (حزم بيانات)**.  
Think of it as breaking a large message into tiny envelopes, each carrying a part of the content.

---

## 🔹 What is a Packet?

A **packet** is a small unit of data sent over a network.  
Instead of sending a whole file or message at once, networks split it into multiple packets to improve speed and reliability.

> Example:
> Sending an email or a file might require **hundreds, thousands, or even millions of packets**.

---

## 🔹 Components of a Packet

A packet has **two main parts**:

### 1️⃣ Header (رأس الحزمة)
The header contains **information about the packet itself**, such as:

- **Source:** Where the packet came from (e.g., IP address)
- **Destination:** Where the packet is going
- **Type of Data:** Text, image, video, etc.

> Think of the header like the **address on an envelope** — it tells the network where the packet should go.

---

### 2️⃣ Payload (المحتوى)
The payload is **the actual data carried by the packet**.  

- For example, in an email split into packets:
  - Header = sender & receiver info
  - Payload = the email text or attachment

> Analogy: If the packet is an envelope, the payload is **what’s inside the envelope**.

---

## 🔹 How Packets Travel

- Large files/messages are **split into multiple packets**.
- Each packet **travels independently** through the network.
- Packets can **arrive out of order**.
- At the destination, packets are **reassembled** into the original message/file.

---

## 🔹 Summary

| Component | Description |
|-----------|-------------|
| **Header** | Contains information about the packet (source, destination, type) |
| **Payload** | Contains the actual data being sent |
| **Packet** | Header + Payload |

**Key idea:** Everything on a network moves as **small packets**, not large chunks.

---

## 🔹 Packet Structure

<img width="704" height="273" alt="image" src="https://github.com/user-attachments/assets/97acb9da-fb1b-42c7-afa3-2f08589969fc" />
