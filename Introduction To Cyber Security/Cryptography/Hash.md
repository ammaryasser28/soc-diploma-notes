# 🔐 Cryptography & Hashing – Fundamentals

This README explains the **hash concept**, the difference between **hashing and encryption**, popular hash algorithms, collision problems, and best practices in cryptography.

---

## 📌 What is a Hash?

A **hash function** is a mathematical function that converts any input (text, file, password, or data) into a **fixed-size output** called a:

- **Hash**
- **Message Digest**

### 🔹 Hash Properties
- **One-way function** → impossible (in theory) to retrieve the original data from the hash
- **Fixed output size** → same length regardless of input size
- **Deterministic** → same input always produces the same hash
- **Avalanche effect** → small changes in input produce completely different hashes
- **Fast to compute**

### 🔹 Example
Input: "Hello"
SHA-256 Hash: 185f8db32271fe25f561a6fc938b2e264306ec304eda518007d1764826381969


- Tool suggestion: [CyberChef](https://gchq.github.io/CyberChef/) → use `hash2` filter and specify 256-bit

---

## 🔐 Hash vs Encryption

| Feature | Hash | Encryption |
|---------|------|------------|
| Key required | No | Yes (symmetric or asymmetric) |
| Reversible | No | Yes (can decrypt with key) |
| Purpose | Data integrity & verification | Confidentiality (hide data) |
| Output | Fixed-size | Variable (depends on input & key) |
| Sensitivity | Small change → different hash | Key change → different ciphertext |

### 🔹 Encryption Examples
- Disk encryption  
- VPNs  
- HTTPS / Web traffic  
- File protection

---

## 📌 Real-life Use of Hash

- When downloading software from official websites, you can often see the **hash of the executable**
- Example: [VLC Media Player hashes](https://images.videolan.org/vlc/index.wa.html)  
- Purpose: Verify file integrity → ensures the file hasn’t been modified

---

## 📌 Hash Algorithms

### MDX Family
- Includes:
  - **MD2** → very slow  
  - **MD4** → faster  
  - **MD5** → most common historically  
- All generate **128-bit hashes**
- ⚠️ Deprecated today; MD5 is **not recommended** due to vulnerabilities

### SHA Family
- Developed by **NIST**
- SHA-0 → flawed, no longer used  
- SHA-1 → old and broken  
- **SHA-2** → current standard (SHA-256 widely used)  
  - The number indicates **hash size in bits**  
- SHA-3 → very strong, rarely used, fallback in case SHA-2 is broken

---

## ⚠️ Collision Problem

- **Collision**: when two different inputs produce the same hash  
- A good hash function should **never collide**  
- Known vulnerable families:
  - SHA-1 → collisions exist  
  - MDX family → collisions exist  
- Example: if there are 100 possible hash values and 101 documents → at least two documents will produce the same hash  

> Collisions are a security risk: an attacker could replace a legitimate file with a malicious one that has the same hash

---

## 🧠 Key Takeaways

1. **Hash is one-way** → cannot revert to original data  
2. **Fixed-size output** → same length regardless of input  
3. **Integrity check** → ensures data has not changed  
4. **Avalanche effect** → small changes produce completely different hashes  
5. **Use modern algorithms** → SHA-256 or SHA-3  
6. **Hash ≠ Encryption** → encryption is reversible; hash is not


