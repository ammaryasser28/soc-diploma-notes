# ARP Cache Poisoning (ARP Spoofing)

## Overview
ARP Cache Poisoning is a network attack that exploits the trust-based nature of the Address Resolution Protocol (ARP). By abusing how devices update their ARP cache, an attacker can impersonate other devices on the network—most dangerously, the default gateway—and place themselves in a Man-in-the-Middle (MITM) position.

---

## What Is ARP Cache?
- The **ARP Cache** is a local table stored on each device.
- It maps **IP addresses** to **MAC addresses**.
- It can be viewed using the command:
```bash
arp -a
```

---


## Normal ARP Communication Flow

### Scenario
- **Device A** wants to communicate with **Device B**
- **Device B IP Address:** `192.168.1.5`

### Steps
1. Device A sends an **ARP Request**:
Who has `192.168.1.5 ?`

2. The request is sent as a **broadcast**:
- Destination MAC: `FF:FF:FF:FF:FF:FF`

3. Device B responds with an **ARP Reply**:
`192.168.1.5` is at `BB:BB:BB:BB:BB:BB`

4. Both devices update their **ARP Cache**.
5. Communication continues normally using **MAC addresses**.

---

## Unsolicited ARP

### Definition
An **Unsolicited ARP** is an ARP reply sent **without a prior ARP request**.

### Legitimate Uses
- Updating ARP tables
- Announcing new IP-to-MAC mappings
- Notifying devices of a MAC address change

### Example
When a router boots up, it may broadcast:
`192.168.1.1` is at `AA:BB:CC:DD:EE:FF`


- Devices update their ARP cache automatically.
- ARP has **no authentication mechanism**, so devices trust these messages by default.

---

## How ARP Cache Poisoning Works

### Attack Concept
- An attacker abuses **Unsolicited ARP** to impersonate another device.
- The most dangerous target is the **default gateway**.

### Attack Steps
1. The attacker sends forged ARP replies:
`192.168.1.1` is at Attacker_MAC
2. All devices on the network update their ARP cache.
3. The legitimate gateway MAC address is replaced.
4. The ARP cache is now **poisoned**.

---

## Traffic Interception

- Victims send all outbound traffic to the attacker.
- Destination MAC address is set to the attacker’s MAC.
- The attacker receives all traffic intended for the gateway.

---

## Man-in-the-Middle (MITM) Attack

- The attacker runs a tool such as **Ettercap**.

### The tool performs the following:
- Receives the victim’s traffic
- Reads or modifies the data
- Rewrites the destination MAC to the real gateway
- Forwards the traffic to the gateway

### Response Flow
- Responses from the gateway return to the attacker.
- The attacker rewrites the MAC again.
- Traffic is forwarded to the victim.

> Both sides believe they are communicating directly.

---

## Why ARP Cache Poisoning Is Dangerous

- Does not require system exploitation
- Relies on protocol design flaws
- Enables:
- Traffic sniffing
- Credential theft
- Session hijacking
- DNS spoofing
- Forms the foundation for many advanced network attacks

---

## Key Takeaways

- ARP is inherently insecure and trust-based
- Unsolicited ARP is both useful and dangerous
- ARP Cache Poisoning allows attackers to impersonate the default gateway
- Successful attacks result in a full **Man-in-the-Middle** position

---

## Conclusion
ARP Cache Poisoning highlights the importance of understanding normal network behavior. By exploiting the lack of authentication in ARP, attackers can silently intercept and manipulate network traffic, making this one of the most critical attacks in local networks.
