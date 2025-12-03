# 🚀 Operating Systems Basics for SOC Professionals

---

## 🖥️ OS as an Interface Provider

Operating Systems provide different ways for users to interact with the computer:

### **🔹 Graphical User Interface (GUI)**

* A visual interface with windows, icons, and buttons.
* Designed for **normal users** to make the experience easy and intuitive.

### **🔹 Command-Line Interface (CLI)**

* Text-based interface used through commands.
* Extremely **powerful for IT, SOC Analysts, and Cyber Security Experts**.
* Allows automation, scripting, quicker system navigation, and deeper system control.

---

## ⚙️ OS as a System Coordinator

The Operating System manages and organizes all system resources:

### **📁 File Management**

* Creates, deletes, reads, and organizes files and directories.

### **🔐 Security Management**

* Manages authentication, permissions, and access control.
* Ensures only authorized users can access sensitive data.

### **🌐 Networking**

* Handles network communication.
* Ensures safe data transfer between devices.

### **📊 System Monitoring**

* Tracks system performance and hardware usage.
* Logs system events and errors — crucial for **SOC Investigations**.

---

## 🧠 The Kernel — The Core of the Operating System

The **Kernel** is the brain of the OS.

### **🔹 What is the Kernel?**

* The central component of any Operating System.
* First thing that loads when the system starts.
* Last thing that shuts down.

### **🔹 What does it do?**

* Works as the **bridge** between user applications and hardware.
* Controls CPU, RAM, Disk, I/O devices.
* Ensures all programs run safely and efficiently.

---

## 🏷️ Types of Operating Systems

### **🪟 Windows OS**

* Mostly used on personal computers and workstations.
* User-friendly, widely deployed in corporate environments.

### **🐧 Linux OS**

* Commonly used on servers, web servers, cloud infrastructure.
* Powers the **most powerful supercomputers in the world**.
* Preferred in cyber security because of flexibility and control.

### **💬 What is the most used OS and why?**

* **Windows** is the most used on desktops → user-friendly + preinstalled.
* **Linux** dominates servers → secure, stable, open-source.

### **⚠️ Linux Vulnerabilities**

* Linux is powerful… but misconfiguration or vulnerabilities in it can be **disastrous** for critical infrastructure.

---

## 💾 Hard Drive vs RAM

Understanding how data is stored is critical for **SOC** and **Digital Forensics**.

### **📀 Permanent Storage (HDD / SSD)**

* Stores data even when the system is turned off.
* Contains OS files, logs, programs, documents.

### **⚡ Temporary Storage (RAM)**

* Stores data temporarily while programs are running.
* Cleared every time the system restarts.

### **🧩 Why does this matter?**

* Programs **must** be loaded from HDD → RAM to run.
* RAM contains volatile but important evidence: processes, connections, keys.
* Crucial in **memory forensics**.

---

## 📚 Summary for SOC Beginners

| Concept             | Why It Matters in SOC                             |
| ------------------- | ------------------------------------------------- |
| GUI vs CLI          | CLI enables faster investigation & automation     |
| File Management     | Investigate logs, artifacts, and suspicious files |
| Security Management | Access control & incident response                |
| Kernel              | Understanding how the OS works under the hood     |
| Linux & Windows     | Different environments = different threats        |
| RAM vs HDD          | Memory forensics & evidence collection            |



