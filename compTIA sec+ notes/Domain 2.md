
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

![](../attachments/Pasted%20image%2020260414214336.png)
![](../attachments/Pasted%20image%2020260414214959.png)

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


![](../attachments/Pasted%20image%2020260414215809.png)

![](../attachments/Pasted%20image%2020260414215952.png)

---
This is a solid deep dive into the **"Digital Sleight of Hand"** that makes social engineering so dangerous. Since you're building this for your portfolio, I’ve refined these notes into a clean, "GitHub-style" reference.

I’ve highlighted the **Typosquatting** and **Pretexting** sections, as those are frequent "gotchas" in cybersecurity exams and real-world audits.

---

# 🎭 2.2 Social Engineering & Identity Deception

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
![](../attachments/Pasted%20image%2020260414222137.png)
![](../attachments/Pasted%20image%2020260414222301.png)

---

This is a classic breakdown of the **Psychological Principles** of social engineering. Since you're building this for your portfolio, I’ve organized these into a "Human Hacking" reference guide.

I’ve included a **Mermaid mindmap**—it looks great in Obsidian and adds that "professional architect" feel to your GitHub repo.

---

# 🧠 2.2 Social Engineering: The Psychological Playbook

> [!IMPORTANT] Social engineering is "Halloween for fraudsters." It is the art of **Pretexting**—creating a fake story (the "trap") to bypass a person's natural defenses.

---

### 🎭 The Roles Attackers Play

Before the attack, the "actor" chooses a character based on the goal:

- **The Authority Figure:** 👔 "I'm calling from the **Office of the Vice President**." People are conditioned to comply with high-ranking titles without questioning.
    
- **The Technical Expert:** ⚙️ Throwing around technical jargon to confuse the victim. "We've detected a `0x8004210B` synchronization error in your registry."
    
- **The "Helpful" Peer:** 🤝 "Hi, I'm Wendy from Microsoft. We found a problem with your PC and I'm here to help."
    
- **The Buddy:** ⚾ "How about those Cubs? Anyway, I forgot my badge, could you let me in?" (Building **Rapport**).
    

---

### 🛡️ Identity Fraud: The Aftermath

When "hacking the human" succeeds, your personal data becomes a tool for further crime:

|Type|Impact|
|---|---|
|**Credit Card Fraud** 💳|Opening new lines of credit or making unauthorized charges.|
|**Bank Fraud** 🏦|Gaining access to existing accounts or draining funds.|
|**Loan/Lease Fraud** 🏠|Taking out long-term debt or renting property in your name.|
|**Government Benefits** 🏛️|Claiming tax refunds or social security benefits on your behalf.|

Export to Sheets

---

### 🛠️ Defense & Verification (The "Zero Trust" Mindset)

The victim often doesn't realize they are being attacked until it's too late. To prevent this:

1. **Never Volunteer Information:** Keep personal details "Need to Know" only.
    
2. **Verify Through 3rd Parties:** If "Microsoft" calls you, hang up and call a verified number from their official website.
    
3. **Encourage Verification:** In a professional IT environment, making people "double-check" should be rewarded, not punished.
    

---

### 🗺️ Social Engineering Mindmap

Code snippet

```
mindmap
  root((Social Engineering))
    Psychological Principles
      Authority
      Intimidation
      Consensus/Social Proof
      Scarcity
      Urgency
      Familiarity/Trust
    Techniques
      Pretexting
      Phishing/Vishing
      Shoulder Surfing
      Dumpster Diving
    Prevention
      Security Awareness Training
      MFA
      Verification Procedures
```

---

This is a classic scenario in cybersecurity: when the front door is locked and the windows are barred, the attacker doesn't try to break in—they wait for you to come to them.

This is the **Watering Hole Attack**. It bypasses your "perfect" perimeter by poisoning a third-party site you already trust. Since you're building out your **Obsidian** vault, this is a great case study for **Defense in Depth**.

---

# 🦁 2.2 The Watering Hole Attack

> [!ABSTRACT] Logic If the "prey" (the target organization) is too secure to attack directly, the "predator" (attacker) poisons the place where the prey goes to "drink" (trusted industry websites).

---

### 🕵️ The 3-Step Strategy

1. **Reconnaissance:** The attacker observes the group's habits. Which industry forums, regulatory sites, or local news pages do they visit daily?
    
2. **Infection:** The attacker finds a vulnerability in that third-party site (e.g., via **SQL Injection** or **Cross-Site Scripting**) and injects malicious **JavaScript**.
    
3. **The Trap:** The site now serves malware, but often _only_ to the intended victims. The script checks the visitor's **IP Address**—if it matches the target bank or agency, the payload drops. Everyone else sees a perfectly normal website.
    

---

