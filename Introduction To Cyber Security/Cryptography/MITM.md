# 🕵️‍♂️ Man-In-The-Middle (MITM) Attack in Cryptography

This README explains the **Man-In-The-Middle (MITM) attack**, how it works in asymmetric cryptography, why it is dangerous, and how **Digital Certificates** mitigate the attack.

---

## 📌 What is a Man-In-The-Middle (MITM) Attack?

A **Man-In-The-Middle attack** occurs when an attacker secretly positions themselves between two communicating parties (e.g., Alice and Bob) and intercepts or modifies the communication without either party realizing it.

The attacker can:
- Read sensitive data
- Modify messages
- Impersonate one or both parties

---

## 🔐 Normal Secure Communication (Without Attack)

1. **Bob** wants to communicate with **Alice**
2. Bob sends his **Public Key** to Alice
3. Alice encrypts messages using Bob’s public key
4. Bob decrypts messages using his **Private Key**

✔️ Communication remains secure

---

## 🚨 MITM Attack Scenario (Public Key Substitution)

### Step 1: Intercepting Bob’s Public Key
- Bob sends his public key to Alice
- The attacker intercepts the packet

### Step 2: Replacing the Key
- The attacker replaces Bob’s real public key with a **fake public key**
- The fake key is sent to Alice

### Step 3: Repeating the Attack in Reverse
- Alice sends her public key to Bob
- The attacker intercepts and replaces it with another fake public key

---

## ❌ Result of the Attack

- Alice believes she has Bob’s real public key
- Bob believes he has Alice’s real public key
- In reality:
  - Both are encrypting messages using **fake public keys**
  - The attacker decrypts messages using the **corresponding fake private keys**
  - The attacker can read, modify, and re-encrypt messages before forwarding them

⚠️ Neither Alice nor Bob is aware of the attack

---

## 🔥 Why MITM is Dangerous

- Breaks **Confidentiality**
- Breaks **Integrity**
- Allows silent eavesdropping and message manipulation
- Encryption alone is **not enough** without identity verification

---

## 🛡️ Mitigation: Digital Certificates

### How Digital Certificates Prevent MITM Attacks

- Instead of sending only a public key, parties send a **Digital Certificate**
- A Digital Certificate:
  - Contains the public key
  - Is signed by a trusted **Certificate Authority (CA)**

### Verification Process
1. The receiver verifies the **CA’s digital signature**
2. Confirms the public key belongs to the real entity
3. If the key is modified, the signature becomes invalid

✔️ Fake public keys are detected immediately

---

## 🌐 Real-World Example

- HTTPS websites use **SSL/TLS certificates**
- Browsers verify certificates before establishing secure connections
- If a certificate is fake or altered:
  - The browser displays a security warning 🚨

---

## 🧠 Key Takeaways

- MITM attacks exploit unauthenticated public key exchange
- Attackers replace real public keys with fake ones
- Victims unknowingly encrypt data for the attacker
- **Digital Certificates + Trusted CAs** are essential to prevent MITM attacks
- Secure communication requires:
  - Encryption ✅
  - Authentication ✅

