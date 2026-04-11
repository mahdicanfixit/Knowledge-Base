---
github_repo: mahdicanfixit| compTIA-security-notes
github_issue: 1
---
# 🛡️ 1.1 Security Controls & CIA Triad i think this is working now

## 🏗️ Control Categories (How they are implemented)

| Category        | Description                                             | Examples                                          |
| --------------- | ------------------------------------------------------- | ------------------------------------------------- |
| **Technical**   | Controls implemented using systems (hardware/software). | Firewalls, Antivirus, OS hardening, Encryption.   |
| **Managerial**  | Administrative controls focused on design and policy.   | Security policies, standard operating procedures. |
| **Operational** | Controls implemented by _people_ rather than systems.   | Security guards, awareness training, log reviews. |
| **Physical**    | Controls that limit physical access to assets.          | Fences, locks, badge readers, guard shacks.       |

Export to Sheets

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

![[Pasted image 20260410112953.png]]

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

![[Pasted image 20260410133936.png]] ![[Pasted image 20260411055837.png]] ![[Pasted image 20260411055939.png]]

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

![[Pasted image 20260411060403.png]] ![[Pasted image 20260411060732.png]]

---

Nice work! You just hit the "Business of Security" side. While the Google Cert focused on how to fix a technical problem, **Gap Analysis** is how you fix a _company_.

In an IT Support or Helpdesk role, you’ll often be the person helping gather the data for these reports (e.g., "How many of our laptops are actually encrypted?").

Here is the polished version for your Obsidian vault.

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

![[Pasted image 20260411065412.png]] ![[Pasted image 20260411065509.png]]

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

Export to Sheets

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

![[Pasted image 20260411070723.png]] ![[Pasted image 20260411071336.png]]

---