### 📂 Case Study: January 2017 Financial Attacks

This was a highly sophisticated campaign linked to the **Lazarus Group**.

- **The Target:** Banking sectors in Poland, Mexico, and Uruguay.
    
- **The Method:** The attackers compromised the **Polish Financial Supervision Authority (KNF)** website.
    
- **The Precision:** The malicious code was configured to only trigger for specific IP ranges belonging to 100+ financial institutions across 31 countries.
    
- **The Result:** Because it was a "trusted" government site, it bypassed many standard web filters.
    

---

### 🛡️ Layered Defense (Defense in Depth)

As you noted, "it's never just one thing." You need layers so that if one fails, the next catches the threat.

|Layer|Defensive Control|Role|
|---|---|---|
|**Network**|**Firewall / IPS**|Blocks traffic to known Command & Control (C2) servers.|
|**Endpoint**|**EDR / Anti-Malware**|Catches the "Drive-by Download" if the code executes.|
|**Application**|**Browser Patching**|Prevents the JavaScript from exploiting a browser vulnerability.|
|**Architecture**|**Zero Trust**|Assumes the network is already breached; requires verification for every move.|
|**Human**|**Awareness Training**|Teaching users to report weird browser behavior or "certificate errors."|

Export to Sheets

---

### 📊 Quick Comparison: Phishing vs. Watering Hole

|Feature|Phishing 🎣|Watering Hole 🦁|
|---|---|---|
|**Delivery**|Push (Email/SMS sent to you)|Pull (You go to the source)|
|**Trust Factor**|Low (Suspicious links)|High (Trusted legitimate site)|
|**Visibility**|High (Email can be scanned)|Low (Injected into clean code)|

---

# 🗣️2.2 Information Warfare & Brand Deception

> [!IMPORTANT] While **Misinformation** is a broader term for false info, **Disinformation** is the _intentional_ dissemination of factually incorrect data to create confusion and division.

---

### 🗳️ Influence Campaigns & Disinformation

Nation-state actors use these to divide, distract, and persuade the public on social and political issues.

- **The Goal:** Sway public opinion or delegitimize institutions.
    
- **The Mechanism:** * **Social Media Amplification:** Using bots and "troll farms" to create, share, and like content.
    
    - **The Echo Chamber:** Algorithms show users what they already believe, making the disinformation feel like "consensus."
        
    - **Paid Advertising:** Purchasing ads to micro-target specific demographics with tailored narratives.
        

---

### 🥤 Brand Impersonation (The "Big Brand" Trap)

