
# 🛡️ Threat Actor Profiles (Domain 2.0)

> [!ABSTRACT] Definition An entity responsible for an event that impacts the safety of another entity. Also known as a **Malicious Actor**.

---

## 🔍 Threat Actor Attributes

To categorize why an attack is happening, we evaluate these core characteristics:

- **Relationship**: `Internal` (The house) vs. `External` (Outside trying to get in).
    
- **Motivation**: What makes them tick? (Money, philosophy, revenge, or war).
    
- **Resources**: Funding levels ranging from `None` to `Extensive`.
    
- **Sophistication**: Capability from `Script Kiddie` (automated) to `APT` (custom).
    

---

## 🎭 The Actor Registry

### 🏛️ Nation-State / APT

- **Motivation**: National security, espionage, or strategic disruption.
    
- **Resources**: Massive funding and military-grade control.
    
- **Sophistication**: Highest (Advanced Persistent Threats).
    
- **Example**: `Stuxnet` (Destroyed 1,000 nuclear centrifuges).
    

### 💼 Organized Crime

- **Motivation**: Almost always **Money**.
    
- **Resources**: High capital; structured like a business (Hacking, Management, Support).
    
- **Sophistication**: The best hacking tools money can buy.
    

### 📢 Hacktivist

- **Motivation**: Philosophy, revenge, or social/political change.
    
- **Resources**: Often limited, but can be crowd-funded/hired.
    
- **Sophistication**: Can be remarkably specific (DoS, private document releases).
    

### 🐍 Insider Threat

- **Motivation**: Revenge or financial gain.
    
- **Resources**: Uses the organization's own tools against itself.
    
- **Attributes**: An internal entity "eating away from the inside."
    

### 👶 Script Kiddie

- **Motivation**: The "hunt" or notoriety.
    
- **Sophistication**: Low; blindly runs premade scripts without understanding the "how."
    
- **Resources**: No funding; limited knowledge.
    

### ☁️ Shadow IT

- **Motivation**: Innovation or working around IT "roadblocks."
    
- **Resources**: Limited to department/company budgets.
    
- **Risk**: Creates rogue infrastructure (unauthorized cloud use).
    

---

## 📊 Mapping Capability vs. Intent

![](../../Pasted%20image%2020260414214336.png)
![](../../Pasted%20image%2020260414214959.png)

---

# 🏹 2.1 Attack Vectors & Threat Surfaces

> **Definition:** The specific path or method used by an attacker to gain access to or infect a target. Securing these is the core mission of an IT Security Professional.

---

### 📧 Messaging & Social Engineering

_Most successful vector because it targets the "human" element._

- **Phishing:** The "universal" vector (Email, SMS/Smishing, IM).
    
- **Vishing:** Voice phishing (Phone calls).
    
- **SPIT:** Spam over IP (Large-scale automated voice calls).
    
- **Social Engineering:** Invoice scams, crypto scams, and "urgent" requests.
    
- **Payload Delivery:** Attaching malware directly to emails.

> [!TIP] Prevention Always scan attachments and never launch untrusted links.
    

---

### 🖼️ Non-Text & File-Based Threats

_Attackers hide code in formats you wouldn't expect._

- **SVG Images:** Described in **XML**. This allows for HTML injection or JavaScript attacks directly within an "image" file.
    
- **Adobe PDF:** Not just a document; it contains objects that can execute malicious code.
    
- **Archive Files:** `.zip` or `.rar` files used to bypass scanners by compressing/encrypting the payload.
    
- **Office Macros:** Malicious scripts hidden in `.docm` or `.xlsm` files.
    

---

### 🔌 Physical & Hardware Vectors

_Bypassing the firewall by walking through the front door._

- **USB Flash Drives:** Can infect "Air-Gapped" networks (industrial/high-security).
    
- **HID Attacks:** USB devices acting as keyboards ("Hacker on a chip").
    
- **Data Exfiltration:** Walking out with terabytes of data on a thumb drive—zero network bandwidth used.
    
- **War Dialing:** Scanning phone numbers to find open modems (it still happens!).
    

---

### 💻 Client vs. Server Vulnerabilities

- **Client-Based:** Infected executables on a user's machine. Requires constant updates/patches.
    
- **Agentless:** No install needed. Compromising software on the server affects all users (the client runs a new instance each time).
    
- **Unsupported Systems:** Legacy OS (Windows 7/XP) where the manufacturer no longer provides security fixes.
    

---

### 🌐 Network & Port Surface

