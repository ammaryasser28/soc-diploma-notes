# 🔐 Types of Encryption Algorithms

## 📌 Overview

Encryption algorithms are used to protect data by converting it into an unreadable form.  
There are **two main types of encryption algorithms** used in modern cryptography:

1. Symmetric Encryption
2. Asymmetric Encryption

Each type has its own use cases, strengths, and limitations.

---

## 🔑 Symmetric Encryption  
### (Same Key for Encryption and Decryption)

### Definition
Symmetric Encryption uses **one shared secret key** for both encryption and decryption.  
Both the sender and the receiver must possess the same key.

---

### Characteristics
- ⚡ Very fast
- 🗄️ Suitable for encrypting large amounts of data
- 🔐 Security depends on keeping the key secret

---

### Key Challenge
**Key Distribution Problem**  
- The secret key must be shared securely.
- If the key is intercepted, the encrypted data is compromised.

---

### Common Algorithms
- **DES** (Data Encryption Standard – outdated and insecure)
- **AES** (Advanced Encryption Standard – widely used and secure)
- **ChaCha20** (Modern, fast, and secure stream cipher)

---

### Process Flow

- Plaintext → Encrypt (Shared Key) → Ciphertext
- Ciphertext → Decrypt (Same Key) → Plaintext

---

## 🔐 Asymmetric Encryption  
### (Public Key and Private Key)

### Definition
Asymmetric Encryption uses **two different keys**:

- 🔓 **Public Key**: Used for encryption and can be shared publicly
- 🔒 **Private Key**: Used for decryption and must be kept secret

Data encrypted with the public key can only be decrypted using the corresponding private key.

---

### Characteristics
- 🔁 Solves the key distribution problem
- 🔒 Provides secure initial communication
- 🐢 Slower than symmetric encryption

---

### Use Cases
- Encrypting small amounts of data
- Secure key exchange
- Digital certificates and authentication

---

### Common Algorithms
- **RSA**
- **Elliptic Curve Cryptography (ECC)**

---

### Process Flow
- Plaintext → Encrypt (Public Key) → Ciphertext
- Ciphertext → Decrypt (Private Key) → Plaintext

---

## ⚖️ Comparison Table

| Feature | Symmetric Encryption | Asymmetric Encryption |
|------|---------------------|----------------------|
| Keys Used | One shared key | Public & Private keys |
| Speed | Very fast | Slower |
| Security | Depends on key secrecy | Strong key exchange |
| Data Size | Large amounts | Small data or keys |
| Examples | AES, DES, ChaCha20 | RSA, ECC |

---

## 🌐 Real-World Usage

In real-world applications, **both encryption types are used together**.

### Example: HTTPS / TLS
1. Asymmetric Encryption  
   - Used to securely exchange a symmetric key.
2. Symmetric Encryption  
   - Used to encrypt the actual data efficiently.

This hybrid approach provides both **security** and **performance**.

---

## ✅ Key Takeaways

- Symmetric encryption is fast and efficient for large data.
- Asymmetric encryption provides secure key exchange.
- Modern systems combine both techniques.
- Choosing the right encryption method depends on the use case.



