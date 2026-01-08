# Cryptography Overview

## Introduction

Cryptography is the science and practice of securing information by transforming it into a format that is unreadable to unauthorized individuals.  
Its main purpose is to protect data while it is being stored or transmitted, ensuring that sensitive information remains secure.

Cryptography helps achieve the following security goals:

- **Confidentiality**: Prevents unauthorized access to data  
- **Integrity**: Ensures data is not altered during storage or transmission  
- **Authentication**: Verifies the identity of the communicating parties  
- **Non-Repudiation**: Prevents senders from denying their actions  

---

## Why Cryptography Is Important

Data is constantly:
- Stored on devices and servers (**Data at Rest**)
- Transmitted across networks (**Data in Transit**)

Without cryptography, this data can be intercepted, modified, or impersonated by attackers.

---

## Encrypted Message Example

The following text appears unreadable at first glance:
- Ygneqog vq Eadgt Ugewtkva Htkgpfu.
- Vjku ku aqwt hktuv etarvqitcrja ngevwtg.

This is a simple example of encrypted data.

---

## Caesar Cipher (Shift Cipher)

The encryption method used in this example is called the **Caesar Cipher**, also known as a **Shift Cipher**.

### How the Caesar Cipher Works

- Each letter in the plaintext is shifted forward in the alphabet by a fixed number.
- In this example, the **shift value is 2**.

#### Letter Shifting Example
- A → C
- B → D
- C → E

To decrypt the message, each letter is shifted **2 positions backward**.

---

## Decrypted Message

After reversing the shift, the original message becomes:
- Welcome to Cyber Security Friends.
- This is our first cryptography lecture.


This demonstrates how encrypted data can appear meaningless until the correct method and key are applied.

---

## The Role of Algorithm and Key

A fundamental concept in cryptography is:

> Encryption = Algorithm + Key

- **Algorithm**: The encryption method (Caesar Cipher)
- **Key**: The secret value used in encryption (Shift = 2)

### Important Note

If you don’t know the algorithm or the key, decrypting the message becomes difficult.  
With modern cryptographic algorithms, breaking encryption without the key is computationally infeasible.

---

## Security Perspective

- Caesar Cipher is **not secure** and can be easily broken.
- It is used only for **educational purposes**.
- Modern cryptography uses advanced algorithms such as:
  - AES (Symmetric Encryption)
  - RSA (Asymmetric Encryption)
  - ECC (Elliptic Curve Cryptography)

---

## Key Takeaways

- Cryptography protects data confidentiality, integrity, and authenticity.
- Even simple encryption can hide the meaning of data.
- Strong security depends on well-designed algorithms and secret keys.
- Understanding basic ciphers helps build a foundation for advanced cryptography.

---

## Disclaimer

This document is for educational purposes only and should not be used to protect real or sensitive data.
