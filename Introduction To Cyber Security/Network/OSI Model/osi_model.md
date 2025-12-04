# 🌐 OSI Model - Open Systems Interconnection

## 1️⃣ What is OSI Model?
The **OSI (Open Systems Interconnection) Model** is a standard framework that explains how data is transmitted between devices on a network.  
- **Purpose:** To standardize communication between different systems, ensuring each layer has a specific role.  
- The OSI Model consists of **7 layers**, each responsible for a particular part of the communication process.

<img width="877" height="431" alt="image" src="https://github.com/user-attachments/assets/3a2d6bb4-c4b7-4150-9b1c-4f29fb9cdd1b" />

---

## 2️⃣ The Seven Layers (7 Layers)

### 1. Physical Layer
- **Function:** Transmits raw bits (0s and 1s) over the physical medium (cables, radio waves, fiber optics).  
- **Responsibilities:**
  - Convert digital data into electrical, optical, or radio signals.  
  - Define transmission speed, frequency, and type of medium.  
- **Example Devices:** Hubs, Repeaters, Cables  

---

### 2. Data Link Layer
- **Function:** Transfers frames between devices on the same network and ensures error-free transmission.  
- **Responsibilities:**
  - Add MAC addresses to identify sender and receiver.  
  - Detect and correct simple errors.  
- **Example Devices:** Switches, Bridges  

---

### 3. Network Layer
- **Function:** Routes data from source to destination across different networks.  
- **Responsibilities:**
  - Assign IP addresses to devices.  
  - Choose the best path for data transmission (Routing).  
- **Example Devices:** Routers  

---

### 4. Transport Layer
- **Function:** Ensures complete and reliable delivery of data between devices.  
- **Responsibilities:**
  - Divide data into segments (TCP) or datagrams (UDP) and reassemble them.  
  - Control flow and error correction (TCP) or fast delivery without confirmation (UDP).  
- **Common Protocols:** TCP, UDP  

---

### 5. Session Layer
- **Function:** Manages sessions between applications on different devices.  
- **Responsibilities:**
  - Establish, maintain, and terminate sessions.  
  - Synchronize data if interruptions occur.  
- **Example:** FTP login session  

---

### 6. Presentation Layer
- **Function:** Converts data into a format understandable by the application layer.  
- **Responsibilities:**
  - Encryption and decryption  
  - Compression and decompression  
  - Data formatting (e.g., converting text, images, video)  
- **Example:** Converting an image file from JPEG to BMP  

---

### 7. Application Layer
- **Function:** Closest layer to the user; provides network services to applications.  
- **Responsibilities:**
  - Provide an interface for end-users to access the network.  
- **Common Protocols:**
  - HTTP/HTTPS (Web browsing)  
  - FTP (File transfer)  
  - SMTP (Email)  

---

## 3️⃣ Layer Interaction
- Each layer depends on the layer below and serves the layer above.  
- Data flows **top-down when sending** (Application → Physical) and **bottom-up when receiving** (Physical → Application).  

---

## 4️⃣ Quick Visual Summary
| Layer | Function | Protocol / Device Example |
|-------|---------|---------------------------|
| 7. Application | User interface and network services | HTTP, FTP, SMTP |
| 6. Presentation | Data formatting / encryption | JPEG, SSL |
| 5. Session | Session management | NetBIOS, RPC |
| 4. Transport | Reliable / fast data delivery | TCP, UDP |
| 3. Network | Routing and addressing | IP, Routers |
| 2. Data Link | Node-to-node delivery / MAC addressing | Switch, MAC addresses |
| 1. Physical | Transmission of raw bits | Cable, Hub, Fiber |

---

## 5️⃣ Protocols Used in OSI Layers

| Layer | Function | Protocol Data Unit (PDU) | Common Protocols |
|-------|---------|-------------------------|-----------------|
| Physical | Establish physical connections between devices | Bits | USB, SONET/SDH, etc. |
| Data Link | Node-to-node delivery of messages | Frames | Ethernet, PPP, etc. |
| Network | Transmission from one host to another across networks | Packets | IP, ICMP, IGMP, OSPF, etc. |
| Transport | Provides service from Network layer to Application layer | Segments (TCP) / Datagrams (UDP) | TCP, UDP, SCTP, etc. |
| Session | Establish, maintain, and secure connections | Data | NetBIOS, RPC, PPTP, etc. |
| Presentation | Format and manipulate data for transmission | Data | TLS/SSL, MIME, etc. |
| Application | Identify client and synchronize communication | Data | FTP, SMTP, DNS, DHCP, etc. |


