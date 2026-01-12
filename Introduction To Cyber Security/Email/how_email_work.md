# How Email Works – SMTP, DNS (MX), and POP3

## Introduction
This repository explains **how email works behind the scenes**, from the moment a user clicks **Send** until the recipient reads the message.  
It focuses on the role of **Mail Servers**, **SMTP**, **DNS MX records**, and **POP3** using a clear and simple scenario.

---

## Scenario
- **Sender:** Ahmed  
  Email: `Ahmed@company.com`

- **Recipient:** Aya  
  Email: `Aya@organization.com`

Ahmed wants to send an email to Aya.

---

## Email Flow Explained

### 1. Sending the Email
When Ahmed clicks **Send**, his computer does **not** send the email directly to Aya.  
Instead, it sends the email to the **Company Mail Server**.

Mail servers act like postmen — they are responsible for delivering emails.

---

### 2. Connection to Company Mail Server
Ahmed’s computer:
- Knows the IP address of the Company mail server
- Connects using:
  - **Protocol:** SMTP (Simple Mail Transfer Protocol)
  - **Port:** TCP 25

The email is transferred from Ahmed’s PC to the Company mail server.

---

### 3. Recipient Address Analysis
The Company mail server checks the recipient address:
`Aya@organization.com`

Since the email domain is different, the server must locate the destination mail server.

---

### 4. DNS MX Record Lookup
The Company mail server sends a DNS request asking for the **MX (Mail Exchange) record** of `organization.com`.

**Important:**
- MX records return the **mail server IP**, not the website IP.

---

### 5. Email Transfer Between Mail Servers
After resolving the MX record:
- Company mail server connects to Organization mail server
- Uses:
  - **Protocol:** SMTP
  - **Port:** TCP 25
- The email is successfully transferred

---

### 6. Email Storage
The Organization mail server:
- Receives the email
- Stores it in Aya’s mailbox
- Keeps it until Aya opens her email client

---

### 7. Retrieving the Email
Aya opens her email client (e.g., Outlook).

The client:
- Connects to the mail server
- Uses:
  - **Protocol:** POP3 (Post Office Protocol v3)
  - **Port:** TCP 110
- Downloads the email to Aya’s device

---

## Protocols and Ports Summary

| Purpose            | Protocol | Port |
|--------------------|----------|------|
| Send Email         | SMTP     | TCP 25 |
| Receive Email      | POP3     | TCP 110 |
| Mail Server Lookup | DNS (MX) | 53 |

---

## Key Concepts
- Emails are delivered **via mail servers**, not directly between users
- DNS MX records are essential for email routing
- SMTP handles sending, POP3 handles receiving

---

## Real-Life Analogy

| Real World        | Email System |
|------------------|--------------|
| Sender           | Ahmed |
| Post Office      | Mail Server |
| Address Directory| DNS |
| Mail Delivery    | SMTP |
| Mail Pickup      | POP3 |

---

## Conclusion
Email communication relies on standardized protocols and mail servers to ensure reliable and scalable message delivery across the internet.