Attackers leverage the trust you have in household names (Coca-Cola, McDonald's, etc.) to deliver payloads.

- **Massive Scale:** Creating tens of thousands of impersonated sites simultaneously.
    
- **SEO Poisoning:** Getting these fake sites into the **Google Index** so they appear in top search results.
    
- **Malicious Advertising (Malvertising):**
    
    1. Attacker buys a legitimate ad slot.
        
    2. User clicks the ad (or just visits a site where the ad loads).
        
    3. A **Pop-up** appears (e.g., "You won a prize!" or "Security Warning").
        
    4. Clicking the pop-up leads to an **almost guaranteed malware infection**.
        

---

### 🛡️ Detection & Prevention

|Threat|Defense Strategy|
|---|---|
|**Disinformation**|**Fact-Checking** 🔎: Verify sources through multiple independent outlets.|
|**Brand Impersonation**|**URL Inspection** 🔗: Check for typos or strange TLDs (e.g., `.cc` instead of `.com`).|
|**Malvertising**|**Ad-Blockers / DNS Filtering** 🛑: Prevent the malicious script from loading in the first place.|
|**Fake Sites**|**Browser Protection** 🌐: Use tools that flag "Low Reputation" sites.|
![](../attachments/Pasted%20image%2020260414223854.png)

---

# 🧠 2.3 Memory Injection & Evasive Malware

> [!ABSTRACT] The "Fileless" Concept Modern malware often avoids the hard drive entirely to bypass traditional Anti-Virus. By running strictly in **Volatile Memory (RAM)**, it leaves no trace on the disk, making **Memory Forensics** essential for detection.

---

### 🔍 What’s in the Memory?

When you analyze a RAM dump, you are looking at:

- **Running Processes:** Active applications.
    
- **DLLs:** Shared libraries used by multiple programs.
    
- **Threads:** The smallest unit of execution within a process.
    
- **Buffers:** Temporary storage areas (a favorite target for "Overflow" attacks).
    

---

### 💉 Injection Methods

Attackers don't want to start a process named `malware.exe`. Instead, they hide inside "the house" (legitimate processes).

#### 1. Process Injection

The attacker adds their own malicious code into the memory space of a legitimate, running process (like `explorer.exe` or `svchost.exe`).

- **The Goal:** Stealth.
    
- **The Bonus:** The malware inherits the **rights and permissions** of the legitimate process, often leading to **Privilege Escalation**.
    

#### 2. DLL Injection

**Dynamic Link Libraries (DLLs)** are the backbone of Windows applications.

- **The Attack:** The attacker forces a legitimate process to load a malicious DLL by injecting its file path into the process's memory.
    
- **Why it's popular:** It is relatively easy to implement and allows the malware to run as part of a trusted application, bypassing many basic security monitors.
    

---

### 🛡️ Detection & Forensics

Since the code isn't on the disk, we have to find it while it's "alive."

|Tool Type|Function|
|---|---|
|**Memory Forensics**|Tools like `Volatility` or `Rekall` to analyze RAM dumps.|
|**EDR**|Endpoint Detection & Response tools that monitor memory calls in real-time.|
|**Process Explorer**|A Sysinternals tool used to see which DLLs a process has loaded.|

---

# 🏁 2.3 Race Conditions & TOCTOU Attacks

> [!ABSTRACT] The Conundrum A **Race Condition** occurs when a system's behavior depends on the sequence or timing of uncontrollable events. When two things happen at once, and the "wrong" one wins, the system crashes or becomes vulnerable.

---

### ⏳ TOCTOU: Time of Check to Time of Use

This is a specific type of race condition where a program checks a condition (like a password or file permission) and then acts on that result later.

**The Vulnerability:** The "window of opportunity" between the **Check** and the **Use**. If an attacker can change the state of the system during that split second, they can bypass security.

1. **Check:** Is this user allowed to write to `file.txt`? (System says: _Yes_)
    
2. **The Gap:** Attacker quickly replaces `file.txt` with a symbolic link to `system_config.db`.
    
3. **Use:** System writes data to what it _thinks_ is `file.txt`, but actually overwrites the core database.
    

---

### 📂 Legendary Case Studies

#### 🚀 2004: Mars Rover Spirit (Reboot Loop)

- **The Problem:** A race condition in the rover's flash file system.
    
- **The Glitch:** The software would identify a problem and trigger a reboot. However, the reboot process itself would hit the same file system error before it could clear the "problem" flag.
    
- **The Result:** A constant reboot loop. It took NASA engineers days to bypass the file system and delete the offending files to regain control.
    

#### 🏎️ 2023: Tesla Model 3 (Pwn2Own Vancouver)

- **The Attack:** Security researchers from Synacktiv used a **TOCTOU vulnerability** in the Bluetooth stack of the Tesla infotainment system.
    
- **The Result:** They escalated privileges from a standard user to **Root**.
    
- **The Prize:** They earned a **$100,000** bounty and literally got to keep the Tesla.
    

---

### 🛡️ Prevention Strategies

How do programmers stop "The Race"?

|Strategy|Description|
|---|---|
|**Atomic Operations**|Ensure the "Check" and "Use" happen as a single, uninterruptible action.|
|**Locking / Mutex**|Locking a resource so no other process can touch it until the task is done.|
|**Least Privilege**|Even if a TOCTOU occurs, the process shouldn't have the permissions to do significant damage.|

---

# 🔄 2.3 The Update Paradox: Security vs. Risk

> [!IMPORTANT] Patching is the #1 prevention tool for security professionals, but it introduces a critical dependency: **Trust**. If the update source is compromised, your "security fix" becomes the "infection vector."

---

### 🛡️ Best Practices for Secure Updates

Before clicking "Install," a security professional follows a strict protocol:

1. **The Backup Rule:** Always have a **known-good backup** before updating. If the update breaks the system or contains a bug, you need a way back.
    
2. **Trusted Sources:**
    
    - **Direct Downloads:** Visit the developer’s site directly. Avoid third-party "driver update" sites.
        
    - **Code Signing:** Modern OSs (Windows/macOS) use digital signatures to verify that the app hasn't been tampered with since it left the developer.
        
3. **Automated Updates:** Generally trustworthy for standard apps (browsers, OS) as they use encrypted channels directly to the developer's servers.
    

---

### ⚠️ Supply Chain Attacks: The SolarWinds Incident

The **SolarWinds Orion** attack (2020) changed how the industry views updates.

- **The Breach:** Attackers (APT29/Cozy Bear) didn't attack the customers directly. Instead, they compromised the **SolarWinds build system**.
    
- **The Method:** They injected a backdoor (named `SUNBURST`) into a legitimate, digitally signed update for the Orion software.
    
- **The Impact:** Because the update was "official" and signed by SolarWinds, it was pushed to **18,000 customers**, including:
    
    - U.S. Treasury, State, and Commerce Departments.
        
    - The Pentagon.
        
    - Fortune 500 companies.
        
- **The Lesson:** Even "trusted" updates must be monitored for unusual behavior (e.g., a signed update suddenly making strange network connections).

---

# 🖥️ 2.3 OS Vulnerabilities & Patch Management

> [!QUOTE] The Security Paradox "The vulnerabilities are already in the code; we just haven't found them yet." Securing an OS is a constant race between the defenders patching and the attackers exploiting.

---

### 📅 The Lifecycle of a Patch: "Patch Tuesday"

Microsoft pioneered the concept of **Patch Tuesday** (the second Tuesday of every month) to give IT admins a predictable schedule for updates.

- **The Resource:** [Microsoft Security Response Center (MSRC)](https://msrc.microsoft.com/) — This is your "Source of Truth" for Windows vulnerabilities.
    
- **Monthly vs. Out-of-Band:**
    
    - **Monthly:** Routine security and bug fixes.
        
    - **Out-of-Band (OOB):** Emergency patches released "on demand" for critical **Zero-Day** vulnerabilities that are being actively exploited in the wild.
        

---

### 🛠️ The Administrator's Workflow

In a professional environment (like the helpdesk roles you're targeting), you don't just "click update." You follow a structured process:

1. **Testing (Staging):** Never deploy to the whole network at once. A patch might fix a security hole but break a custom internal app. Test on a small group first.
    
2. **The Reboot Requirement:** Many core OS patches require a system restart to replace files currently in use. This requires coordination to avoid downtime.
    
3. **The Fallback Plan:** If a patch causes a **BSOD (Blue Screen of Death)** or a boot loop, you need a recovery path.
    
    - **Backups:** System images or file-level backups.
        
    - **Restore Points:** Quick snapshots of the Windows Registry and system files.
        

---

### 📊 The Patching "Race"

|Phase|Description|
|---|---|
|**Discovery**|A researcher or attacker finds a vulnerability.|
|**Disclosure**|The developer is notified (Private) or the world finds out (Public).|
|**The Window**|The time between the vulnerability becoming known and a patch being applied.|
|**Remediation**|The patch is deployed, the system reboots, and the hole is closed.|

---

# 💉 2.3 Injection Attacks

### 🔌 The Core Concept: Code Injection

**Definition:** Adding unauthorized code or data into a data stream to change the execution path of an application.

- **The Root Cause:** **Improper Input Validation.** The application trusts the user input too much and fails to sanitize it before processing.
    
- **Variety:** Injection isn't limited to one language; it can target **HTML**, **XML**, **LDAP**, and most commonly, **SQL**.
    

---

### 🗄️ SQL Injection (SQLi)

**Definition:** Inserting malicious SQL statements into entry fields for execution (e.g., to dump the database contents to the attacker).

- **The Methodology:**
    
    - Attackers use characters like the single quote (`'`), dashes (`--`), or keywords like `UNION` and `OR` to break the original SQL command.
        
    - **Example:** In a login field, instead of a username, an attacker enters:
        
        `' OR 1=1 --`
        
    - **The Result:** The database sees the "1=1" (which is always true) and logs the attacker in without a valid password.
        

---

### 🧩 Anatomy of a Vulnerable Request

In your example with **Employee: SMITH**, a normal backend query looks like this: `SELECT * FROM employees WHERE name = 'SMITH';`

**The Attack:** If the attacker inputs `SMITH' OR '1'='1`, the query becomes: `SELECT * FROM employees WHERE name = 'SMITH' OR '1'='1';`

- **Why it works:** Because `'1'='1'` is always true, the database returns **every** record in the table instead of just Smith's.
    

---

### 🛡️ Prevention (The "Pro" Fixes)

To stop this, you don't just "block" characters. You use:

1. **Stored Procedures / Parameterized Queries:** The application treats the input as a "label" only, never as executable code.
    
2. **Input Validation:** Only allow expected characters (e.g., if it's a ZIP code field, only allow numbers).
    
3. **Web Application Firewall (WAF):** Can detect and block common SQLi patterns before they reach the server.

![](../attachments/Pasted%20image%2020260415202350.png)

![](../attachments/Pasted%20image%2020260415202511.png)

---

# 🕵️‍♂️ 2.3 Cross-Site Scripting (XSS)

### 🧩 The Core Concept

**Definition:** A vulnerability where an attacker injects malicious scripts (usually **JavaScript**) into a trusted website. The script then executes in the **victim's browser**, not on the server.

- **The Goal:** Steal session cookies/tokens, hijack accounts, or deface websites.
    
- **The Cause:** The website fails to "sanitize" user input, allowing scripts to be treated as executable code.
    

---

### 📉 1. Reflected XSS (Non-Persistent)

- **The Methodology:** The malicious script is "reflected" off a web application to the victim.
    
- **Common Vector:** A link in an email or chat. The script is hidden inside a URL (e.g., in a search query or tracking ID).
    
- **Example:** A user clicks a link to `trusted-bank.com/search?q=<script>alert('Hacked')</script>`. The site "reflects" that script back, and the browser runs it.
    

---

### 🧱 2. Stored XSS (Persistent)

- **The Methodology:** The attacker "stores" the malicious script directly on the server (e.g., in a blog comment, social media post, or forum signature).
    
- **The Danger:** It is **persistent**. Anyone who views that page will automatically execute the script in their browser.
    
- **The "Viral" Effect:** This can spread exponentially; the script can be designed to post itself to the viewer's profile, infecting their friends as well.
    

---

### 🚗 Case Study: The Subaru Token Flaw (2017)

- **The Vulnerability:** An XSS flaw in the web front-end allowed attackers to execute scripts in other users' sessions.
    
- **The Impact:** Subaru’s authentication tokens **never expired**. Once an attacker used XSS to steal a user's token, they had permanent access to that account.
    
- **The Result:** Attackers could add their own email to the account, track the car’s location, and even unlock the doors or start the engine.
    

---

### 🛡️ Prevention & Defense

- **Input Validation:** Never trust user input. Filter out characters like `< > " ' ( )`.
    
- **Output Encoding:** Ensure that data being pulled from a database is rendered as **plain text**, not as active code.
    
- **Content Security Policy (CSP):** A browser-side security layer that tells the browser which scripts are "safe" to run and blocks unauthorized third-party scripts.
    
- **Update Everything:** Keep browsers patched to close known flaws that XSS might exploit.
    

---

### ⚖️ SQLi vs. XSS (Quick Exam Check)

|Feature|SQL Injection (SQLi)|Cross-Site Scripting (XSS)|
|---|---|---|
|**Target**|The Database (Server)|The User's Browser (Client)|
|**Language**|SQL|JavaScript / HTML|
|**Goal**|Dump data / Bypass logins|Steal cookies / Impersonate users|

---

![](../attachments/Pasted%20image%2020260415202831.png)

![](../attachments/Pasted%20image%2020260415202956.png)

---

# 🔌 2.3 Embedded & Legacy Systems Security

### 🏠 The IoT (Internet of Things) Landscape

**The Problem:** We are surrounded by hardware (light bulbs, thermostats, locks) that lacks a traditional, accessible Operating System.

- **Entry Points:** Because these devices are connected to the network but often overlooked, they are perfect entry points for attackers to gain a foothold.
    
- **Security Shift:** As the landscape grows, security professionals must move from "securing computers" to "securing the environment."
    

---

### 💾 Firmware: The Invisible OS

**Definition:** The specialized software "burned" into the hardware that acts as its operating system.

- **Vendor Dependency:** Security is entirely dependent on the manufacturer. If a vendor doesn't release an update, the hardware remains vulnerable.
    
- **Case Study (Trane Thermostats):** Three vulnerabilities were found in April 2014. It took a full year to patch two of them, and **nearly two years** to patch the third. This highlights the slow response time in the embedded world.
    

---

### ⏳ The Product Lifecycle (EOL vs. EOSL)

Understanding these dates is critical for risk management:

- **End of Life (EOL):** The manufacturer stops **selling** the product. They may still offer support and security patches for a while, but the clock is ticking.
    
- **End of Service Life (EOSL):** The manufacturer stops **supporting** the product entirely.
    
    - **The Danger:** No more security patches. Any new vulnerability found after this date is a "forever day" exploit—it will never be fixed.
        
    - **The Risk:** In many industries, technology remains installed far longer than its EOSL date (e.g., medical devices or industrial controllers).
        

---

### 🏛️ Legacy Systems & Technical Debt

**Definition:** Older OS, applications, or middleware that are no longer modern but are still required for business operations.

- **Risk vs. Return:** You have to weigh the risk of running an unpatched Windows XP machine against the cost of replacing a multi-million dollar piece of lab equipment it controls.
    
- **Compensating Controls:** If you **must** keep a legacy device, you wrap it in extra security:
    
    - **Isolation:** Put it on its own VLAN with no internet access.
        
    - **Strict Firewall Rules:** Only allow communication with specific, trusted devices.
        
    - **IPS Signatures:** Use an Intrusion Prevention System specifically tuned to watch for exploits targeting that older OS.

---

# 💻 2.3 Virtualization & Hypervisor Security

### 🧱 The Hypervisor: The Virtual Traffic Cop

**Definition:** The software (or hardware) that manages and allocates physical resources (CPU, RAM, Storage) to multiple Virtual Machines.

- **The Vulnerability:** Since the hypervisor sits between the guest OS and the actual hardware, it is the "High-Value Target." If the hypervisor is compromised, every VM running on it is exposed.
    
- **Resource Reuse:** To be efficient, the hypervisor re-uses RAM and CPU cycles. If not managed perfectly, data from "VM A" could stay in a memory register that "VM B" later reads. This is an **Information Disclosure** risk.
    
    +1
    

---

### 🏃 VM Escape: Breaking the Fourth Wall

**Definition:** An exploit where an attacker "breaks out" of a guest VM to interact directly with the host OS or other VMs on the same hardware.

- **The Impact:** This is a "Critical" severity exploit. It bypasses the primary security benefit of virtualization (isolation).
    
- **The 2017 Pwn2Own Case Study:**
    
    1. **The Chain:** Attackers used a JavaScript bug in **Microsoft Edge** to get into the guest Windows 10 OS.
        
    2. **The Escalation:** They used a Windows kernel bug to gain System privileges inside that VM.
        
    3. **The Escape:** Finally, they exploited a **Hardware Simulation bug in VMware** to "leap" out of the VM and execute code on the host machine.
        
- **The Lesson:** Always keep your hypervisor (VMware, VirtualBox, Hyper-V) patched. These "leaps" are rare but devastating.
    

---

### 📉 Virtualization Risks

- **Sprawl:** VMs are so easy to create that you might end up with hundreds of "forgotten" servers that aren't being patched (Shadow IT in the virtual world).
    
- **Local Privilege Escalation:** An attacker starts as a low-level user in a VM and uses a flaw to become an Admin, setting the stage for a VM Escape.
    
- **Shared Resources:** If a host has 4GB of RAM and hosts three VMs that _think_ they have 2GB each, the hypervisor must juggle that memory. **Memory management patches** are vital to ensure "VM A" cannot see "VM B’s" data during this swap.

---

# ☁️ 2.3 Cloud & Application Attacks

### 🌐 The Cloud Vulnerability Gap

**The Reality:** Cloud adoption is universal, but security maturity is not. Most cloud breaches in 2026 aren't from "super-hacks"—they are from **Misconfigurations**.

- **Identity is the Perimeter:** In the cloud, "IP addresses" matter less than **IAM (Identity & Access Management)**. If a dev leaves an S3 bucket public or an API key in a GitHub repo, the "walls" of the cloud don't matter.
    
- **Shadow Infrastructure:** 32% of cloud assets sit idle and unmonitored, often running **End-of-Life (EOL)** software that never gets patched.
    

---

### 🛠️ Common Attack Vectors

|Attack Type|Definition|The "Sec+ Key"|
|---|---|---|
|**DoS / DDoS**|Flooding a service to make it unavailable.|Focus on **Availability**.|
|**Auth Bypass**|Exploiting weak logic to get in without a password.|Often involves stolen **OAuth Tokens**.|
|**Directory Traversal**|Moving through folders on a server (`../../etc/passwd`).|Accessing files outside the web root.|
|**RCE**|**Remote Code Execution.** Running any command you want.|The "Holy Grail" for attackers.|

Export to Sheets

---

### 💉 Modern Application Exploits

- **Log4j (Log4Shell):** * **What it is:** A massive vulnerability in a common Java logging library.
    
    - **The Trick:** An attacker sends a specific string (a JNDI lookup) in a simple log message (like a chat box or a search field). The server "logs" it, but also **executes** it, allowing the attacker to take full control.
        
- **Out-of-Bounds Write:**
    
    - **The Concept:** A program writes data past the end of its intended "box" (buffer) in memory.
        
    - **The Result:** It overwrites adjacent memory, which can crash the system (**DoS**) or hijack the program's flow to run malicious code (**RCE**).
        
        +1
        
- **Injection (SQLi & XSS):** * These remain top threats. In the cloud, **SQLi** is often used to dump entire customer databases from misconfigured web apps.

---

# 🏭 2.3 Supply Chain & Third-Party Risk

### ⛓️ The Supply Chain Concept

**Definition:** The network of all moving parts (suppliers, manufacturers, distributors) required to deliver a product or service.

- **The Security Gap:** You can control your own security posture, but you cannot always control your service providers.
    
- **The "Pivot" Point:** Attackers often target a smaller, less-secure vendor to gain "trusted" access to a larger, high-value target.
    

---

### 🏢 Case Study: Target Corporation (2013)

- **The Breach:** 40 million credit cards stolen.
    
- **The Vector:** Attackers didn't hack Target directly. They hacked an **HVAC (Heating & Air Conditioning) firm** in Pennsylvania.
    
- **The Escalation:** The HVAC tech had VPN credentials to Target's network to manage thermostats. Attackers stole those credentials, entered the network, and pivoted to the Point-of-Sale (POS) systems at 1,800 stores.
    
- **Lesson:** Any vendor with network access—even the cleaning crew or the payroll firm—is a potential security risk.
    

---

### 📦 Hardware & Software Integrity

Trust is the foundation of security, but that trust can be manufactured or faked.

- **Counterfeit Hardware:** * **Example:** The 2022 Cisco reseller bust ($1 billion in fake gear).
    
    - **The Risk:** Knock-off hardware isn't just a fire hazard; it can contain "backdoors" in the firmware that allow attackers to bypass your firewall entirely.
        
- **Software Supply Chain (SolarWinds Orion):**
    
    - **The Attack (2020):** Attackers compromised the software build process at SolarWinds.
        
    - **The Result:** 18,000 customers (including the US Government and Microsoft) downloaded a **legitimate, digitally signed update** that contained a hidden backdoor.
        
    - **The "Stay" Time:** The breach went undetected for **9 months**, allowing attackers to exfiltrate massive amounts of data.
        

---

### 🛠️ Defense & Mitigation

How do we protect ourselves from a supply chain we don't fully control?

1. **Vendor Risk Management:** Conduct ongoing security audits of all contractors.
    
2. **Least Privilege for Vendors:** If the HVAC tech only needs to see the thermostat, don't give them access to the segment where the credit card data lives.
    
3. **Digital Signature Verification:** Always confirm the digital signature of software installations and updates.
    
4. **Hardware Provenance:** Buy only from authorized resellers to avoid counterfeit or tampered hardware.
    
5. **Open Source Auditing:** Realize that open-source code can be compromised at the source. Use tools to scan libraries for known vulnerabilities.

---

# ⚙️ 2.3 Misconfigurations & Unsecured Protocols

### 📂 1. Open Permissions & Cloud Exposure

**Definition:** Leaving data accessible to the public due to incorrect permission settings (extremely common in cloud storage).

- **Case Study (Verizon 2017):** 14 million records were exposed because a third-party vendor left an **Amazon S3 bucket** wide open.
    
- **The Lesson:** "Open by default" is the enemy. Always use **Implicit Deny**—if access isn't explicitly granted, it should be blocked.
    

---

### 🔑 2. Privileged Account Mismanagement

**The Risk:** Misconfiguring the **Root (Linux)** or **Administrator (Windows)** accounts.

- **Bad Habits:** Using weak passwords (`123456`, `password`) or leaving these accounts active for daily tasks.
    
- **Hardening Steps:**
    
    - **Disable Direct Root Login:** Force users to log in as a standard user and use `sudo` or `su` for administrative tasks.
        
    - **Principle of Least Privilege:** Only a tiny fraction of users should have administrative access.
        
    - **MFA:** Multi-Factor Authentication is a "must" for any privileged account.
        

---

### 📡 3. Unsecured Protocols (Cleartext)

**Definition:** Using "legacy" protocols that send data (including passwords) in plain text over the network.

- **The "Cleartext" Danger:** Anyone with a packet capture tool (like **Wireshark**) can see everything.
    
- **The Secure Swap:**
    

|Unsecure (Cleartext)|Secure (Encrypted)|Default Port|
|---|---|---|
|**Telnet**|**SSH** (Secure Shell)|22|
|**FTP**|**SFTP** (SSH File Transfer)|22|
|**HTTP**|**HTTPS** (TLS)|443|
|**SMTP / IMAP**|**SMTPS / IMAPS**|Varies (e.g., 465 / 993)|

Export to Sheets

---

### 🤖 4. Default Settings & The Mirai Botnet

**The Risk:** Many IoT devices ship with "Default Credentials" (Admin/Admin) that are never changed by the user.

- **Case Study (Mirai Botnet):**
    
    - **The Attack:** Mirai scanned the internet for IoT devices (cameras, routers, DVRs) using **60+ default username/password pairs**.
        
    - **The Impact:** It took over hundreds of thousands of devices to launch some of the largest **DDoS attacks** in history (e.g., the Dyn attack that took down Twitter and Reddit).
        
    - **The Result:** The code was released as Open Source, leading to countless variants that still plague the internet today.
        

---

### 🛡️ 5. Firewall & Port Management

- **Port Management:** Every open port is a potential door. Close anything that isn't essential.
    
- **Firewall Rulesets:** These can be complex. A single "Permit Any Any" rule at the bottom of a list can invalidate all the security above it.
    
- **Audit & Test:** Always run a port scan (like `nmap`) against your own devices to see what a hacker sees.

![](../attachments/Pasted%20image%2020260415223654.png)


---

Moving into **Mobile Device Security** is like trying to protect a mini-computer that is constantly running away from you. It’s one of the most personal—and therefore most dangerous—entry points for an attacker.

Here is the polished version for your vault.

---

# 📱 2.3 Mobile Device Security

### 🏃 The "Always-On" Risk

**The Problem:** Mobile devices are small, packed with sensitive data, and constantly in motion. They transition between trusted home Wi-Fi and untrusted public networks multiple times a day.

- **Purpose-Built Systems:** Unlike your Ubuntu lab, you don't have direct access to the mobile OS (iOS/Android). You are at the mercy of the manufacturer's security.
    

---

### 🔓 Escaping the Sandbox: Rooting vs. Jailbreaking

Manufacturers "sandbox" apps to keep them from stealing each other's data. Users often try to bypass these limits:

- **Rooting (Android):** Gaining "Superuser" (Root) access to the Linux-based Android OS.
    
- **Jailbreaking (Apple iOS):** Circumventing Apple's software restrictions to install unauthorized apps.
    
- **The Danger:** Once you "escape" the sandbox, **malware gets those same privileges.** * **MDM Failure:** Mobile Device Management (MDM) tools rely on the OS being intact. On a rooted/jailbroken device, the MDM becomes useless because the user (or malware) can simply turn it off.
    

---

### 📲 Sideloading & Malicious Apps

**Definition:** Installing an app from a third-party source (a website or an unofficial app store) instead of the official Google Play or Apple App Store.

- **The Vulnerability:** Official stores vet apps for malware and privacy leaks. Sideloading skips this "Border Control."
    
    +1
    
- **Impact:** 80% of mobile malware is found in sideloaded apps. A single Trojan horse app can steal banking credentials, record your screen, or act as a "pivot" into your company's network.
    
    +1
    

---

### 🛡️ Management & Mitigation

To regain control, organizations use these strategies:

1. **MDM (Mobile Device Management):** Sets policies for the entire device (e.g., "Must have a 6-digit PIN," "Remote wipe if lost," "Block sideloading").
    
2. **MAM (Mobile Application Management):** Only manages specific business apps (like Outlook) without controlling the user's personal photos or texts.
    
3. **OTA (Over-The-Air) Updates:** Ensuring devices are patched automatically. Rooted devices often lose the ability to receive these, making them "forever vulnerable."
    
4. **Geofencing:** Disabling certain features (like the camera) when the device enters a specific physical location (like a secure lab).

---

# 🕵️‍♂️ 2.3Zero-Day Vulnerabilities

### ⏱️ The "Zero-Day" Concept

**Definition:** A vulnerability that is unknown to the vendor. The "zero" refers to the number of days the vendor has had to fix the problem.

- **The Race:** Once an attack is spotted in the wild, the clock starts. The vendor must rush to create a patch while the attacker rushes to exploit as many systems as possible.
    
- **The Defense Difficulty:** Because there is no signature or patch, traditional antivirus often fails. You have to rely on **Behavioral Analysis** (looking for a program doing something suspicious) to stop it.
    

---

### 🏛️ CVE: The Security Dictionary

**CVE (Common Vulnerabilities and Exposures):** Managed by **MITRE**, this is the industry-standard list of known vulnerabilities.

- **Format:** `CVE-YYYY-XXXX` (e.g., CVE-2023-2033).
    
- **The Goal:** To give everyone (vendors, researchers, and admins) a common language to identify and fix specific bugs.
    

---

### 📅 2023: The Year of the Zero-Day

You listed some heavy hitters. Notice a pattern? They often target the **Sandbox** or the **Kernel**.

|Date|Target|Vulnerability Type|Impact|
|---|---|---|---|
|**April 2023**|**Google Chrome**|Memory Corruption|Allowed a "Sandbox Escape" (getting out of the browser to hit the OS).|
|**May 2023**|**Microsoft**|Secure Boot Flaw|Allowed attackers to bypass the "Trusted Boot" process you studied earlier.|
|**May 2023**|**Apple iOS**|3-Bug Chain|A mix of sandbox escapes and data disclosure.|

Export to Sheets

---

### 🛡️ How to Defend Against the "Unknown"

Since you can't patch a Zero-Day immediately, you use **Defense in Depth**:

1. **EDR (Endpoint Detection & Response):** Monitors system behavior. If "Notepad" suddenly tries to change a system file, EDR kills the process even if it doesn't recognize the "virus."
    
2. **Network Segmentation:** If an attacker uses a Zero-Day to get into one VM, your firewall rules (like the ones in your Ubuntu project) should stop them from moving to the rest of the network.
    
3. **WAF / IPS:** These can sometimes block the _method_ of the attack (like a specific type of memory injection) even if they don't know the specific vulnerability.

---

