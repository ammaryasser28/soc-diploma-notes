# Traceroute / Tracert (Windows)

**Traceroute** (or `tracert` on Windows) is a network utility used to discover the **actual path that data packets take between two systems** on a network or the Internet. It shows each **router or hop** the packet passes through before reaching the destination.

---

## How It Works
Traceroute works by **manipulating the TTL (Time-To-Live) field in the IP header**.

- **TTL** is a value in the IP packet header that limits the number of hops a packet can traverse.
- Each router the packet passes through **decrements TTL by 1**.
- If TTL reaches 0 or 1 at a router, the router:
  1. Discards the packet.
  2. Sends an ICMP **"Time-To-Live Exceeded"** message back to the sender.

---

## Step-by-Step Process
1. Your computer sends a packet with **TTL = 1**.
   - It reaches your **Default Gateway** (first router).
   - Since TTL = 1, the router discards the packet and sends back a **TTL Exceeded** message.
   - Your computer records the first hop's IP and response time.
2. Your computer then sends a packet with **TTL = 2**.
   - The first router decrements TTL to 1.
   - The second router receives it with TTL = 1 → discards and sends a **TTL Exceeded** message.
   - Your computer records the second hop's IP and response time.
3. The process repeats, incrementing TTL (3, 4, 5…) until the packet reaches the destination.
4. The result is a **list of all hops and response times** to the destination host.

---

## Example Command
```bash
tracert google.com
```
Typical output includes:
- Hop number: The sequence of each router between you and the destination.
- IP address: Address of each router.
- Response time: Time taken to reach each hop (in milliseconds).
- Number of attempts: Usually three measurements per hop.

--- 

## Use Cases
- Discover Packet Route: See the actual path packets take to reach a server.
- Network Troubleshooting: Identify which hop is slow or causing packet loss.
- Measure Latency per Hop: Helps pinpoint slow parts of a network.
- Network Analysis: Understand how subnets and routers connect across the Internet.

---

## Important Notes
- Some networks or devices may block ICMP TTL Exceeded messages → results may show * instead of IP addresses.
- Traceroute uses ICMP or UDP depending on the operating system.
- On Windows, the command is tracert; on Linux/macOS, it is traceroute.

--- 

## Visual Diagram (Traceroute Process)
```
Your Device                  Router 1                  Router 2                  ...                  Destination
   |                             |                         |                                     |
   | -- TTL=1 Packet ----------> |                         |                                     |
   | <--- TTL Exceeded --------- |                         |                                     |
   |                             |                         |                                     |
   | -- TTL=2 Packet ----------------> |                     |                                     |
   | <--- TTL Exceeded ----------------- |                   |                                     |
   |                             |                         |                                     |
   | -- TTL=3 Packet ----------------------> |               |                                     |
   | <--- TTL Exceeded ----------------------- |             |                                     |
   |                             |                         |                                     |
   | -- Packet reaches Destination ----------------------------------------> |
```
