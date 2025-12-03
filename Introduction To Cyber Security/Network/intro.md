# 🌐 Networking Basics

**What is a Network?**  
A **network** is a group of devices (computers, servers, phones, printers, etc.) connected together via cables or Wi-Fi to **share data and resources**.  

**Why Networks Exist:**
- To share files and information between devices  
- To connect to the Internet  
- To use shared resources like printers or servers  
- To enable communication between devices within a LAN or across WAN

**Example:**  
In a home, your laptop, phone, smart TV, and router are all connected to a network.  
On a larger scale, the **Internet** is the biggest network in the world, connecting millions of smaller networks.

---

## 1️⃣ LAN vs WAN

### 🏠 Local Area Network (LAN)
A **LAN** is a network confined to a small geographic area (home, office, building).  

**Key Points:**
- Can be divided into smaller networks called **subnets** for easier management and efficiency.  
- Multiple subnets connected form a larger LAN.  

**Example:**  
A company has three departments: IT, HR, Accounting.  
- Each department → **subnet**  
- All three subnets connected → **company LAN**

---

### 🌍 Wide Area Network (WAN)
A **WAN** covers a large geographic area (city, state, country).  

**Key Points:**
- Connects multiple LANs at different locations.  
- Often used by companies to link offices in different cities.  

**Example:**  
Company offices in Cairo, Alexandria, and Mansoura → WAN connects all LANs.

**Comparison Table:**

| Feature | LAN | WAN |
|---------|-----|-----|
| Area Covered | Small (office/home) | Large (city/state/country) |
| Speed | High | Lower due to distance |
| Ownership | Private | Usually ISP or company-managed |
| Components | Switches, sometimes routers | Routers connecting LANs |
| Example | Office network | Multi-branch corporate network |

---

## 2️⃣ Routers vs Switches

### 🔹 Switch
- Connects devices **within the same network (LAN)**  
- Layer: **Layer 2 (Data Link)**  
- Uses: **MAC addresses**  
- Forwards traffic based on **destination MAC address**  

**Example:**  
PC1 → Switch → PC3  
- Switch sends data **only to PC3**, not all devices.

---

### 🔹 Router
- Connects **different networks** together  
- Layer: **Layer 3 (Network)**  
- Uses: **IP addresses**  
- Routes traffic to the correct network

**Example:**  
Home LAN → Router → Internet  
- Router directs traffic to correct IP outside LAN.

**Comparison Table:**

| Feature | Switch | Router |
|---------|--------|--------|
| Layer | 2 (Data Link) | 3 (Network) |
| Uses | MAC addresses | IP addresses |
| Connects | Devices within LAN | Networks together |
| Internet Access | No | Yes |
| Speed | Fast (LAN) | Slightly slower due to routing |

---

## 3️⃣ ARP Protocol (Address Resolution Protocol)

**Purpose:** Map **IP address → MAC address** in a LAN.  

**How it works:**
1. Sys2 wants to send data to Gateway (IP: 192.168.1.1)  
2. Sends **ARP Request** (broadcast):  
   - "Who has IP 192.168.1.1? Tell me your MAC."  
3. Gateway responds with **MAC address**  
4. Sys2 stores it in **ARP Cache** (RAM) for later use  
5. After cache expires, ARP request repeats  

**Key Points:**
- Operates between **Layer 2 and Layer 3**  
- Efficient delivery of packets within LAN  
- Duration of ARP Cache depends on OS

---

## 4️⃣ Packets

**Definition:** Data moves across networks inside **packets**.  

### 🟢 Parts of a Packet
1. **Header:** Metadata (source, destination, type, sequence)  
2. **Payload:** Actual data being sent

**Example:**  
Sending a large file → split into thousands of packets.  
- Each packet travels independently  
- Reassembled at destination

**Visual Representation:**
Packet:
+-----------------------------+
| Header: Source, Dest, Type |
+-----------------------------+
| Payload: Actual data |
+-----------------------------+
