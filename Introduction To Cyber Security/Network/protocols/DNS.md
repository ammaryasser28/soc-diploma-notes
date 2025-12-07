# 🌐 DNS (Domain Name System)

DNS (Domain Name System) is a hierarchical and distributed naming system that translates human-readable domain names into IP addresses, allowing computers to locate and communicate with servers on the internet. Without DNS, users would need to remember numerical IP addresses for every website, which is impractical.

---

## 1️⃣ How DNS Works

When a user types a website address into a browser, DNS ensures the request reaches the correct server. The process involves several steps:

1. **User Input**

   * Example: `www.geeksforgeeks.org`

2. **Local Cache Check**

   * The browser checks its local cache for a recently resolved IP.
   * ✅ If found: Uses IP directly.
   * ❌ If not found: Moves to the DNS resolver.

3. **DNS Resolver Query**

   * Sends a request to a DNS resolver (provided by ISP or configured manually).

4. **Root DNS Server**

   * Resolver queries a root server.
   * Root server directs it to the correct TLD server based on the domain extension (e.g., `.org`).

5. **TLD Server**

   * Points resolver to the authoritative DNS server for the domain.

6. **Authoritative DNS Server**

   * Contains actual DNS records, including IP address.
   * Sends IP back to the resolver.

7. **Final Response**

   * Resolver returns IP to computer.
   * Browser connects to website server and loads the page.

**Local vs Network Steps:**

* **Local:** Cache check, host file lookup.
* **Network:** Resolver, root server, TLD server, authoritative server.

---

## 2️⃣ DNS Hierarchy

* **Root DNS Servers**: Top-level servers knowing where TLD servers are.
* **TLD Servers**: Manage domain extensions like `.com`, `.org`, `.net`.
* **Authoritative DNS Servers**: Store actual DNS records and provide IP addresses.
* 
<img width="773" height="376" alt="image" src="https://github.com/user-attachments/assets/0dd87543-14e7-4d11-9b68-583ac76f3261" />

---

## 3️⃣ Types of Domains

1. **Generic Domains**: `.com`, `.org`, `.net`, `.edu`
2. **Country Code Domains**: `.in` (India), `.us` (USA), `.uk` (UK), `.jp` (Japan)
3. **Inverse Domains**: Reverse DNS lookups (IP → domain) for diagnostics and security.

<img width="773" height="376" alt="image" src="https://github.com/user-attachments/assets/7f2287ee-8917-4b82-98da-aa911c29900c" />

---

## 4️⃣ Types of DNS Queries

* **Recursive Query**: Resolver queries multiple servers until final answer is found.
* **Iterative Query**: Resolver asks servers for the best answer available.
* **Non-Recursive Query**: Resolver queries a server with record in its cache.

<img width="777" height="377" alt="image" src="https://github.com/user-attachments/assets/be5d7235-1793-4728-a6ef-93f2270f0db3" />

---

## 5️⃣ DNS Caching & TTL

* **DNS Caching**: Stores resolved records locally to reduce repeated queries.
* **TTL (Time-to-Live)**: Duration a record stays in cache before expiration.

  * Example: TTL = 3600 seconds → cached for 1 hour.

---

## 6️⃣ DNS Security (DNSSEC)

* **Threats**: Vulnerable to cache poisoning and redirects.
* **DNSSEC**: Adds cryptographic signatures to verify authenticity and integrity.

---

## 7️⃣ Reverse DNS Lookup

* Maps IP address back to domain name.
* Uses:

  * Network diagnostics
  * Email security (verifying sources)

---

## 8️⃣ Common DNS Record Types

| Record    | Description                                         |
| --------- | --------------------------------------------------- |
| **A**     | Maps domain to IPv4 address                         |
| **CNAME** | Alias of another domain                             |
| **MX**    | Specifies mail servers for the domain               |
| **TXT**   | Stores text info, used for verification (SPF, DKIM) |

---

## 9️⃣ Public DNS Servers

| Provider   | IPv4                            |
| ---------- | ------------------------------- |
| Cloudflare | 1.1.1.1 & 1.0.0.1               |
| Google DNS | 8.8.8.8 & 8.8.4.4               |
| OpenDNS    | 208.67.222.222 & 208.67.220.220 |

---

## 🔟 Summary

DNS is essential for:

* Translating domain names to IP addresses
* Hierarchical server system (Root → TLD → Authoritative)
* Faster access with caching & TTL
* Enhanced security with DNSSEC
* Reverse lookups and versatile query types
