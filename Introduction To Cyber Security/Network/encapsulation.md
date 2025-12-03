# 🌐 Encapsulation in Networking

## 🔹 What is Encapsulation?

**Encapsulation** literally means "wrapping".  
In networking, it is the process of **wrapping data with protocol information before sending it across a network**.  

Each layer in the **OSI** or **TCP/IP** model adds its own **Header** (and sometimes Trailer) to the data from the layer above.

**Analogy:**  
- 📄 The message itself → Data  
- ✉️ Address on the envelope → Header  
- 🔒 Postage stamp or seal → Trailer  

---

## 🔹 How Encapsulation Works

### Step-by-Step Example: Sending an Email

1. **📨 Application Layer**  
   - Converts the message into digital data.

2. **🔗 Transport Layer**  
   - Adds a **TCP/UDP header** containing:  
     - Source Port (where it came from)  
     - Destination Port (where it is going)  

3. **🌍 Network Layer**  
   - Adds an **IP header** containing:  
     - Source IP (sender address)  
     - Destination IP (receiver address)  

4. **💻 Data Link Layer**  
   - Adds a **MAC address header** (and sometimes a trailer) to identify devices on the local network.

5. **⚡ Physical Layer**  
   - Sends data as electrical or optical signals through the medium (cable or air).

---

## 🔹 De-Encapsulation (Receiver Side)

When the data reaches the destination, it moves **up the layers**:

1. **Data Link Layer:** Removes MAC header  
2. **Network Layer:** Removes IP header and caches the source IP  
3. **Transport Layer:** Removes TCP/UDP header and caches the source port  
4. **Application Layer:** Reads the actual message  

> ✅ Each layer wraps the data at the sender side and unwraps it at the receiver.

---

## 🔹 Key Points

- **Purpose of Encapsulation:**  
  - Ensures data is **properly formatted, addressed, transmitted, and received**.  
  - Guarantees delivery to the **correct program or device**.  
  - Ensures the **message is correctly understood** by the receiver.

- **IP Spoofing:**  
  - Incoming packets can claim to be from any IP.  
  - Your system responds to the IP in the header, **even if it’s fake**.

- **Immutable Process:**  
  - Encapsulation is built into TCP/IP and **cannot be changed**.  
  - Every packet always contains headers from all layers.

---

## 🔹 Summary Diagram

```text
Sender Side:
Application Data
      ↓
Transport Header (TCP/UDP)
      ↓
Network Header (IP)
      ↓
Data Link Header/Trailer (MAC)
      ↓
Physical Layer (Bits)
      ↓
Receiver Side (De-encapsulation)
```
