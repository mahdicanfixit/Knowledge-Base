## 🛡️ Domain 5.1: Governance, Risk, and Compliance (GRC)

### 1. The Hierarchy of Security Documentation

Security isn't just firewalls; it’s a framework of expectations.

- **Security Goals:** The high-level "Why." This always maps back to the **CIA Triad** (Confidentiality, Integrity, and Availability).
    
- **Security Policies:** The "What" and "Why." High-level statements identifying security goals (e.g., "All company data must be encrypted at rest").
    
- **Acceptable Use Policy (AUP):** The most common policy. It defines what is considered "appropriate" use of company equipment (Internet, phones, laptops).
    
    - _Pro-tip:_ AUPs are critical for **limiting legal liability** for the organization.
        
- **Procedures:** The "How." Step-by-step instructions for specific tasks (e.g., "How to wipe a virus-infected laptop").
    
- **Roles & Responsibilities:** Defining who is in charge of what. Without this, enforcement fails.
    

### 2. Business Continuity & Disaster Recovery (BCP/DRP)

Planning for when things go wrong so the business doesn't go under.

- **Alternative Processes:** If the network goes down, how do we make money? (e.g., manual paper receipts, phone-in approvals).
    
- **Disaster Recovery Plan (DRP):** A technical subset of BCP. It focuses on IT restoration:
    
    - Recovery locations (Hot/Cold sites).
        
    - Data restoration methods.
        
    - Application restoration.
        
- **Business Continuity Planning (BCP):** The broader umbrella. It ensures the _entire_ organization keeps running during a disaster.
    

### 3. Incident Response (IR)

When the prevention fails (Malware execution, DDoS, Data Theft), the IR team steps in.

- **The Stakeholders:** IR isn't just IT. It includes:
    
    - **Management:** For corporate support.
        
    - **Compliance Officers:** To handle legal/regulatory fallout.
        
    - **Technical Staff:** To pull the plugs and clean the systems.
        
    - **User Community:** To stay informed and alert.
        
- **NIST SP 800-61 Lifecycle:**
    
    1. **Preparation** -> 2. **Detection & Analysis** -> 3. **Containment, Eradication, & Recovery** -> 4. **Post-Incident Activity** (Lessons Learned).
        

![NIST incident response lifecycle, AI generated](https://encrypted-tbn2.gstatic.com/licensed-image?q=tbn:ANd9GcT7pnEUpWAYZZjn9Ousr0NcygGwDC10U__jeEg8duYuVlso2mS4nlpoEsBNDnsgrLHffOdY5m30986n5j8AQuaDRmdhoK4EWJV_uKFyKayI0swPzgM)

vaeenma

### 4. Change Management

The process of making modifications (Software upgrades, Firewall config changes) without breaking the environment.

- **The Risk:** Change is one of the most common causes of downtime.
    
- **The Policy:** Must include **Frequency**, **Duration**, **Installation Process**, and a **Fallback (Rollback) Plan**.
    
- **The Challenge:** Often the hardest part isn't the tech; it's changing the **Organizational Culture** to follow the process.
    

### 5. Software Development Lifecycle (SDLC)

Building security into the software from day one rather than "bolting it on" at the end.

- **Phases:** Requirements -> Design -> Development -> Testing -> Deployment -> Maintenance.
    
- **Frameworks:** Provide a structured path to ensure no steps are skipped.

![](../../Pasted%20image%2020260505203130.png)

---

## 🛡️ Domain 5.1: Standards, Access, & Encryption (Continued)

### 1. Frameworks and Standards

Organizations don't have to reinvent the wheel; they use established "blueprints."

- **Industry Standards:** Many organizations follow global standards like **ISO/IEC 27001** or **NIST SP 800-53**.
    
- **Custom Standards:** Some organizations create their own internal "flavor" of these frameworks to fit their specific business needs.
    

### 2. Access Control Governance

This defines **who** can touch **what**, **when**, and **how**.

- **Access Control Policies:** Formal rules determining information access under specific circumstances.
    
- **Hybrid Systems:** No system is limited to just one "flavor" (like DAC or MAC). Modern organizations use a mix of **Role-Based (RBAC)**, **Attribute-Based (ABAC)**, and **Mandatory Access Control (MAC)** depending on the sensitivity of the data.
    
- **Lifecycle Management:**
    
    - **Provisioning:** Documenting and granting the specific privileges a user needs.
        
    - **Deprovisioning:** A formal "off-boarding" process to ensure access is removed immediately when an employee leaves.
        

### 3. Physical Security Policies

Governance over the "meat-space"—the building and the hardware.

- **Access Rules:** Clear distinctions between **Employee** access (badges, biometrics) and **Visitor** access (registration, badges).
    
- **Monitoring Standards:** Defining the requirements for motion detection, CCTV coverage, and alarm systems.
    
- **Human Controls:** Policies requiring **escorts** for visitors and specific procedures for securing property (e.g., locking server racks).
    

### 4. Data Security & Encryption Standards

This is the "technical law" of the company. It defines the minimum bar for protecting bits and bytes.

- **Encryption Minimums:** Explicitly stating which algorithms are allowed (e.g., "AES-256 is the minimum for data at rest").
    
- **State of Data:**
    
    - **Data at Rest:** Encryption for hard drives and databases.
        
    - **Data in Transit:** Standards for TLS/SSL when data moves over the network.
        
    - **Data in Use:** Security for data currently in RAM or CPU cache.
        
- **Credential Security:** Specific rules on **password storage** (e.g., "Passwords must be salted and hashed using Argon2 or bcrypt, never stored in plain text").

---

