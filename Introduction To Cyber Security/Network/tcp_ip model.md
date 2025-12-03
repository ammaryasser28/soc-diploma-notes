## What is TCP/IP?

The **TCP/IP model** (or TCP/IP stack) is a framework used to explain how data travels across networks. It consists of **4 main layers**, each with a specific role in handling and transmitting data.

<img width="787" height="388" alt="image" src="https://github.com/user-attachments/assets/c926f5d5-afbf-4f51-8046-84a5865640c8" />

---

## 1️⃣ Link Layer (Network Access Layer)

**Function:** Defines how to access a specific network topology and connects devices.  
**Works on:** Sending data within the same local network (LAN) or directly connected networks.  
**Example Protocols/Technologies:**
- **Ethernet** – The most common LAN protocol.
- **Token Ring** – An older network technology.
- **Wi-Fi** – Wireless network access.

**Summary:** This layer handles how bits are transmitted over wires or wirelessly.

---

## 2️⃣ Internet Layer (Network Layer)

**Function:** Responsible for **routing data** between different networks.  
**Works on:** Datagrams, which include sender and receiver addresses.  
**Example Protocols:**
- **IP Version 4 (IPv4)** – Uses 32-bit addresses.  
- **IP Version 6 (IPv6)** – Uses 128-bit addresses to support more devices.  
- **ICMP (Internet Control Message Protocol)** – Used for error messages and connectivity testing (e.g., `ping`).

**Summary:** This layer decides **where the data should go** on the network.

---

## 3️⃣ Transport Layer

**Function:** Provides **end-to-end delivery** of data between applications on different devices.  
**Works on:** Segmenting data into packets for transmission through the Internet layer.  
**Example Protocols:**
- **TCP (Transmission Control Protocol)** – Reliable, ensures data arrives without loss or duplication.  
- **UDP (User Datagram Protocol)** – Faster but unreliable, used in streaming and online gaming.

**Summary:** Ensures data reaches the correct application on the destination device.

---

## 4️⃣ Application Layer

**Function:** Serves as the interface between the network and user applications.  
**Example Services/Protocols:**
- **Telnet** – Remote control of devices.  
- **FTP (File Transfer Protocol)** – File transfer between devices.  
- **DNS (Domain Name System)** – Converts domain names (e.g., google.com) to IP addresses.

**Summary:** The layer that users interact with directly through programs and network services.

---

## ⚡ Working of TCP/IP Model

<img width="641" height="317" alt="image" src="https://github.com/user-attachments/assets/8f47db8f-382b-42bf-855c-168f51469095" />

---

## ⚡ Note: TCP/IP vs OSI Model

- **OSI Model:** 7 layers – Physical, Data Link, Network, Transport, Session, Presentation, Application.  
- **TCP/IP Model:** 4 layers – Covers all OSI functions in a practical, simplified way.

