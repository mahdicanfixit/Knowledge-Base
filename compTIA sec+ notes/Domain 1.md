# 🛡️ 1.1 Security Controls & CIA Triad

## 🏗️ Control Categories (How they are implemented)

| Category        | Description                                             | Examples                                          |
| --------------- | ------------------------------------------------------- | ------------------------------------------------- |
| **Technical**   | Controls implemented using systems (hardware/software). | Firewalls, Antivirus, OS hardening, Encryption.   |
| **Managerial**  | Administrative controls focused on design and policy.   | Security policies, standard operating procedures. |
| **Operational** | Controls implemented by _people_ rather than systems.   | Security guards, awareness training, log reviews. |
| **Physical**    | Controls that limit physical access to assets.          | Fences, locks, badge readers, guard shacks.       |

---

## 🕹️ Control Types (What they do)

> [!TIP] **Exam Strategy:** CompTIA often asks you to categorize a single item (like a fence) into both a _Category_ (Physical) and a _Type_ (Preventive).

- **Preventive:** Physically blocks access to a resource.
    
    - _Examples:_ Firewall rules, door locks, security policies.
        
- **Deterrent:** Discourages an intrusion attempt without physically stopping it.
    
    - _Examples:_ Warning signs, "No Trespassing" notices, reception desks.
        
- **Detective:** Identifies and logs an intrusion after or during the attempt.
    
    - _Examples:_ Motion detectors, system logs, security patrols.
        
- **Corrective:** Applied after an event to reverse the impact and restore operations.
    
    - _Examples:_ Restoring from backups, fire extinguishers, incident response.
        
- **Compensating:** A "workaround" used when the primary control isn't possible.
    
    - _Examples:_ Using a firewall to block an unpatchable app; using a generator during a power outage.
        
- **Directive:** Directs subjects toward compliance via rules or instructions.
    
    - _Examples:_ Policy training, signs saying "Store sensitive files in protected folders."

![697](../attachments/Pasted%20image%2020260410112953.png)

---

## 📐 The CIA Triad

### 🔐 Confidentiality

_Prevents unauthorized disclosure of information._

- **Encryption:** Encoding messages.
    
- **Access Controls:** Restricting who can see what.
    
- **2FA/MFA:** Extra confirmation before disclosing info.
    

### 💎 Integrity

_Ensures data is not modified without detection._

- **Hashing:** Mapping data to a fixed length (unique fingerprint).
    
- **Digital Signatures:** Mathematical scheme to verify data hasn't been changed.
    
- **Certificates:** Combined with signatures to verify an individual's identity.
    
- **Non-Repudiation:** Proof of integrity so a user cannot deny an action.
    

### ⚡ Availability

_Ensures systems/data are accessible to authorized users when needed._

- **Redundancy:** Building services that are always available (multiple servers).
    
- **Fault Tolerance:** Systems continue to run even if a component fails.
    
- **Patching:** Maintaining stability and closing security holes.
    


---

# 🛡️ 1.2 Fundamental Security Concepts

## ✍️ Non-Repudiation

> [!ABSTRACT] Definition **Non-Repudiation** ensures that a subject cannot deny having performed an action. It provides high assurance of both the **origin** and the **integrity** of data.

- **The Concept:** Similar to signing a physical contract. Once your signature is on it, you cannot claim it wasn't you.
    
- **In Practice:** We use **Digital Signatures** to achieve this.
    
- **The "Equation":** Integrity + Authentication = **Non-Repudiation**.
    

---

## 🔢 Cryptographic Foundations

### 1. Hashing (Integrity)

- **What it is:** A mathematical algorithm that represents data as a short, fixed-length string of text (often called a **Message Digest** or **Fingerprint**).
    
- **The Rule:** If the data changes by even one bit, the hash changes completely.
    
- **The Limitation:** A hash proves the data remains accurate and consistent, but it **does not** prove who sent it.
    

### 2. Digital Signatures (Authentication & Integrity)

- **The Process:**
    
    - **Sign with a Private Key:** Only the owner possesses this key; therefore, nobody else can create the signature.
        
    - **Verify with a Public Key:** Anyone can use the public key to verify that the signature is valid.
        
