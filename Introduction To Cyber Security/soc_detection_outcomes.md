# SOC Detection Outcomes  
## True Positive, False Positive, True Negative, False Negative

## Introduction
In a **Security Operations Center (SOC)**, detection tools such as **SIEM, IDS, IPS, and EDR** continuously monitor events and generate alerts.  
Each alert must be evaluated to determine whether it correctly identifies a real security incident.

This document explains the four possible detection outcomes:
- True Positive
- False Positive
- True Negative
- False Negative

---

## Core Concept
Every detection decision is based on two factors:
1. **What the security system reports**
2. **What actually happens in reality**

This leads to four possible scenarios.

---

## 1. True Positive (TP)
### Correct Detection

**Definition:**  
The system detects an attack **and** the attack is real.

**Example:**  
- SIEM generates an alert for a **Brute Force Attack**
- Investigation confirms multiple unauthorized login attempts

**Impact in SOC:**  
- Correct alert
- Immediate and appropriate response

✅ This is the **desired outcome**.

---

## 2. False Positive (FP)
### False Alarm

**Definition:**  
The system detects an attack, but **no real attack exists**.

**Example:**  
- A user enters the wrong password several times
- SIEM flags it as a Brute Force Attack
- Activity is confirmed as legitimate

**Impact in SOC:**  
- Wasted analyst time
- Alert fatigue
- Reduced efficiency

⚠️ False positives should be minimized.

---

## 3. True Negative (TN)
### Correct Non-Detection

**Definition:**  
The system reports no attack **and** no attack actually exists.

**Example:**  
- Normal user login activity
- No alert generated

**Impact in SOC:**  
- System behaving correctly
- Normal operation

✅ Indicates accurate tuning of detection rules.

---

## 4. False Negative (FN)
### Missed Attack (Critical Risk)

**Definition:**  
The system fails to detect an attack that **actually occurs**.

**Example:**  
- Data exfiltration takes place
- Detection rules are misconfigured
- No alert is generated

**Impact in SOC:**  
- Undetected breach
- Potential data loss
- Severe security risk

🚨 This is the **most dangerous scenario**.

---

## Detection Outcomes Summary

| System Alert | Actual Event | Result |
|------------|-------------|--------|
| Attack | Attack | True Positive |
| Attack | No Attack | False Positive |
| No Attack | No Attack | True Negative |
| No Attack | Attack | False Negative |

---

## Real-World Analogy: Home Alarm System

| Scenario | Description |
|--------|------------|
| True Positive | Burglar enters, alarm triggers |
| False Positive | Pet moves, alarm triggers |
| True Negative | No movement, alarm silent |
| False Negative | Burglar enters, alarm silent |

---

## SOC Best Practices
- Reduce **False Positives** to prevent analyst fatigue
- Minimize **False Negatives** to avoid missed attacks
- Continuously tune detection rules and correlations

---

## Key Interview Statement
> False Negative is more dangerous than False Positive because it allows real attacks to go undetected.

---

## Conclusion
Understanding detection outcomes is critical for SOC analysts to:
- Evaluate alerts accurately
- Improve detection efficiency
- Protect organizational assets effectively

---

<img width="1536" height="1024" alt="ChatGPT Image Jan 12, 2026, 02_31_23 PM" src="https://github.com/user-attachments/assets/7c963b00-711b-4a38-bac2-610e18d160fd" />

