# Domain Hijacking

## Overview
**Domain Hijacking** is an attack in which an attacker gains unauthorized control over a domain name by manipulating domain registration or DNS information at the **Domain Registrar** level.  
This attack often exploits weak or nonexistent authentication procedures used by some registrars when processing domain change requests.

---

## How Domain Management Normally Works
- Domain owners manage their domains through a **Registrar**.
- Changes such as:
  - DNS records
  - Nameservers
  - IP address mappings  
  require authentication and authorization.
- Registrars are expected to verify the identity of the requester before applying changes.

---

## The Vulnerability
Many domain registrars perform **insufficient verification** when processing requests to modify domain information.  
In some cases, a convincing email or fax is enough to authorize critical changes.

This creates an opportunity for attackers to impersonate legitimate domain owners.

---

## How the Domain Hijacking Attack Works
1. The attacker gathers information about the target domain.
2. The attacker sends a **forged or socially engineered request** (email or fax) to the registrar.
3. The request asks to modify DNS or IP information for the domain.
4. Due to weak verification, the registrar applies the changes.
5. The domain now points to systems controlled by the attacker.

Example:
`victim.com → attacker-controlled IP`

---

## Impact of Domain Hijacking
- Redirection to malicious websites
- Credential and data theft
- Malware distribution
- Email interception
- Reputation damage to the legitimate domain owner

---

## Why This Attack Is Dangerous
- Affects all services tied to the domain (web, email, APIs).
- Often remains undetected for long periods.
- Breaks trust in the domain’s identity.
- Can be leveraged for large-scale phishing campaigns.

---

## Common Attack Techniques
- Social engineering against registrar support staff
- Forged emails and faxes
- Exploiting weak registrar authentication policies

---

## Mitigation Techniques

### 1. Registrar Lock
- Prevents unauthorized domain transfers or changes.
- Requires additional verification to unlock.

### 2. Strong Authentication
- Multi-Factor Authentication (MFA)
- Account-level passwords and access controls

### 3. Secure Change Requests
- Signed and encrypted email communication
- Strict mail header verification

### 4. Monitoring and Alerts
- Notifications for DNS or registrar-level changes
- Regular audits of domain configuration

### 5. Use Reputable Registrars
- Established registrars enforce strict verification procedures
- Reduced reliance on manual email or fax-based changes

---

## Comparison with DNS Cache Poisoning
| Domain Hijacking | DNS Cache Poisoning |
|------------------|--------------------|
| Targets the registrar | Targets DNS resolvers |
| Changes are persistent | Changes are temporary |
| Full domain control | Traffic redirection only |
| Administrative attack | Technical attack |

---

## Summary
- Domain Hijacking exploits weak registrar authentication.
- Attackers impersonate domain owners to modify domain records.
- The domain is redirected to attacker-controlled systems.
- Strong registrar security practices are the primary defense.