_Every open connection is a potential door._

- **Wireless:** Outdated protocols (WEP, WPA) or "Rogue" APs.
    
- **Wired:** No `802.1X` authentication.
    
- **Bluetooth:** Reconnaissance and implementation bugs.
    
- **Open Ports:** Every TCP/UDP port is an opportunity.
> [!CAUTION] Attack Surface More services = Larger attack surface. Every open port must be justified in the firewall rules.
    

---

### 🔑 Authentication & Defaults

- **Default Credentials:** Most devices ship with `admin/admin`.
    
- **Resource:** [routerpasswords.com](https://www.routerpasswords.com) — Attacker's first stop.
    
- **Privilege Escalation:** Gaining administrator/root access for full control.
    

---

### 🏭 Supply Chain & Infrastructure

_Tampering with the underlying manufacturing or management process._

- **MSP (Managed Service Providers):** A "gold mine" for attackers. Access one MSP, gain access to _all_ their customers.
    
- **Vendors:** Using third-party access (e.g., the **2013 Target Breach** via an HVAC vendor).
    
- **Counterfeit Hardware:** Fake Cisco switches or hardware with pre-installed backdoors (**2020 Fake Cisco Incident**).
    

---

### 📊 Attack Vector Comparison Table

|Vector Type|Target|Difficulty to Detect|Key Example|
|---|---|---|---|
|**Phishing**|Human|Medium|Invoice Scams|
|**USB/HID**|Physical|High|Stuxnet / Air-Gap|
|**SVG/XML**|Browser|High|JS Injection|
|**Supply Chain**|Hardware|Extreme|Counterfeit Switches|
|**Default Creds**|Admin UI|Low|`admin:password12`|


![](../../Pasted%20image%2020260414215809.png)

![](../../Pasted%20image%2020260414215952.png)

---
This is a solid deep dive into the **"Digital Sleight of Hand"** that makes social engineering so dangerous. Since you're building this for your portfolio, I’ve refined these notes into a clean, "GitHub-style" reference.

I’ve highlighted the **Typosquatting** and **Pretexting** sections, as those are frequent "gotchas" in cybersecurity exams and real-world audits.

---

# 🎭 Social Engineering & Identity Deception

> [!WARNING] The Human Firewall Social engineering bypasses technical controls by exploiting human trust. When combined with **spoofing**, it becomes one of the most effective attack vectors in existence.

---

### 🎣 Phishing Variations

Attackers use "variations on a theme" to reach targets wherever they are most vulnerable.

- **Phishing:** General email-based attacks.
    
- **Smishing:** SMS (Text) based. High success rate due to the personal nature of mobile devices.
    
- **Vishing:** Voice/Voicemail. Often uses **Caller ID Spoofing** to appear as a local bank or government agency.
    

---

### 🎭 Deception Techniques

#### 1. Spoofing & Slight of Hand

The goal is to make a fake source look legitimate.

- **Email Spoofing:** Changing the "From" header to look like a trusted source (e.g., `professor@professormessor.com` instead of the legitimate `messer`).
    
- **Financial Fraud:** Modifying wire transfer details or bank info via spoofed emails to redirect payments.
    
- **Visual Cues:** Look for "not quite right" elements:
    
    - Non-standard **Fonts** or low-quality **Graphics**.
        
    - Subtle **Spelling** errors in the body or signature.
        

#### 2. Typosquatting (URL Hijacking)

Attackers register domains that are common misspellings of popular sites.

- **Example:** `professormessor.com` vs. `professormesser.com`.
    
- **Goal:** Catch users who make a typo in the browser or fail to inspect a link before clicking.
    

#### 3. Pretexting

The attacker doesn't just ask for info; they **create a character** and a situation.

- **The Hook:** "Hi, I'm calling from Visa regarding an automated payment to your utility service..."
    
- **The Goal:** Build a "pretext" that makes the request for sensitive info (SSN, Verification codes) seem logical and urgent.
    

---

### 🚩 Red Flag Checklist

| Feature     | What to Look For                                                       |
| ----------- | ---------------------------------------------------------------------- |
| **URL**     | Is it `https`? Is the domain name spelled _exactly_ right?             |
| **Source**  | Does the email address match the organization's official domain?       |
| **Urgency** | Does it demand immediate action (e.g., "Account suspended in 1 hour")? |
| **Request** | Are they asking for a verification code, password, or wire transfer?   |
![](../../Pasted%20image%2020260414222137.png)
![](../../Pasted%20image%2020260414222301.png)

---

