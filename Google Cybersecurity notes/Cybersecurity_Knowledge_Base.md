# Cybersecurity Knowledge Base

## 1. Core Foundations

### The CIA Triad
The fundamental model for information security.

1.  **Confidentiality:** Protecting data from unauthorized access.
2.  **Integrity:** Ensuring data accuracy and trustworthiness.
3.  **Availability:** Ensuring data is accessible when needed.

### The Security Analyst Role
**Goal:** Protect organizations by identifying risks and developing solutions.
* **Key Soft Skills:** Communication, Collaboration, Analysis, Problem-solving.
* **Ethics:** Unbiased, confidential, and compliant with laws (e.g., leaving patient data unattended violates HIPAA).

### Data Privacy Types
* **PII (Personally Identifiable Information):** Full name, DOB, Address, Email.
* **SPII (Sensitive PII):** Stricter regulations apply. Includes SSN, financial accounts.
    * *Risk:* Theft of SPII leads to severe identity theft.

---

## 2. Threat Landscape
*See the detailed breakdown in: [[Threats_and_Vulnerabilities]]*

* **Malware & Ransomware**
* **Social Engineering (Vishing, Phishing)**
* **The 3 Layers of the Web**
* **Historical Attacks (Morris Worm, LoveLetter)**

---

## 3. Frameworks & Governance
*See the detailed breakdown in: [[Security_Frameworks]]*

* **NIST CSF & RMF** (Federal Standards)
* **CISSP** (8 Domains of Security)
* **OWASP** (Web Security Principles)
* **Regulatory Compliance** (GDPR, PCI DSS)

---

## 4. Security Operations & Architecture
*See detailed breakdown in: [[Network_Security_Architecture]]*

### Network Fundamentals
* **Devices:** Router vs. Switch vs. Hub.
* **Addressing:** IPv4 vs IPv6, MAC Addresses, Ports.
* **Models:** TCP/IP (4 Layers).

### Defense & Hardening
* **Hardening:** Reducing the attack surface (Patching, MFA, Disabling unused ports).
* **Tools:** Firewalls (NGFW), VPNs, IDS vs. IPS.
### Key Tools
| Tool Type          | Description                                                                     | Examples |
| :----------------- | :------------------------------------------------------------------------------ | :--------------------------- |
| **SIEM**           | Security Information and Event Management. Collects logs and alerts on threats. | Splunk, Google Chronicle |
| **Packet Sniffer** | Captures and analyzes network traffic protocols.                                | Wireshark, tcpdump |
| **Playbooks**      | Manuals detailing step-by-step incident response actions.                       | *Custom Organizational Docs* |

---

## 5. Linux & SQL databases
*See the detailed breakdown in: [[SQL_and_Databases]] & [[Linux_and_OS_Security]]
### Linux fundamentals
* **Distros & commands:** Red hat, kali linux. /root commands
* **Permissions:** root vs sudoers vs users vs groups
### SQL commands
* **SELECT & FROM commands:** the basics of SQL commands and their purposes
* **filtering:** WHERE and LIKE to fliter speific requests

---

## 7. Identity, Cryptography & AppSec (Course 5)

### Cryptography
*See details in: [[Cryptography_and_Identity heh]]*
* **Encryption:** Symmetric (Shared Key) vs. Asymmetric (Public/Private Keys).
* **PKI:** Framework for secure web exchange (HTTPS).
* **Hashing:** Ensuring Data Integrity.

### Identity & Access (IAM)
* **AAA Framework:** Authentication, Authorization, Accounting.
* **MFA:** Combining factors (Know, Have, Are) for stronger security.
* **Tokens:** OAuth and Session IDs.

### Vulnerability Management
*See details in: [[Vulnerability_and_Threat_Modeling]]*
* **Defense in Depth:** 5 Layers (Perimeter $\to$ Data).
* **CVE & CVSS:** The global standard for scoring system flaws (0-10 Scale).
* **Threat Modeling:** Using frameworks like **PASTA** to simulate attacks.

---

## 8. Detection and Response (Course 6)
*See detailed breakdown in: [[Detection_and_Response]]*

### Key Concepts
* **Incident Lifecycle (NIST):**
    1.  **Preparation** (Plans & Playbooks).
    2.  **Detection & Analysis** (Triage & Validation).
    3.  **Containment, Eradication, & Recovery** (Stopping & Fixing).
    4.  **Post-Incident** (Lessons Learned).
* **Triage Logic:**
    * **True Positive:** Real threat.
    * **False Positive:** False alarm.
    * **False Negative:** Missed threat (Dangerous!).

### Core Tools
* **SIEM:** The central tool that aggregates and normalizes logs to find alerts.
* **IDS vs. IPS:** Detection (Alerts) vs. Prevention (Stops).
* **Packet Sniffing:** Capturing network traffic (using tools like Wireshark) to analyze headers and payloads.

