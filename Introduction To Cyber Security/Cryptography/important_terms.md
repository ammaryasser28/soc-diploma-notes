# 🔐 Cryptography – Important Terms

## 📌 Overview

Cryptography is a core pillar of information security.  
Before studying modern encryption algorithms, it is essential to understand the basic cryptographic terminology used across all security systems.

This document provides a clear, structured explanation of the most important cryptography terms.

---

## 📖 Plaintext

**Plaintext** is the original data in its readable and understandable form.

### Characteristics:
- Human-readable
- Not encrypted
- Not secure if exposed

### Example:
- Hello Cyber Security

---

## 🔒 Ciphertext

**Ciphertext** is the encrypted form of plaintext.

### Characteristics:
- Not human-readable
- Appears random or meaningless
- Can only be understood after decryption

### Example:
- Jgnnq Eadgt Ugewtkva

---

## 🔐 Encryption

**Encryption** is the process of converting plaintext into ciphertext.

### Purpose:
- Protect sensitive data
- Prevent unauthorized access

### Process Flow:
- Plaintext → Encryption → Ciphertext

---

## 🔓 Decryption

**Decryption** is the reverse process of encryption.

### Purpose:
- Restore original data
- Make encrypted data readable again

### Process Flow:
- Ciphertext → Decryption → Plaintext


---

## ⚙️ Algorithm

An **Algorithm** is the publicly known set of rules that defines how encryption and decryption work.

### Key Notes:
- Algorithms are NOT secret
- Security does not rely on hiding the algorithm
- Modern algorithms use complex mathematical operations

### Example: Caesar Cipher
- Based on shifting letters
- Very simple and weak
- Easy to break

---

## 🔑 Key

A **Key** is a secret numeric value used by the algorithm.

### Characteristics:
- Measured in bits (e.g., 128-bit, 256-bit)
- Must remain confidential
- Core element of cryptographic security

### Fundamental Rule:
- Encryption Security = Algorithm + Key

---

## 🧮 Key Space

**Key Space** refers to the total number of possible keys that can be generated.

### Why It Matters:
- Larger key space = stronger security
- Makes brute-force attacks impractical

### Example:
- A **56-bit key** produces:
- 72,057,594,037,927,936 possible keys

---

## 🧠 Cryptanalysis

**Cryptanalysis** is the science of breaking encryption systems.

### Objective:
- Recover plaintext without knowing the key

### Common Techniques:
- Brute-force attacks
- Statistical analysis
- Pattern recognition

Used by:
- Attackers
- Security researchers
- Penetration testers

---

## 🕵️‍♂️ Historical Fun Fact – Steganography

Before modern cryptography, people hid information using creative techniques.

### Example:
- A slave’s head was shaved
- A message was tattooed on the scalp
- Hair was allowed to grow back
- The slave was sent to the destination
- Hair was shaved again to reveal the message

This technique is called **Steganography**, which focuses on hiding information rather than encrypting it.

---

## 📝 Summary Table

| Term | Description |
|----|------------|
| Plaintext | Original readable data |
| Ciphertext | Encrypted unreadable data |
| Encryption | Converts plaintext to ciphertext |
| Decryption | Restores ciphertext to plaintext |
| Algorithm | Public encryption method |
| Key | Secret value used in encryption |
| Key Space | Total number of possible keys |
| Cryptanalysis | Breaking encryption |

---

## ✅ Key Takeaways

- Cryptography protects data confidentiality and integrity
- Algorithms are public; keys must be secret
- Larger key sizes increase security
- Understanding basics is essential before advanced cryptography


