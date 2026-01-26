# 🖥 Virtualization

---

## 📌 Overview
**Virtualization** is a technology that allows you to run **multiple virtual machines (VMs)** on a single physical system.  
Each VM behaves like a completely independent computer with its own operating system, applications, and resources.

All of this is made possible by a **hypervisor**, which manages the creation and operation of virtual machines.

---

## 🎯 Hypervisors

### 1️⃣ Bare-metal Hypervisor (Type 1)
- Runs **directly on the hardware** without a host OS
- Provides high performance and is commonly used in enterprise environments
- Examples:
  - Microsoft Hyper-V
  - VMware ESXi

### 2️⃣ Hosted Hypervisor (Type 2)
- Runs **on top of an existing operating system**
- Easier to set up for personal or testing environments
- Examples:
  - VirtualBox
  - VMware Workstation

---

## ⚙ Virtual Machine Hardware
Each virtual machine is configured to appear as a real computer:
- Network Interface Card (NIC)
- Video card
- Hard disk drive (HDD)
- And more…

**Important:** All hardware in a VM is **virtualized**; it’s simulated by the hypervisor and does not physically exist.

---

## 🛠 Benefits of Virtualization
- Run multiple operating systems on a single physical machine  
- Isolate systems for testing, security, or development purposes  
- Save costs by reducing the need for multiple physical machines  
- Simplify backups, snapshots, and recovery  
- Easy experimentation with different OS environments  

---

## 🧠 Key Takeaways
- Virtualization allows multiple independent computers on one physical system  
- Hypervisors manage resources and simulate hardware for each VM  
- Bare-metal hypervisors are more performant for enterprise use  
- Hosted hypervisors are simpler for personal or testing environments  