- **The Result:** * If the signature is verified, we have **Authentication** (Proof of Origin).
    
    - If the hash matches, we have **Integrity** (Proof the message wasn't changed).
        

---

## 🏗️ The Zero Trust Philosophy

- **The Strategy:** "Never trust, always verify."
    
- **The Shift:** We no longer assume a user is "safe" just because they are inside the physical building or on the internal network.
    
- **Implementation:** Every request for access is authenticated, authorized, and inspected for anomalies before being granted.
    

---

## 🔍 Gap Analysis

- **Definition:** The process of comparing the **current state** of security against the **target state** (industry standards like NIST, ISO, or company policy).
    
- **The Goal:** Identify what is missing (the "Gap") so the organization can prioritize which controls to implement next.
    

---

### 📂 Attachments
![](../attachments/Pasted%20image%2020260410133936.png)
  ![675](../attachments/Pasted%20image%2020260411055837.png)
![](../attachments/Pasted%20image%2020260411055939.png)

---
# 🔑 1.2 Access Control & AAA Framework

## 📑 The AAA Framework

> [!IMPORTANT] The logical flow of access.
> 
> 1. **Identification:** Who you _claim_ to be (e.g., Username).
>     
> 2. **Authentication:** Proving you are who you claim to be (e.g., Password, Token, Biometrics).
>     
> 3. **Authorization:** What you are _allowed_ to do based on your identity (Permissions).
>     
> 4. **Accounting:** Tracking what you did (Logins, data usage, logout times).
>     

---

## 💻 Device Authentication (Machine-to-Machine)

- **The Problem:** Systems and remote devices can't type passwords, and storing passwords in plain text is a huge security risk.
    
- **The Solution:** **Digitally Signed Certificates.**
    
    - **Trust:** The organization acts as its own **Certificate Authority (CA)**.
        
    - **The Process:** The CA signs a certificate for the device. The device presents this certificate to the network (like a VPN).
        
    - **Validation:** The server checks the CA’s digital signature. If it matches, the device is authenticated.
        

---

## 🛡️ Authorization Models (Managing Access at Scale)

- **Simple Model (User → Resource):** * _Issue:_ Does not scale. If you have 1,000 users, managing individual permissions is a nightmare.
    
- **Abstraction Model (The "Middle Man"):**
    
    - _Process:_ Users are assigned to **Roles** or **Groups** (e.g., "HR Department" or "IT Admin").
        
    - _Benefit:_ Streamlines administration. Instead of changing 50 individual permissions, you just change the permission for the "Role."
        
    - _Scale:_ Supports any number of users or resources efficiently.
        

---

### 📂 Attachments

 ![](../attachments/Pasted%20image%2020260411060403.png)
![](../attachments/Pasted%20image%2020260411060732.png)

---

# 📈 1.2 Gap Analysis & Strategic Planning

## 📋 What is a Gap Analysis?

> [!ABSTRACT] Definition A **Gap Analysis** is the formal process of comparing an organization’s **current security posture** (where we are) against its **target objectives** or a specific baseline (where we want to be).

- **The "Gap":** The space between the current state and the goal.
    
- **Complexity:** This isn't a 5-minute task; it can take weeks or months of emails, technical research, and data gathering.
    

---

## 🛠️ The Process

### 1. Choose a Framework (The Goal)

You don't just "guess" what good security looks like. You use established industry standards:

- **NIST** (National Institute of Standards and Technology)
    
- **ISO** (International Organization for Standardization)
    
- **Internal Baselines:** Specific goals set by company leadership.
    

### 2. Evaluate the "Now" (The Current State)

- **Employees:** What is their current training level? Do they actually know the security policies?
    
- **Processes:** How are things currently done? (e.g., How do we handle password resets?)
    
- **IT Systems:** Research existing hardware, software, and configurations.
    

### 3. The Detailed Comparison

- Break broad categories into smaller, manageable segments (e.g., instead of "Network," look at "Firewall Rules," then "VPN Access").
    
- **Identify:** Highlight weaknesses and recognize what is already working well.
    

### 4. The Path Forward (The Report)

The final report is a roadmap that includes:

- **Recommendations:** Specific steps to close the gap.
    
- **Resources:** Estimates of the **Time** and **Money** required.
    
- **Change Control:** How these changes will be implemented without breaking existing systems.
    

---

## 📂 Attachments

 ![](../attachments/Pasted%20image%2020260411065412.png)
![](../attachments/Pasted%20image%2020260411065509.png)

---

# 🛡️ 1.2 Zero Trust Architecture (ZTA)

## 🌐 The Holistic Approach

> [!QUOTE] The Motto "Implicit trust is a vulnerability. **Never trust, always verify.**"

- **The Shift:** Traditional security focuses on the perimeter (the firewall). Zero Trust focuses on the **assets** (data, people, and devices) regardless of where they are.
    
- **Methods:** Utilizes MFA, mandatory encryption, strict permissions, and internal segmentation.
    

---

## ✈️ Functional Planes

|Plane|Responsibility|Examples|
|---|---|---|
|**Data Plane**|The "Muscle." Handles the actual processing and movement of data.|Forwarding, encrypting, NAT, trunking frames/packets.|
|**Control Plane**|The "Brain." Defines the policies and rules that the Data Plane must follow.|Routing tables, session tables, NAT tables.|


---

## 🚦 Access & Risk Indicators

Zero Trust uses **Adaptive Identity**. Before granting access, it evaluates multiple risk factors:

- **Relationship:** Is this an employee or a contractor?
    
- **Location:** Is the IP address from a known office or an unexpected country?
    
- **Connection:** Is this a managed company laptop or a private phone?
    
- **Threat Scope:** Reducing the number of entry points to minimize the "attack surface."
    

---

## 🏛️ The Zero Trust Architecture Components

When a user (Subject) tries to access a system, they go through two main points:

### 1. PDP (Policy Decision Point)

The "Judge" that decides if you get in. It consists of:

- **Policy Engine:** The brain that evaluates the request against rules and risk factors.
    
- **Policy Administrator:** The component that communicates the final decision.
    

### 2. PEP (Policy Enforcement Point)

The "Gatekeeper" (The Muscle).

- **Action:** It actually allows, monitors, or terminates the connection based on what the PDP decided.
    

---

## 📂 Attachments

 ![](../attachments/Pasted%20image%2020260411070723.png)
![](../attachments/Pasted%20image%2020260411071336.png)

---
# 🛡️1.2 Physical Security Controls

Physical security focuses on the protection of personnel, hardware, and data from physical actions and events. These controls are categorized into **Deterrent**, **Preventive**, and **Detective** measures.

---

### 🚧 Perimeter & Site Defense

- **Bollards & Barricades:** Physical structures (concrete pillars or moats) used to block vehicle-borne attacks.
    
- **Fencing:** Establishes a clear perimeter.
    
    - _Standard:_ 2.4 meters (8ft) to deter climbing.
        
    - _Enhancements:_ Razor wire, anti-climb paint, or robust materials to prevent cutting.
        
- **Lighting:** A fundamental deterrent. Attackers avoid lit areas where they are visible to cameras and guards. Includes specialized IR lighting for night-vision cameras.
    
- **Signage:** Deterrent control (e.g., "No Trespassing" or "CCTV in Operation") to warn potential intruders.
    

### 🚪 Access Control & Entry Management

- **Access Control Vestibule (Mantrap):** A set of two interlocking doors.
    
    - _Failsafe:_ All doors unlocked (e.g., in a fire).
        
    - _Fail-secure:_ All doors locked (e.g., during a breach).
        
    - _Logic:_ Opening one door prevents the other from unlocking, ensuring one-at-a-time entry.
        
- **ID Badges:** Must be worn at all times; used for visual identification and electronic logging via RFID/NFC.
    
- **Physical Guards:** Human security at reception or checkpoints to validate credentials and provide immediate response.
    
- **Two-Person Integrity:** Requirement that two authorized individuals must be present to access a critical asset (prevents insider threats).
    

### 📹 Monitoring & Detection

- **Video Surveillance (CCTV):** Networked cameras used for real-time monitoring and forensic recording.
    
    - _Motion Detection:_ Alerts security when movement is sensed.
        
    - _Object Detection/Recognition:_ Identifies specific items like license plates or facial features.
        
- **Intrusion Detection Sensors:**
    
    - **Infrared (PIR):** Detects heat signatures in light or dark.
        
    - **Pressure Sensors:** Detects weight/force changes (floors/windows).
        
    - **Microwave/Ultrasonic:** Detects motion across large open volumes using signal reflection.

---
# 🍯1.2 Deception Technology

Deception technology involves creating fake environments, files, or data to lure attackers, observe their techniques, and alert security teams to a breach in progress.

---

### 🏛️ The Infrastructure: Honeypots & Honeynets

- **Honeypots:** A single virtual decoy server or system designed to look vulnerable.
    
    - _Purpose:_ To distract attackers from production systems and study their "TTPs" (Tactics, Techniques, and Procedures).
        
    - _Mechanism:_ Usually open-source and easy to deploy; any interaction with it is considered a high-fidelity alert.
        
- **Honeynets:** A larger, complex network of decoys.
    
    - _Components:_ Includes virtual servers, workstations, routers, and firewalls.
        
    - _Project Honeypot:_ A global effort to use networked honeypots to identify and stop spammers/harvesters.
        

### 🍱 The Bait: Honeyfiles & Honeytokens

- **Honeyfiles:** Files that act as "bait" within a network share (e.g., `passwords.txt`, `Payroll_2026.xlsx`).
    
    - _The "Bear Trap":_ These files contain no real data, but an alert is instantly sent to the SOC if they are accessed or moved.
        
- **Honeytokens:** Traceable data used to track malicious actors beyond the network.
    
    - **API Credentials:** Fake keys that don't provide access but alert the owner when an attacker tries to use them.
        
    - **Fake Email Addresses:** Added to contact lists to identify web scrapers or spammers.
        
    - **Database Records:** "Seeded" data that, if found on the Dark Web, proves a specific database was breached.
        
    - **Web Page Pixels:** Invisible tracking pixels used to identify the source of unauthorized site mirroring.
        

---

### 🛡️ Why Use Deception?

1. **Interesting Recon:** Attackers (or automated bots) waste time exploring a "virtual world" while you gather intelligence on them.
    
2. **Early Warning:** Since no legitimate user should be touching a honeyfile, any activity is a 100% confirmed security incident.
    
3. **Evidence Gathering:** Honeynets provide a safe environment to watch how an attacker moves (Lateral Movement) without risking actual company assets.


---

# 📈 1.3 Change Management & Operational Risk

### 📋 The Fundamentals

**Definition:** A formal, documented process for managing technical modifications to avoid downtime, confusion, and catastrophic mistakes.

- **The Reality:** Change is one of the most frequent and common risks in the enterprise.
    
- **The "Bite":** It is often overlooked or ignored until a minor update causes a total system failure.
    
- **The Goal:** To have clear policies regarding frequency, duration, installation processes, and mandatory rollback procedures.
    

---

### 🏛️ The Approval Workflow

|Stage|Action Item|Key Objectives|
|---|---|---|
|**Request**|Formal Documentation|Complete forms defining the **Purpose**, **Scope**, and **Schedule**.|
|**Risk Analysis**|Risk Level Assessment|Assign a value (High/Medium/Low) based on potential impact.|
|**Approval**|**Change Control Board (CCB)**|Get formal sign-off from management and stakeholders.|
|**Implementation**|Technical Execution|Perform the actual change (upgrade, patch, or config shift).|
|**Verification**|End-User Acceptance|Confirm the system works for the people who actually use it.|


---

### 👥 Roles & Responsibilities

- **The Process Owner:** The entity that _needs_ the change (e.g., Shipping & Receiving). They manage the request and ensure the process is followed.
    
- **The Custodian (IT):** The technical team that handles the actual changes (e.g., upgrading label printer software).
    
- **Stakeholders:** Anyone impacted by the change. This can scale from a single user to the entire company (affecting revenue reports and CEO visibility).
    

---

### 🛡️ Risk Mitigation & "The Safety Net"

#### 🧪 Testing in the Sandbox

A **Sandbox** is a technological safe space—a testing environment with zero connection to the real-world production system.

- **The Rule:** Try the upgrade, apply the patch, and confirm success _before_ touching production.
    

#### 🔙 The Backout Plan (Rollback)

Never assume a change will go perfectly. Always prepare for the worst.

- **Reversion:** Have a predefined way to move everything back to the original state.
    
- **The Backup:** **Always have verified backups.** This is the ultimate safety net.
    
- _Note:_ Some changes are incredibly difficult to revert; the backout plan must account for this complexity.
    

---

### 📅 Scheduling & Timing

|Consideration|Strategy|Reason|
|---|---|---|
|**Workday**|Generally avoided.|Minimizes impact on active production and employee output.|
|**Overnights**|Preferred choice.|Ideal for systems that aren't 24/7, though challenging for global ops.|
|**Change Freeze**|Retail/Financial "Blackouts."|Networks are "frozen" during peak times (e.g., holidays) to ensure 100% stability.|

---

# ⚙️ 1.4 Change Execution & Technical Implementation

### 📋 Moving from Plan to Action

**Definition:** The technical phase of change management where upgrades, patches, and configurations are deployed into the production environment.

- **No "Simple" Upgrades:** Every change has moving parts; what looks like one event may actually require several coordinated steps.
    
- **The Conflict:** Change Management focuses on **What** changes; the Technical Team (you) focuses on **How** it changes.
    
- **The Risks:** Every new application is a potential vector for vulnerabilities, Trojan horses, or malware.
    

---

### 🛡️ Application Control & Execution

|Strategy|Mechanism|Security Posture|
|---|---|---|
|**Allow List**|Nothing runs unless explicitly approved.|**High Security:** Very restrictive; best for high-risk environments.|
|**Deny List**|Only known "bad" files are blocked.|**Standard:** Relies on antivirus/malware signatures to identify threats.|


---

### 🛠️ Execution & Minimizing Disruption

#### 📉 Managing Downtime

- **Disruptive by Nature:** Services will eventually be unavailable; scheduling during **non-production hours** is mandatory.
    
- **Service Redundancy:** If possible, switch traffic to a secondary system, upgrade the primary, then switch back.
    
- **Automation:** The more automated the process, the lower the risk of human error. Automation should also be built into the **Backout Plan**.
    

#### 🔄 The "Restart" Reality

- **Bouncing Services:** It is common to require a restart of the OS, a power cycle of a switch, or a "bounce" of a specific daemon.
    
- **Recovery Check:** Always verify if the system can recover automatically from an unexpected power outage after a change.
    
- **State Management:** Closing applications completely and launching new instances to ensure the new configuration is active.
    

---

### 🏛️ Legacy Systems & Dependencies

> [!WARNING] **Legacy Systems:** Some applications were here before you and will be here after you. If they are no longer supported by the developer, **you** are now the support team.
> 
> - **Action:** Document the "quirks" and create specific procedures. Face the fear of the unknown by becoming the expert.
>     

#### 🔗 Dependency Mapping

- **Sequence Matters:** To complete Step A, you must often complete Step B (e.g., an app requiring a specific library version).
    
- **System Cross-Talk:** Modifying one component (like upgrading firewall code) may require restarting other interconnected systems.
    

---

### 📝 Post-Change Documentation

- **Version Control:** Tracking changes to files or configurations over time. Essential for reverting to a "Last Known Good" state.
    
- **The Living Document:** Diagrams, IP address updates, and network configurations must be updated _immediately_ after the change.
    
- **Policy Alignment:** Ensure that the technical reality of the system still matches the organization’s written security policies.


---

# 🔐 1.3 Cryptography & Public Key Infrastructure (PKI)

### 📋 What is PKI?

**Definition:** The hardware, software, people, policies, and procedures needed to create, manage, distribute, use, store, and revoke digital certificates.

- **The Core Goal:** To bind **Public Keys** to specific people or devices.
    
- **The Trust Factor:** It all centers on the **Certificate Authority (CA)**. If you don't trust the CA, the entire system fails.
    
- **The Scale:** This is a "big, big endeavor" that requires massive planning and coordination.
    

---

### 🕹️ Encryption Methods

|Feature|Symmetric Encryption|Asymmetric Encryption|
|---|---|---|
|**Key Count**|One (Shared Secret)|Two (Public & Private)|
|**Speed**|**Very Fast** (Low overhead)|**Slow** (Math heavy)|
|**Scaling**|Difficult (Does not scale well)|Excellent (Anyone can have the Public key)|
|**Primary Use**|Bulk data encryption|Key exchange & Digital Signatures|

---

### 🔑 Asymmetric Cryptography (Public Key)

**Definition:** A system that uses two mathematically related keys. You cannot derive the private key from the public key.

#### 🛠️ How it Works

1. **Key Generation:** Both keys are built at the same time using large prime numbers and heavy randomization.
    
2. **The Public Key:** Give it to everyone. It is used to **encrypt** data.
    
3. **The Private Key:** Keep this a total secret. It is the **only** key that can **decrypt** what the public key encrypted.
    

> [!TIP] **Hybrid Encryption:** In the real world (like HTTPS), we use **Asymmetric** encryption to securely exchange a **Symmetric** key, then use that symmetric key for the actual data transfer because it's faster.

---

### 📂 Key Management & Escrow

#### 💼 Key Escrow (Third-Party Control)

**Definition:** A process where your decryption keys (Private Keys) are held by a third party or a specific entity within your organization.

- **The Business Case:** A company may need to access employee data if they leave, or a government agency may need to decrypt data for legal reasons.
    
- **The Controversy:** It is highly debated in the security community because it creates a single point of failure—if the escrow is breached, all encrypted data is exposed.
    

---
![](../attachments/Pasted%20image%2020260411195922.png)

![697](../attachments/Pasted%20image%2020260411200147.png)

---

# 🔒 1.4 Data States & Encryption Implementation

### 📋 The Three States of Data

|State|Definition|Primary Protection Method|
|---|---|---|
|**Data at Rest**|Data stored on a physical or cloud device.|FDE (Full Disk Encryption), Database encryption.|
|**Data in Transit**|Data moving across a network.|HTTPS, VPNs, TLS/SSL.|
|**Data in Use**|Data currently being processed in RAM/CPU.|Memory encryption (Advanced hardware).|

---

### 🏛️ Protection: Data at Rest

**Goal:** Prevent unauthorized access if a storage device (SSD, USB, Phone) is lost or stolen.

#### 🏗️ Storage Encryption Types

- **Full Disk Encryption (FDE):** Encrypts the entire drive or partition.
    
    - _Examples:_ **BitLocker** (Windows), **FileVault** (macOS).
        
- **File/Folder Encryption:** Encrypts specific files or directories.
    
    - _Examples:_ **EFS** (Encrypting File System), 7-Zip/AES-256 archives.
        
- **Database Encryption:**
    
    - **Transparent Encryption:** Encrypts the entire database file with a symmetric key.
        
    - **Record-Level Encryption:** High-granularity protection; encrypts specific columns (e.g., just the "Credit Card Number" column).

![](../attachments/Pasted%20image%2020260411200813.png)

![](../attachments/Pasted%20image%2020260411200841.png)

---

### 🌐 Protection: Data in Transit

**Goal:** Prevent "Man-in-the-Middle" (MITM) attacks while data traverses the internet.

- **Application Level:** Encrypting specifically for one app.
    
    - _Example:_ **HTTPS** (Browser communicating with a web server).
        
- **Network Level:** Encrypting all traffic regardless of the app.
    
    - **Client-to-Site VPN:** Uses SSL/TLS to protect a remote worker.
        
    - **Site-to-Site VPN:** Uses **IPsec** to bridge two entire offices securely.
        

---

### 🔑 The "Strength" of Cryptography

> [!IMPORTANT] **Kerckhoffs's Principle:** The algorithm should not be secret; it’s expected to be a known entity. The **only** thing that must remain secret is the **Key**.

#### 🛠️ Key Metrics

|Feature|Symmetric|Asymmetric|
|---|---|---|
|**Common Key Size**|128-bit or larger.|2048-bit or larger.|
|**Brute Force Defense**|Larger keys = harder to crack.|Larger keys = much more math overhead.|

#### 💪 Key Stretching

If a key is "weak" (like a simple password), you can make it stronger using **Key Stretching**.

- **The Process:** Hash the password, then hash that hash—repeat this thousands of times.
    
- **The Impact:** It forces a brute-force attacker to reverse every single hash iteration, making the attack mathematically impossible for them.

---

# 🤝 1.4 Key Exchange & Session Security

### 📋 The Logistical Challenge

**The Problem:** How do you share a secret key with someone across the insecure internet without an attacker intercepting it?

- **The Goal:** Fast, secure communication without the overhead of permanent asymmetric encryption.
    

---

### 🏛️ Key Exchange Methodologies

|Method|Description|Pros/Cons|
|---|---|---|
|**Out-of-Band**|Transferring the key outside the network (Telephone, Courier, In-person).|**Pros:** Very secure. **Cons:** Doesn't scale; slow.|
|**In-Band**|Transferring the key over the existing network.|**Pros:** Instant. **Cons:** Requires additional encryption to protect the key during transit.|


---

### 🔑 The Hybrid Solution: Session Keys

**Definition:** A temporary symmetric key used for a single communication session. It combines the **Security** of Asymmetric encryption with the **Speed** of Symmetric encryption.

#### 🔄 The Implementation Flow

1. **Asymmetric Protection:** The client creates a random **Symmetric Key**.
    
2. **The Delivery:** The client encrypts that random key using the **Server’s Public Key**.
    
3. **The Handshake:** Only the server can decrypt it (using its Private Key).
    
4. **The Session:** Both sides now have the same symmetric "Session Key" and use it for the rest of the conversation.
    

> [!IMPORTANT] **Best Practices:**
> 
> - **Change Often:** Session keys should be short-lived.
>     
> - **Unpredictable:** Use high-quality randomization (large prime numbers) to prevent attackers from guessing the key.

---
![](../attachments/Pasted%20image%2020260411213725.png)
![](../attachments/Pasted%20image%2020260411213817.png)

---

# 🛡️ 1.4 Hardware Security & Key Management

### 🏗️ Trusted Platform Module (TPM)

**Definition:** A dedicated specification for cryptographic functions integrated directly into a device's hardware.

- **Cryptographic Processor:** Includes a hardware-based Random Number Generator (RNG) and Key Generator.
    
- **Persistent Memory:** Contains unique keys (like the Endorsement Key) "burned in" during manufacturing.
    
- **Versatile Memory:** Securely stores storage keys, hardware configuration information, and hashes to ensure system integrity.
    
- **Practical Use:** This is what **BitLocker** uses to store encryption keys securely; it is often password or PIN protected to prevent unauthorized access.
    

---

### 💳 Hardware Security Module (HSM)

**Definition:** High-end, standalone cryptographic hardware used in large-scale enterprise environments.

- **Physical Form:** Can be a plug-in PCIe card, a separate network-attached device, or a cluster.
    
- **Key Features:**
    
    - **Key Backup:** Provides secure, physical storage for thousands of cryptographic keys.
        
    - **Cryptographic Accelerators:** Offloads heavy encryption math from the main CPU to dedicated hardware.
        
    - **Redundancy:** Used in clusters with redundant power to ensure high availability in data centers.
        

---

### ☁️ Key Management Systems (KMS)

**Definition:** A centralized console used to manage the lifecycle of keys across on-premises and cloud-based services.

- **Centralized Control:** Manage keys for many different services (AWS, Azure, Google Cloud) from a single third-party software console.
    
- **Operational Features:**
    
    - **Creation:** Generate keys for specific cloud providers or services.
        
    - **Association:** Link keys to specific users or roles.
        
    - **Key Rotation:** Automatically rotate keys at regular intervals to minimize the impact of a potential leak.
        
    - **Logging/Auditing:** Records every time a key is used or modified for security compliance.
        

---

### 🔐 Secure Enclaves & Processors

**The Philosophy:** Our most private data is physically closest to us (phones/laptops), but attackers are always evolving. We need a "safe room" inside our hardware.

- **Secure Enclave:** A protected area for secrets implemented as a hardware processor isolated from the main CPU.
    
- **Security Features:**
    
    - **Independent Boot ROM:** Provides its own secure startup process separate from the OS.
        
    - **Boot Monitoring:** Watches the system boot process to ensure no malware has tampered with the kernel.
        
    - **Real-Time Encryption:** Performs AES encryption in hardware and provides real-time memory encryption.
        
    - **Root of Trust:** Holds the root cryptographic keys that are never exposed to the main operating system.

![](../../Pasted%20image%2020260414201127.png)

![](../../Pasted%20image%2020260414201138.png)

![](../../Pasted%20image%2020260414201144.png)

---

# 🕵️‍♂️ 1.4 Obfuscation, Steganography, & Tokenization

### 🌫️ Obfuscation

**Definition:** The process of making something unclear or difficult to understand. While it is not impossible to reverse, it hides the logic or intent from a casual observer.

- **Data Masking:** Hiding some of the original data (e.g., showing only the last four digits of a credit card).
    
- **Dynamic Masking:** The data remains intact in storage, but the "view" is controlled based on user permissions.
    
- **Techniques:** Substituting characters, shuffling data, or using simple encryption to scramble code.
    

---

### 🖼️ Steganography

**Definition:** Derived from the Greek for "concealed writing." It is the art of hiding information in plain sight (Security through Obscurity).

- **The Methodology:**
    
    - **Covertext:** The container document or file used to hide the secret.
        
    - **The Secret:** The message is invisible to the naked eye but easily extracted with the right tool.
        
- **Common Use Cases:**
    
    - **Image-based:** Embedding text or files within the pixels of an image.
        
    - **Audio:** Interlacing a secret message within a digital audio file.
        
    - **Network-based:** Embedding hidden messages within TCP/IP packet headers.
        
    - **Invisible Watermarks:** Famous examples include the "yellow dots" printed by laser printers to track documents.
        

---

### 🎫 Tokenization

**Definition:** Replacing sensitive data with a non-sensitive placeholder called a "Token."

- **Key Characteristic:** Unlike encryption or hashing, the token and the original data are **not mathematically related**.
    
- **The Process:**
    
    - A sensitive value (e.g., SSN `226-12-1112`) is swapped for a random string (`691-61-8539`).
        
    - The actual data is stored in a secure centralized vault.
        
- **Why it’s used:** Primarily in **Credit Card Processing**. If an attacker captures the token, it is useless to them because they cannot "decrypt" it to get the card number.
    

---

### ⚖️ Quick Comparison for the Exam

|Feature|Encryption|Steganography|Tokenization|
|---|---|---|---|
|**Logic**|Mathematical scramble|Hiding in plain sight|Random placeholder|
|**Visibility**|Obvious (Ciphertext)|Invisible (Hidden)|Visible but useless|
|**Relation**|Related by Key|Related by Container|Not mathematically related|
![](../../Pasted%20image%2020260414202427.png)

---

# 🛡️ 1.4 Hashing, Salting, & Digital Signatures

### 🔢 Hash Functions

**Definition:** A cryptographic function that takes an input of any size and creates a fixed-size string of text, known as a **Message Digest**, **Checksum**, or **Fingerprint**.

- **The "One-Way" Trip:** Hashing is a one-way process; it is computationally impossible to recover the original message from the digest.
    
- **Integrity Verification:** Used to verify that a downloaded document or file is identical to the original.
    
- **Fixed Output:** Regardless of the input size (a single word or a whole movie), the output is always the same length.
    
    - **SHA-256:** A common standard that produces a 256-bit hash (64 hexadecimal characters).
        
- **Collisions:** A "collision" occurs when two different inputs produce the same hash.
    
    - **MD5 Warning:** MD5 was found to have collision vulnerabilities in 1996. **Do not use MD5** for security-sensitive tasks.
        

---

### 🧂 Password Salting

**Definition:** Adding random data (a "salt") to a password before it is hashed to prevent pre-computed attacks.

- **How it works:**
    
    - Every user is assigned a unique, random salt.
        
    - The salt is stored alongside the hash in the database.
        
    - **Password + Salt = Unique Hash.**
        
- **The Benefit:** * **Anti-Rainbow Table:** Even if two users have the same password ("Password123"), their hashes will look completely different due to the unique salts.
    
    - **Slowing Down Brute Force:** It adds complexity to the reverse-engineering process, forcing attackers to crack passwords one by one rather than all at once.
        

---

### ✍️ Digital Signatures

**Definition:** A cryptographic process used to provide **Integrity**, **Authentication**, and **Non-Repudiation**.

- **The Process:**
    
    1. **Signing:** The sender signs a hash of the message using their **Private Key**. (The message itself does not have to be encrypted).
        
    2. **Verifying:** The recipient uses the sender's **Public Key** to verify the signature.
        
- **The Guarantees:**
    
    - **Integrity:** If even one bit of the message changes, the signature becomes invalid.
        
    - **Authentication:** Since only the sender has their private key, only they could have created the signature.
        
    - **Non-Repudiation:** The sender cannot later deny sending the message because the signature is unique to their private key.
        

---

### 💡 Quick Comparison for the Exam

| Feature          | Hashing               | Digital Signature                      |
| ---------------- | --------------------- | -------------------------------------- |
| **Primary Goal** | Integrity             | Integrity + Authentication             |
| **Reversible?**  | No                    | No                                     |
| **Key Used**     | None (Algorithm only) | Private Key to Sign / Public to Verify |
| **Analogy**      | A tamper-evident seal | A wax seal with a unique signet ring   |

![](../../Pasted%20image%2020260414202851.png)

![](../../Pasted%20image%2020260414203023.png)

![](../../Pasted%20image%2020260414203054.png)

![](../../Pasted%20image%2020260414203330.png)

![](../../Pasted%20image%2020260414203617.png)

![](../../Pasted%20image%2020260414203717.png)

---

# 🔗 1.4 Blockchain & Distributed Ledgers

### 📖 The Distributed Ledger

**Definition:** A decentralized database that tracks transactions across a network of computers. Instead of one central bank or company holding the "master" list, every participant has a copy.

- **Consensus & Replication:** Everyone on the blockchain network maintains and replicates the ledger.
    
- **Immutability:** Once a transaction is recorded and verified by the network, it is nearly impossible to change. This provides a high level of **Integrity**.
    
- **Transparency:** All participants can see the transaction history, which builds trust without needing a central middleman.
    

---

### 🛠️ Practical Applications in Security

Blockchain isn't just for cryptocurrency; it has major enterprise security uses:

- **Payment Processing:** Secure, peer-to-peer financial transactions that don't rely on a single point of failure (like a central server).
    
- **Digital Identification:** Providing a secure, tamper-proof way to verify identities (Authentication) without a centralized ID database that could be hacked.
    
- **Supply Chain Monitoring:** Tracking the "provenance" (origin) of hardware or software. This ensures that the server or code you bought wasn't tampered with by a third party before it reached you.

![](../../Pasted%20image%2020260414204606.png)

![](../../Pasted%20image%2020260414204616.png)

![](../../Pasted%20image%2020260414204632.png)

![](../../Pasted%20image%2020260414204643.png)

![](../../Pasted%20image%2020260414204650.png)

![](../../Pasted%20image%2020260414204659.png)

---

# 📜 1.4 Public Key Infrastructure (PKI)

### 🏗️ The Foundation of Trust

**Trust** is the foundational characteristic of IT security. In PKI, we build trust for unknown entities (like a random website) by using a **Trusted Third Party**.

- **Root of Trust:** An inherently trusted component (Hardware like an HSM, or software/firmware) that serves as the starting point for the trust chain.
    
- **Certificate Authority (CA):** The entity responsible for vetting requests and digitally signing certificates.
    
    - **Public CAs:** Browsers come pre-loaded with these (e.g., DigiCert, Let's Encrypt). If the CA signs a site, your browser trusts it automatically.
        
    - **Vetting:** The CA confirms the identity of the requester before signing.
        

---

### 🛠️ The Lifecycle of a Certificate

1. **Key Generation:** You create a **Public/Private Key Pair**.
    
2. **CSR (Certificate Signing Request):** You send your **Public Key** and identity details to a CA to be signed.
    
3. **Issuance:** The CA signs the request and sends back a **Digital Certificate** (X.509 standard).
    
4. **Binding:** The certificate binds your public key to your identity via the CA's digital signature.
    

---

### 🏢 Internal vs. Public CAs

- **Public CAs:** Used for public-facing websites. You purchase "trust" so that the general public's browsers recognize you.
    
- **Private/Internal CAs:** Built in-house (e.g., Windows Certificate Services).
    
    - **Use Case:** Best for medium-to-large organizations for internal web servers or VPNs.
        
    - **Benefit:** No cost per certificate. You simply install your **Internal Root CA Certificate** on all company devices, and they will trust any cert you sign.
        

---

### 🏷️ Certificate Types & Extensions

- **SAN (Subject Alternative Name):** An extension to the X.509 cert that allows one certificate to support multiple different domains (e.g., `google.com` and `youtube.com`).
    
- **Wildcard Certificates:** Uses an asterisk (e.g., `*.mahdilabs.com`) to protect the main domain and **all** its subdomains (like `mail.mahdilabs.com` or `dev.mahdilabs.com`).
    

---

### 🚫 Revocation: When Trust is Broken

If a private key is compromised (like during the **2014 Heartbleed** flaw), the certificate must be canceled before it expires.

|Method|Description|Pros/Cons|
|---|---|---|
|**CRL (Cert. Revocation List)**|A large file maintained by the CA listing all revoked serial numbers.|**Cons:** Can become very large; requires the client to download the whole list.|
|**OCSP (Online Cert. Status Protocol)**|A real-time check where the browser asks the CA responder if a specific cert is valid via HTTP.|**Cons:** Doesn't scale well if millions of people ask the CA at once.|
|**OCSP Stapling**|The certificate holder (the web server) gets the status from the CA and "staples" it into the SSL/TLS handshake.|**Pros:** Fast and scalable. The status is digitally signed by the CA, so the server can't lie.|
![](../../Pasted%20image%2020260414205140.png)

![](../../Pasted%20image%2020260414205545.png)

![](../../Pasted%20image%2020260414205904.png)

![](../../Pasted%20image%2020260414210058.png)

