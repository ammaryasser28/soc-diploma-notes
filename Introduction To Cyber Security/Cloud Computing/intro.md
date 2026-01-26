# ☁️ Cloud Computing & Cloud-based Cybersecurity

---

## 📌 Overview
**Cloud Computing** is the delivery of computing resources over the Internet, including:
- Servers
- Storage
- Networking
- Databases
- Software  

**Key Features:**
- On-demand availability
- Scalable resources
- No need to own physical infrastructure

Cloud providers operate large-scale servers, and you can rent either **bare-metal resources** or **services running on top of them**, paying only for what you need.

---

## 🎯 Cloud Service Models

### 1️⃣ IaaS – Infrastructure as a Service
- **You manage:**  
  - Operating System (OS)  
  - Patching  
  - Applications  
  - Security configurations  
- **Provider manages:**  
  - Hardware  
  - Hypervisor  
  - Physical data center  

**Summary:** You handle everything above the infrastructure; provider handles the physical servers.

---

### 2️⃣ PaaS – Platform as a Service
- **You manage:**  
  - Application code  
  - Data  
- **Provider manages:**  
  - OS  
  - Runtime  
  - Middleware  
  - Patching  

**Summary:** Focus on application development; provider manages everything else.

---

### 3️⃣ SaaS – Software as a Service
- **You manage:**  
  - Users  
  - Data usage  
- **Provider manages:**  
  - Everything else (OS, applications, infrastructure, security, updates)  

**Example:** Microsoft 365  
- Most expensive model as the provider handles almost everything.

---

## 🛡 Cloud-based Cybersecurity Solutions

### Example: SIEM (Security Information and Event Management)

#### 🔹 On-premises SIEM
1. Purchase or receive preconfigured hardware with SIEM software.  
2. Install the SIEM software on servers.  
3. Collect logs from various sources.  
4. **You are responsible for:** managing servers, log storage, and monitoring.

#### 🔹 Cloud-based SIEM
1. Subscribe to a cloud SIEM service without buying or managing hardware.  
2. Platform is pre-deployed and maintained by the provider.  
3. Configure log ingestion from sources (cloud services, endpoints, network devices) using agents or APIs.  
4. Responsibilities:  
   - **Provider:** infrastructure, availability, scaling  
   - **You:** configure log sources, detection rules, and respond to alerts  

---

## 🧠 Key Takeaways
- Cloud computing allows on-demand access to resources without owning hardware.  
- Service models define responsibility:  
  - IaaS → you manage everything above hardware  
  - PaaS → you manage applications and data  
  - SaaS → you manage only users and data usage  
- Cloud-based cybersecurity solutions like SIEM reduce operational overhead while maintaining security.  

