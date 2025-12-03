# IPv4 Header Explained

<img width="757" height="291" alt="image" src="https://github.com/user-attachments/assets/3c38b302-3d89-495c-b6c4-742260513d48" />

---

## Overview
- Each row in the IPv4 header represents **32 bits (4 bytes)**.  
- The minimum header size is **20 bytes**.  
- Different protocols have different headers (IPv6 is different, but some fields are common).

---

## IPv4 Header Fields

1. **Version (4 bits)**
   - Indicates the IP version.  
   - Allowed values:
     - `4` → IPv4  
     - `6` → IPv6  
   - Any other value → malformed packet, should be dropped.

2. **Internet Header Length (IHL) (4 bits)**
   - Length of the header in 32-bit words.  
   - Minimum: 5 → 5 × 4 = 20 bytes.  
   - Helps routers locate the start of the payload.

3. **Type of Service (TOS) / Differentiated Services (DS)**
   - Specifies packet priority or handling.  
   - Used for Quality of Service (QoS).

4. **Total Length (16 bits)**
   - Total packet length (Header + Data) in bytes.  
   - Maximum: 65535 bytes.

5. **Identification (16 bits)**
   - Unique ID for fragmented packets.

6. **Flags (3 bits)**
   - Control fragmentation:
     - Bit 0 → Reserved  
     - Bit 1 → Don't Fragment (DF)  
     - Bit 2 → More Fragments (MF)

7. **Fragment Offset (13 bits)**
   - Position of this fragment in the original packet.

8. **Time-To-Live (TTL) (8 bits)**
   - Maximum number of hops a packet can traverse.  
   - Decreases by 1 at each router.  
   - If TTL = 0 → packet is dropped.  
   - Max TTL = 255 → prevents packets from looping forever.

9. **Protocol (8 bits)**
   - Identifies the transport layer protocol.  
   - Examples:
     - TCP = 6  
     - UDP = 17  
     - ICMP = 1  
   - After reading the destination IP, the router uses this field to forward the packet.

10. **Header Checksum (16 bits)**
    - Verifies the integrity of the header only.

11. **Source IP Address (32 bits)**
    - The sender’s IP address (may be spoofed).

12. **Destination IP Address (32 bits)**
    - The receiver’s IP address.  
    - Located at bytes 16–20 in the header.

13. **Options (Variable)**
    - Optional field for special purposes (Security, Record Route, Timestamp).  
    - Increases header size above 20 bytes if present.

14. **Padding**
    - Ensures header size is a multiple of 32 bits.

---

### Notes
- Header size is **at least 20 bytes**, may increase if options exist.  
- Payload (actual data) comes immediately after the header.
