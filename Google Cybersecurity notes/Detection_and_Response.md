# Detection and Incident Response

## 1. Incident Management
* **Incident:** An event that jeopardizes the **CIA Triad** or violates policy.
* **The CSIRT (Computer Security Incident Response Team):**
    * **Security Analyst:** Triage and investigation (The First Responder).
    * **Technical Lead:** Guides the technical strategy.
    * **Incident Coordinator:** Manages communication.
* **The 5 W's:** Who, What, When, Where, Why.

## 2. The NIST Incident Response Lifecycle


[Image of NIST Incident Response Lifecycle]

1.  **Preparation:** Hardening systems, creating **Playbooks** (guides) and **Incident Response Plans**.
2.  **Detection & Analysis:**
    * **Triage:** Prioritizing alerts.
    * **Chain of Custody:** Documenting who handled evidence (critical for legal cases).
    * **IoC (Indicator of Compromise):** Evidence of a breach (e.g., Data Exfiltration).
3.  **Containment, Eradication, & Recovery:**
    * *Containment:* Isolating the threat.
    * *Eradication:* Removing the malware/root cause.
    * *Recovery:* Restoring from backups.
4.  **Post-Incident Activity:**
    * **Lessons Learned:** Meeting to improve future response.
    * **Final Report:** Full documentation of the event.

## 3. Detection Tools
* **SIEM (Security Information & Event Management):**
    * **Collects** logs -> **Normalizes** (cleans) data -> **Analyzes** rule sets -> Alerts.
* **SOAR:** Automates response actions (e.g., auto-blocking an IP).
* **IDS/IPS (Intrusion Detection/Prevention):**
    * **NIDS:** Monitors Network traffic.
    * **HIDS:** Monitors Host (Device) activity.
    * **Signature Analysis:** Matches traffic against known threat patterns.

## 4. Technical Analysis
### Packet Analysis (IPv4 Header)
* **TTL (Time to Live):** Prevents infinite loops.
* **Protocol:** ID number (e.g., TCP=6).
* **Source/Dest IP:** Address of sender/receiver.
* **Payload:** The actual data inside.

### Log Management
* **Formats:**
    * **Syslog:** Standard protocol (Header + Message).
    * **JSON:** Key-value pairs `{ "user": "admin" }` (Easy to read).
    * **XML:** Uses tags `<user>admin</user>`.
    * **CSV:** Comma-separated (spreadsheet style).

*Back to [[Cybersecurity_Knowledge_Base]]*
