# DNS Cache Poisoning

## Overview
**DNS Cache Poisoning** (also known as **DNS Spoofing**) is an attack in which an attacker tricks a DNS resolver into storing a **fake IP address** for a legitimate domain name.  
As a result, users are redirected to a malicious website without their knowledge.

---

## How DNS Works (Normal Behavior)
1. A user enters a domain name (e.g., `google.com`).
2. The user’s device sends a request to a **DNS Resolver**.
3. The resolver queries a **DNS Server**.
4. The DNS server responds with the correct IP address.  
   Example:
`google.com → 8.8.8.8`
5. The resolver caches the response and the user is directed to the legitimate website.

---

## The Vulnerability
DNS resolvers cache responses to:
- Improve performance
- Reduce network traffic

If an attacker manages to inject a **malicious DNS record** into this cache, all subsequent users are affected until the cache expires.

---

## How the DNS Cache Poisoning Attack Works
1. The attacker exploits a vulnerability in a **DNS Server or Resolver**.
2. The attacker injects a **forged DNS response** into the cache.
3. The legitimate DNS record:
`google.com → 8.8.8.8`
is replaced with a malicious one:
`google.com → 5.5.5.5`
4. The malicious IP address hosts a fake or malicious website.
5. When users request `google.com`, they are redirected to the attacker’s site.

---

## Impact on Users
- Redirection to phishing websites
- Credential theft (usernames and passwords)
- Malware distribution
- Man-in-the-Middle attacks
- Large-scale compromise of multiple users

---

## Why This Attack Is Dangerous
- Completely transparent to the user
- Affects all users relying on the poisoned DNS cache
- Can compromise trusted and well-known domains
- Difficult to detect without proper security mechanisms

---

## Common Causes
- Misconfigured or outdated DNS servers
- Lack of DNSSEC implementation
- Predictable DNS transaction IDs
- UDP-based DNS communication without authentication

---

## Mitigation Techniques

### 1. DNSSEC (DNS Security Extensions)
- Adds cryptographic signatures to DNS records
- Allows resolvers to verify authenticity
- Prevents forged DNS responses

### 2. Randomized Source Ports and Transaction IDs
- Makes spoofing DNS responses significantly harder

### 3. Use Trusted DNS Providers
- Examples: Google DNS, Cloudflare DNS
- Regularly updated and secured infrastructure

### 4. HTTPS and Certificate Validation
- Even if DNS is poisoned, HTTPS certificates can reveal fake websites

---

## Summary
- DNS Cache Poisoning targets trust in DNS infrastructure
- Attackers inject fake IP addresses into DNS cache
- Users are redirected to malicious websites unknowingly
- DNSSEC and HTTPS are the most effective defenses


