# 🕵️ Steganography vs Cryptography

## 📌 Overview

Steganography and Cryptography are two important techniques used to protect information.  
While both aim to secure data, they achieve this in very different ways.

Understanding the difference is essential for information security professionals.

---

## 🔐 Cryptography

### Definition
Cryptography is the practice of protecting information by transforming readable data into an unreadable format.

### Key Concept
> Cryptography hides the **meaning** of the message but not its existence.

### Example
- Plaintext: Hello World
- Ciphertext: Jgnnq Yqtnf
- The encrypted message looks strange
- Without the key, it cannot be understood

---

## 🕶️ Steganography

### Definition
Steganography is the technique of hiding information inside another file or medium so that **no one even knows a secret message exists**.

### Common Carriers
- Images
- Audio files
- Video
- Text files

### Key Concept
> Steganography hides the **existence** of the data itself.

---

## ⚖️ Core Difference

| Aspect | Cryptography | Steganography |
|--------|-------------|---------------|
| What it hides | Meaning of the message | Existence of the message |
| Output | Weird-looking encrypted text | Normal-looking file |
| Detection | Everyone knows communication is happening | No one knows communication exists |
| Goal | Confidentiality | Stealth / Hidden communication |

---

## 🔐 Using Both Together

Some attackers (and defenders) use a combination of **both techniques**:

1. Encrypt the data using cryptography
2. Hide the encrypted data inside an image, audio, or video file

### Benefits
- Strong confidentiality
- Hidden communication
- Extra layer of protection

---

## ✅ Legitimate Uses of Steganography

Steganography is not only for malicious purposes. Example:

- **Digital Watermarking**
  - Hide a watermark in an image
  - Protect against plagiarism
  - Even if the image is edited, part of the watermark remains

---

## 🖼️ Practical Example (Lecture Exercise)

<img width="663" height="216" alt="image" src="https://github.com/user-attachments/assets/898b3246-8606-438f-ae51-3fb290fbbb0c" />

- A hidden message can be embedded in a picture
- Students can extract the message to remember the difference between Steganography and Cryptography

### Steps:
1. Find the **stego_image** in the lecture session
2. Use the tool: [Aperisolve](https://aperisolve.com/)
3. Upload the image
4. Analyze for hidden messages

> Steganography can also be applied to sound files or other file types.

---

## 🧠 Summary

- **Cryptography**: Hides the meaning of the message  
- **Steganography**: Hides the existence of the message  
- Both can be combined for enhanced security  
- Steganography has legal and practical applications (e.g., digital watermarking)
