## 📌 What is DHCP?

DHCP (Dynamic Host Configuration Protocol) is a network protocol used to automatically assign:

* **IP Address**
* **Subnet Mask**
* **Default Gateway**
* **DNS Servers**
* Other optional network parameters

Instead of manually configuring every device, DHCP automates this process and reduces configuration errors.

DHCP works over **UDP**, using:

* **Port 67** → Server
* **Port 68** → Client

---

## 📝 Why Do We Need DHCP?

* Manual IP assignment is possible for a few devices, but impossible for hundreds or thousands.
* DHCP offers **centralized control**, **fewer errors**, and **automatic address reuse**.
* Useful in dynamic environments like **campuses**, **offices**, and **public Wi-Fi networks**.

---

## 📦 Static vs Dynamic IP Assignment

### **Static Assignment**

You manually configure the IP on the device.

### **Dynamic Assignment (DHCP)**

The server automatically assigns an IP and other network info.

Servers are usually **static**.
Clients are usually **dynamic**.

---

## 🧩 How DHCP Works — The 4-Step Process

The DHCP process is known as **DORA**:

### 1️⃣ DHCP Discover (Client → Broadcast → Port 67)

Client broadcasts a request asking: *Is there any DHCP server available?*

### 2️⃣ DHCP Offer (Server → Broadcast/Unicast → Port 68)

DHCP server replies with an offer that includes:

* Proposed IP
* Lease Time
* Subnet Mask
* Gateway
* DNS

### 3️⃣ DHCP Request (Client → Broadcast → Port 67)

Client requests the offered configuration from a specific server.

### 4️⃣ DHCP ACK (Server → Broadcast/Unicast → Port 68)

Server confirms assignment.
Client applies the settings and joins the network.

---

## ⏳ Lease Time & Renewal

A **lease** is how long the client can keep the assigned IP.

Renewal happens in phases:

* **T1 (50%)** → Client tries to renew with the original server.
* **T2 (87.5%)** → Client broadcasts renewal if the server is unreachable.
* If lease expires → Client restarts the process with **DHCP Discover**.

---

## 🧱 DHCP Options (Common Ones)

DHCP messages contain optional fields called **Options**:

* **Option 1** → Subnet Mask
* **Option 3** → Gateway
* **Option 6** → DNS Servers
* **Option 12** → Hostname
* **Option 15** → Domain Name
* **Option 50** → Requested IP
* **Option 51** → Lease Time
* **Option 53** → DHCP Message Type
* **Option 54** → Server Identifier

---

## 🌐 DHCP Relay (IP Helper)

Broadcasts do *not* cross routers.
So networks use a **DHCP Relay Agent**:

* Forwards client DHCP broadcasts to a remote DHCP server.
* Adds the **GIADDR** field so the server knows which network the request came from.

---

## 🔐 DHCP Security

Common protections:

* **DHCP Snooping** → Prevents rogue DHCP servers.
* **Rate Limiting** → Protects from DHCP starvation attacks.
* **Proper VLAN segmentation**.

---

## 🛠 Common Issues

| Problem                     | Explanation                          |
| --------------------------- | ------------------------------------ |
| Client receives 169.254.x.x | No DHCP server response (APIPA)      |
| Duplicate IPs               | Overlapping static + dynamic entries |
| Internet not working        | Wrong gateway or DNS in DHCP config  |
| Slow network join           | Relay or broadcast issues            |

---

## 🧪 Packet Capture Tips (Wireshark)

Useful filters:

```
dhcp
bootp
```

Check fields:

* `yiaddr` (Your IP Address)
* `GIADDR`
* `Option 53` for message type

---

## 🧭 Summary

* DHCP automates IP assignment.
* Works with UDP on ports 67/68.
* Follows **Discover → Offer → Request → ACK**.
* Supports additional options like gateway, DNS, etc.
* Uses lease timers (T1 & T2).
* May require a Relay Agent across subnets.
* Security features like DHCP Snooping help protect networks.


