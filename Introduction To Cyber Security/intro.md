# Cybersecurity Basics: CIA, AAA, PPT, Least Privilege, Authentication, Access Control, and Logging

This repository contains study notes for understanding the fundamental concepts of cybersecurity: **CIA (Confidentiality, Integrity, Availability)**, **AAA (Authentication, Authorization, Accounting)**, **PPT (Policy, Procedures, Training)**, **Least Privilege Principle**, **Authentication Factors & Password Security**, **Access Control Models (DAC & RBAC)**, and **Logging & Audit**.

---

## 1️⃣ CIA: Confidentiality, Integrity, Availability

### Confidentiality (سرية)

* Ensuring data is only accessible to authorized people.
* Example: Encrypting sensitive data so hackers can’t read it.

### Integrity (نزاهة / سلامة)

* Ensuring data is accurate and not tampered with.
* Only authorized people can modify it.
* Example: Digital signatures or checksums.

### Availability (توافر)

* Ensuring systems and data are available when needed.
* Example: Backups, redundancy, DR sites, anti-Ransomware solutions.

**Quick reminder:**

* Who can read a file → Confidentiality
* Who can write → Integrity
* Is it always available → Availability

### CIA Importance by Industry

* **Pharmaceuticals:** Confidentiality is critical (valuable drug formulas).
* **Finance:** Integrity is vital (any mistake can collapse the system).
* **IT/Services:** Availability matters most (services must always run).

---

## 2️⃣ AAA: Authentication, Authorization, Accounting

### Authentication

* Who are you? Verify your identity.
* Example: Username + Password, Multi-Factor Authentication (MFA).

### Authorization

* What are you allowed to do?
* Example: Employee can read files but not delete them.

### Accounting

* Tracking and recording user activities.
* Example: Logging login times, data accessed, or actions taken.

---

## 3️⃣ PPT: Policy, Procedures, Training

### Policy

* High-level rules defining how security is managed.
* Example: Password policy requiring strong and regular updates.

### Procedures

* Step-by-step instructions to implement policies.
* Example: How to securely reset a user password.

### Training

* Ensure everyone understands policies and procedures.
* Example: Regular phishing awareness training.

**Note:** Policies and procedures are useless if no one knows about them.

---

## 4️⃣ Least Privilege Principle (أقل صلاحية ممكنة)

### Definition

* Give each user or system **only the access needed to perform their job** and nothing more.

### Why it matters

* **Prevent misuse of unnecessary permissions**.
* **Limit damage** if an account is compromised.

### Examples

1. **Normal user:** Can read files but cannot install software.
2. **Developer:** Can write to test servers but not production servers.
3. **Admin:** Full permissions to install software and manage systems.

### Key point

* Admin accounts are the most important and should be **carefully protected**.

---

## 5️⃣ Authentication Factors & Password Security

### Authentication Factors

1. **Something you know:** Passwords, PINs, cognitive questions.
2. **Something you have:** Physical device like token, USB key, or mobile for OTP.
3. **Something you are:** Fingerprints, retina/iris scans, facial recognition, typing dynamics.
4. **Somewhere you are:** Location-based authentication (e.g., VPN from a specific country).
5. **Combination:** Often systems use multiple factors (2FA / MFA).

### Keep Your Password Strong

* Make it complex: Use uppercase, special characters, numbers, and make it longer.
* Hardware is getting faster, making passwords easier to crack.
* Quantum computing is a potential future threat.
* Don’t share too much personal information.
* Don’t reuse the same password across accounts.

### Account Lockout

* Annoying but necessary for security.
* Balance between number of attempts and lockout duration.
* Don’t store passwords in text files; use a trusted password manager.

---

## 6️⃣ Access Control Models

### Discretionary Access Control (DAC)

* The **owner of a file/folder/resource** decides who can access it and what they can do (read, write, execute).
* Default access model in **Windows and Linux**.
* Each file has an owner who assigns permissions (ACL), and the system enforces those permissions.
* Called Discretionary because **permission decisions are left to the owner**.

**Example:** File has owner → Owner assigns permissions → System enforces access.

### Role-Based Access Control (RBAC)

* Administrators create **predefined roles/groups** and assign access based on job roles.
* New employees get added to the appropriate role → automatically granted required access.
* Centralized permission management; scales better for large organizations.

**Example:** Joe joins Accounting → Admin puts him in Accounting group → Joe gets Accounting access.

### RBAC Positives

* Easy to manage access.
* Effective when there’s high employee turnover.
* Users in same role automatically have same permissions.

### RBAC Negatives

* Can violate **Least Privilege Principle**: Just being in a role doesn’t mean a user should have all permissions.
* Needs careful review to avoid excessive access.

---

## 7️⃣ Logging & Audit

### What is Logging?

* Recording all useful activities like user and admin actions.
* Useful for **cybersecurity monitoring** and **troubleshooting**.
* Understanding logs is crucial for SOC and administrators.
* Example: 40 failed login attempts in under a minute may indicate a brute-force attack.
* Tools: **SIEM Solutions** like LogRhythm and Splunk help centralize and analyze logs.

### Importance

* You cannot define abnormal behavior if you don't know what normal looks like.
* Helps detect attacks and operational issues.

### Logging Limitations & Challenges

1. **Storage challenges:** Large organizations generate huge volumes of logs.
2. **Retention period:** How long logs are stored can be an issue.
3. **Logging methods:**

   * Local file logging: Stored on individual machines.
   * Centralized logging: Collected in a central server for analysis (recommended for large organizations).

---

## 8️⃣ Putting it all together: CIA + AAA + PPT + Access Control + Logging

* Achieving **CIA** requires correctly implemented **AAA**.
* Effective **AAA** needs solid **PPT**.
* Access control models (DAC, RBAC) help manage **who can do what**.
* Logging & Audit help detect and investigate abnormal activity.
* Cybersecurity skills are broad; every tech skill can reflect and help in security.

---

## Summary Table

| Concept           | Key Question             | Example                             |
| ----------------- | ------------------------ | ----------------------------------- |
| Confidentiality   | Who can read?            | Encrypting sensitive data           |
| Integrity         | Who can write?           | Digital signatures, checksums       |
| Availability      | Is it always accessible? | Backups, redundancy, DR sites       |
| Authentication    | Who are you?             | MFA, login credentials              |
| Authorization     | What can you do?         | File access permissions             |
| Accounting        | What did you do?         | Activity logs                       |
| Policy            | Rules                    | Password policies                   |
| Procedures        | Steps                    | Password reset procedure            |
| Training          | Know-how                 | Phishing awareness training         |
| Least Privilege   | Minimum necessary access | User/dev/admin access levels        |
| Password Security | Is it strong?            | Complex passwords, no reuse         |
| Account Lockout   | Limits misuse            | Lock accounts after failed attempts |
| DAC               | Owner decides access     | File owner assigns ACLs             |
| RBAC              | Role-based access        | Users assigned to job roles         |
| Logging & Audit   | Detect abnormal activity | SIEM tools, failed logins           |



