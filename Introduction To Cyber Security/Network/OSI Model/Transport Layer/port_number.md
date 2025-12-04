## 📌 What Are Network Ports?

Network ports are **logical identifiers** used at **Layer 4 (Transport Layer)** to differentiate between multiple sessions and applications running on the same computer.

They allow the operating system to know:

* أي تطبيق يستقبل البيانات
* أي جلسة مرتبطة بأي اتصال

> **Ports exist in Layer 4 inside TCP/UDP headers.**

---

## 📌 Where Do Ports Exist?

Ports are included in the **TCP Header** or **UDP Header**:

* **Source Port**
* **Destination Port**

These are 16-bit numbers → range **0 to 65535**.

```
+-----------------------------+
|   Layer 7: Application      |
+-----------------------------+
|   Layer 6: Presentation     |
+-----------------------------+
|   Layer 5: Session          |
+-----------------------------+
|   Layer 4: Transport        |  <-- Here (TCP/UDP) ports exist
+-----------------------------+
|   Layer 3: Network          |
+-----------------------------+
|   Layer 2: Data Link        |
+-----------------------------+
|   Layer 1: Physical         |
+-----------------------------+
```

---

# 🔥 Complete Port Number Classification

Port numbers are divided into **four main ranges**.

## 0 — Reserved

* محجوز للاستخدامات الداخلية الخاصة بالنظام.
* لا يُستخدم كبورت خدمة.

---

## 0–1023 — Well-Known Ports

* Ports assigned to standard services.
* Managed by **IANA**.
* Examples:

  * 21 → FTP
  * 22 → SSH
  * 25 → SMTP
  * 53 → DNS
  * 80 → HTTP
  * 443 → HTTPS

### Notes:

* لا تستخدم هذه البورتات لتطبيقات مخصصة.
* فتح بورت أقل من 1024 يتطلب صلاحيات root على Linux.

---

## 1024–49151 — Registered Ports

Used by well-known applications but less restricted.

Examples:

* 3306 → MySQL
* 3389 → RDP
* 5432 → PostgreSQL

### Notes:

* يمكن استخدامها، لكن يُفضل عدم إعادة استخدامها لخدمة مختلفة لتجنب التعارض.

---

## 49152–65535 — Dynamic / Ephemeral Ports

* Ports selected automatically by clients.
* Used as **source ports** when your device initiates a connection.

### Example:

When you visit Google:

* Client source port: **49155** (ephemeral)
* Destination port: **443** (HTTPS)

Server response:

* Source: 443
* Destination: 49155

---

# ⚙️ How Ports Work in TCP/UDP

Every packet contains:

* **Source Port** (port of CLIENT)
* **Destination Port** (port of SERVER)

### TCP (Connection-oriented)

* Uses 3-way handshake
* Requires listening socket on server
* Tracks sessions using source/destination IP + port

### UDP (Connectionless)

* No handshake
* Still uses ports to define which application receives data

---

# 📌 Common Ports Cheat Sheet

| Port  | Service    | Protocol |
| ----- | ---------- | -------- |
| 20/21 | FTP        | TCP      |
| 22    | SSH        | TCP      |
| 23    | Telnet     | TCP      |
| 25    | SMTP       | TCP      |
| 53    | DNS        | TCP/UDP  |
| 80    | HTTP       | TCP      |
| 110   | POP3       | TCP      |
| 143   | IMAP       | TCP      |
| 443   | HTTPS      | TCP      |
| 3306  | MySQL      | TCP      |
| 3389  | RDP        | TCP      |
| 5432  | PostgreSQL | TCP      |

---

# 🔍 How to View Open Ports

## Linux

```
ss -tuln
netstat -tuln
lsof -i :443
ss -tunap
```

## Windows

```
netstat -ano
```

---

# 🔐 Security Best Practices

* افتح فقط البورتات الضرورية.
* تغيير البورت الافتراضي لا يعني حماية كاملة.
* استخدم جدار ناري (UFW, firewalld, Windows Firewall).
* راقب السجلات logs.
* أمن خدماتك بتشفير ومصادقة قوية.

---

# 📦 Summary Table

| Range       | Name              | Usage                      |
| ----------- | ----------------- | -------------------------- |
| 0           | Reserved          | Not used for services      |
| 1–1023      | Well-known        | Standard internet services |
| 1024–49151  | Registered        | Third‑party apps/services  |
| 49152–65535 | Dynamic/Ephemeral | Client source ports        |



