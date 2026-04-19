
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

# 🦠 2.4 Malware Types & Characteristics

### 🧪 The Attack Chain

Malware rarely works alone. Think of it like a professional heist team:

1. **The Entry (Worm):** Exploits a vulnerability to get into the network.
    
2. **The Delivery (Trojan):** Drops a "payload" onto the system.
    
3. **The Persistence (Backdoor/Rootkit):** Ensures the attacker can get back in even if the computer restarts.
    
4. **The Goal (Ransomware/Spyware):** Either encrypts data for cash or steals secrets.
    

---

### 🧬 Viruses vs. Worms (The "Big Two")

|Feature|**Virus**|**Worm**|
|---|---|---|
|**User Action**|**Required.** You must open a file, click a link, or run a program.|**Not Required.** It spreads automatically across the network.|
|**Host File**|Needs to "attach" itself to a legitimate program.|Stand-alone software; doesn't need a host file.|
|**Speed**|Spreads as fast as humans share files.|Spreads at the speed of the network (extremely fast).|

Export to Sheets

---

### 💰 Ransomware & Crypto-Malware

This is the most financially damaging malware today.

- **The Attack:** It uses **Asymmetric Encryption** (Public Key Cryptography) to lock your files. The attacker holds the Private Key.
    
- **The Impact:** Your OS stays running (so you can see the "Pay Me" note), but your pictures, docs, and databases are useless.
    
- **The Defense:** **Offline Backups.** If your backup is connected to the computer, the ransomware will encrypt the backup too.
    

---

### 🕵️‍♂️ Stealth & Surveillance

- **Trojan Horse:** Software that pretends to be something useful (like a free game or a driver) but hides malicious code inside.
    
- **Rootkit:** The "Ghost" of malware. It modifies core system files to hide its presence from the Task Manager and Antivirus.
    
- **Keylogger / Spyware:** Sits quietly in the background. It records every keystroke (passwords/PII) and sends them to the attacker.
    
    +1
    
- **Logic Bomb:** Malware that sits dormant until a specific "trigger" occurs (like a specific date or a certain employee being deleted from payroll).
    

---

### 🛡️ The "Keep Everything Updated" Rule

Your notes are spot on: **Updates are your #1 weapon.**

1. **OS & Apps:** Patches the "holes" that Worms use to enter.
    
2. **Antivirus Signatures:** Tells your software what the latest "fingerprints" of malware look like.
    
3. **The Human (You):** Awareness stops you from clicking the link that starts a Virus.

---

# 🦠 2.4 Viruses vs. Worms (The Deep Dive)

### 🧬 The Virus (Needs a Human)

**Definition:** Malicious code that reproduces by inserting itself into another program or file. It cannot move on its own; it "hitchhikes" on your actions.

- **The Trigger:** You must **execute** something (open an email attachment, run an `.exe`, or open a macro-enabled Word doc).
    
- **The Persistence:** Once run, it can hide in several places:
    
    - **Program Virus:** Attaches to an application.
        
    - **Boot Sector Virus:** Hides in the part of the drive that starts the OS. It runs _before_ the OS even loads.
        
    - **Script/Macro Virus:** Uses the built-in logic of browsers or Microsoft Office (Excel/Word) to run malicious commands.
        
- **The "Fileless" Virus (Stealth):** This is the modern "ninja" version. It doesn't sit in a file on your disk; it lives entirely in the **RAM (Memory)**. Because there’s no "file" to scan, traditional antivirus often misses it.
    
    +1
    

---

### 🪱 The Worm (Needs a Network)

**Definition:** Self-replicating malware that uses the network to spread. It does **not** need you to click anything.

- **The Trigger:** It exploits a **vulnerability** (like an unpatched service or an open port) to "crawl" from one computer to the next.
    
- **The Speed:** Because it doesn't wait for humans, it spreads at the speed of light. A single worm can take down an entire global corporation in minutes by saturating network bandwidth.
    
- **The Payload:** Many worms are used to install **Backdoors**, turning your computer into a "Zombie" for a **Botnet**.
    

---

### ⚖️ Quick Comparison Table

|Feature|**Virus**|**Worm**|
|---|---|---|
|**Movement**|Needs a host file/program.|Stand-alone; moves independently.|
|**Transmission**|Human action (USB, Email, Downloads).|Network exploits (Self-propagating).|
|**Detection**|Signature-based Antivirus.|Firewalls, IDS/IPS, and Patching.|
|**Primary Goal**|Corrupt files, steal data, annoy.|Spread fast, install backdoors, eat bandwidth.|

Export to Sheets

---

### 🛡️ The Defensive Strategy

- **For Viruses:** **User Training.** If the human doesn't click, the virus doesn't spread.
    
- **For Worms:** **Patch Management & Firewalls.** If the "hole" in the OS is patched, the worm can't get in. If the firewall blocks the port, the worm can't see the computer.

![](../../Pasted%20image%2020260417232458.png)

![](../../Pasted%20image%2020260417232248.png)

---

---

# 🕵️‍♂️ 2.4 Spyware, Adware, & Bloatware

### 👁️ Spyware & Keyloggers (The Spies)

**Definition:** Software that monitors your activity and sends the data back to an attacker without your consent.

- **The Goal:** Identity theft, capturing bank logins, and affiliate fraud (stealing credit for your online purchases).
    
- **Keyloggers:** A specific type of spyware that records **every keystroke**.
    
    - **Impact:** Your passwords, private messages, and credit card numbers are captured before they are even encrypted by the website you're using.
        
- **Defense:** Behavioral analysis in Antivirus (looking for software that is "hooking" into the keyboard) and keeping signatures updated.
    

---

### 📢 Adware (The Advertisers)

**Definition:** Software designed to flood your screen with advertisements or redirect your browser to specific sites.

- **The Trick:** Often bundled with "free" software or peer-to-peer (P2P) files. It might even pretend to be **"Fake Security Software"** telling you that you have a virus and need to pay to fix it.
    
- **The Clean-up:** Adware is notoriously hard to remove because it embeds itself in the browser.
    
    - **Tools:** Specialized scanners like **Malwarebytes** are often better than traditional AV for this.
        
    - **The "Nuke" Option:** Always have a backup. Sometimes it's faster to wipe the drive than to hunt down every last piece of adware.
        

---

### 📦 Bloatware (The Unwanted Guests)

**Definition:** Pre-installed software on a new computer or phone that you didn't ask for and likely don't need.

- **The Risk:** * **Performance:** Uses CPU, RAM, and storage, making a brand-new PC feel slow.
    
    - **Security:** Every app is a potential **Exploit**. If the manufacturer installed a "Photo Editor" that has a vulnerability, your whole system is at risk even if you never open the app.
        
- **Removal:**
    
    - **Built-in Uninstaller:** Your first step.
        
    - **Third-Party Cleaners:** Use with caution. Some "cleaners" are actually Adware in disguise.
        
    - **Clean Install:** The "Pro" move—wiping the factory OS and installing a fresh, "Vanilla" version of Windows or Linux.
        

---

### 🛡️ Defensive Mindset

1. **Read the Fine Print:** During software installation, always choose "Custom Install" to uncheck the "Free Browser Toolbar" or "Bonus Optimizer" (which are actually Adware/Spyware).
    
2. **Signature Updates:** New spyware variants appear hourly. Your AV needs the latest "mugshots" to catch them.
    
3. **The Backup Rule:** As you noted, "Cleaning adware isn't easy." A solid backup allows you to restore to a clean state in minutes.

---

# 🕵️‍♂️ 2.4 Keyloggers, Logic Bombs, & Rootkits

### ⌨️ Keyloggers & Data Loggers

**Definition:** A form of spyware that records user input. It is particularly dangerous because it captures data **before encryption** (e.g., before your browser turns your password into HTTPS traffic).

- **Beyond Keystrokes:** Modern loggers don't just watch the keyboard. They also capture:
    
    - **Clipboard Logging:** Stealing anything you "Copy" (like passwords from a manager).
        
    - **Screen Logging (Screenshots):** Taking a picture of your screen every few seconds.
        
    - **Instant Messaging:** Capturing chat logs and search queries.
        
- **Defense:** **MFA (Multi-Factor Authentication)**. Even if they have your password, they don't have your physical token or biometric.
    

---

### 💣 Logic Bombs

**Definition:** Malicious code that remains dormant until a specific "trigger" or condition is met.

- **The "Time Bomb":** Triggered by a specific date or time.
    
- **The "User Event":** Triggered by an action (e.g., an admin being removed from the payroll database).
    
- **Case Study: South Korea (March 20, 2013):**
    
    - **The Attack:** At exactly 2:00 PM, a logic bomb activated on thousands of computers at South Korean banks and media outlets.
        
    - **The Result:** It deleted the **Master Boot Record (MBR)** and wiped hard drives. Systems rebooted to a "Boot device not found" error, paralyzing ATMs and newsrooms.
        
- **Defense:** **Change Control** and **Auditing**. Use tools like **Tripwire** (Host-based IDS) to alert you if a system file is modified unexpectedly.
    

---

### 👻 Rootkits

**Definition:** A collection of tools designed to gain **Root** (Admin) access while remaining completely invisible to the OS.

- **The "Ghost" Factor:** Rootkits modify the **Kernel** (the core of the OS). When you ask the Task Manager "What programs are running?", the Rootkit intercepts that question and hides itself from the list.
    
- **Where they live:**
    
    - **Kernel-mode:** Part of the OS itself.
        
    - **Firmware/UEFI:** Built into the hardware's BIOS. It survives even if you wipe the hard drive and reinstall Windows.
        
- **Defense:** * **UEFI Secure Boot:** This ensures that only "signed," trusted software can load during the boot process, blocking rootkits from starting.
    
    - **Specific Removers:** Once a rootkit is known, specialized tools are built to "hunt" for its unique footprint.

---

# 🏗️ 2.4 Physical Security & Environmental Controls

### 🚪 1. The Physical Vulnerability

**The Golden Rule:** If an attacker has physical access to your hardware, it is no longer _your_ hardware.

- **Circumventing the OS:** With physical access, an attacker can reboot into a Live USB, bypass your Windows/Linux login, and read your unencrypted files directly.
    
- **Brute Force (Physical):** Just like guessing a password, physical brute force is about using raw power (crowbars, hammers) to overcome a lock or window.
    

---

### 💳 2. RFID & Proximity Attacks

**Definition:** Radio Frequency Identification (RFID) is the tech inside your office badge or key fob.

- **The Vulnerability (Cloning):** You can buy a duplicator on Amazon for less than $50. An attacker only needs to be within a few inches of your pocket (on a bus or in an elevator) to "sniff" and clone your badge.
    
- **The Defense:**
    
    - **MFA (Multi-Factor):** Require a PIN + the badge to open the door.
        
    - **Shielding:** Use RFID-blocking wallets or sleeves to prevent unauthorized scanning.
        

---

### ❄️ 3. Environmental Attacks (Infrastructure)

If you can’t hack the server, you hack the **room** it lives in.

- **Power Monitoring & Sabotage:**
    
    - An attacker might cut the main power from outside the building.
        
    - **Defense:** **UPS** (Uninterruptible Power Supply) for short-term and **Generators** for long-term backup.
        
- **HVAC (Heating, Ventilation, Air Conditioning):**
    
    - Servers generate massive heat. If the cooling is cut, hardware will shut down or permanently melt within minutes.
        
    - **Defense:** Sensors that alert if humidity or temperature spikes.
        
- **Fire Suppression:**
    
    - Some systems (like Halon or FM-200) work by removing oxygen. An attacker could trigger a false fire alarm to force an evacuation or a server shutdown.
        

---

### 🛡️ 4. Physical Security Controls (Layered Defense)

Think of this as a **"Defense in Depth"** for the physical world:

1. **Perimeter:** Fences, lighting, and signage ("Restricted Area").
    
2. **Entrance:** Guards, cameras (CCTV), and **Mantraps** (a small room with two doors where the first must close before the second opens).
    
3. **Internal:** Locked racks, hardware locks (Kensington locks), and **Safe** storage for backups.
    
4. **Sensors:** Motion detectors and "Tripwire" alarms on doors/windows.

---

## ⚡ 2.4 Denial of Service (DoS & DDoS)

### 🛑 1. The Goal: Availability

The primary target of a DoS attack is the **"A"** in the **CIA Triad** (Confidentiality, Integrity, Availability).

- **Intentional:** Overloading a service for competitive advantage or a "smokescreen" (distracting the IT team while a different hack happens elsewhere).
    
- **Unintentional:** It's not always a hacker!
    
    - **Layer 2 Loop:** A switch without **STP (Spanning Tree Protocol)** can create a broadcast storm that kills the network.
        
    - **The "Slashdot Effect":** Too many legitimate users downloading a huge file (like a new Linux Distro) on a weak connection.
        

---

### 🤖 2. DDoS (Distributed Denial of Service)

**Definition:** Using an army of infected computers (**Botnets**) to launch a coordinated attack.

- **The Zeus Botnet:** At its peak, it infected over **3.6 million PCs**.
    
- **Asymmetric Threat:** A single teenager with a botnet can bring down a multi-billion dollar corporation. The attacker has fewer resources, but more "firepower."
    

---

### 📢 3. Amplification & Reflection Attacks

This is the most common way modern DDoS attacks reach **Terabit** speeds.

- **Reflection:** The attacker sends a request to a legitimate third-party service (like a DNS server) but **spoofs** the return IP address to be the victim’s. The service "reflects" the answer to the victim.
    
- **Amplification:** The attacker sends a _tiny_ query that triggers a _massive_ response.
    
    - **NTP/DNS/ICMP:** These protocols don't require much authentication.
        
    - **Example:** Sending a 1-byte DNS query that results in a 50-byte answer sent to the victim. If you have 1 million bots doing this, the victim's bandwidth is instantly deleted.
        

---

### 🛡️ 4. Mitigations

- **Cloud Scrubbing:** Using services like Cloudflare to "clean" traffic before it hits your server.
    
- **IPS/IDS:** Identifying patterns of DDoS and blocking the source IPs.
    
- **Patching:** Fixing the vulnerabilities that allow botnets to form in the first place.

---

![](../../Pasted%20image%2020260418010503.png)![](../../Pasted%20image%2020260418010616.png)


---

# 🌐 2.4 DNS Attacks & URL Hijacking

### 🏴‍☠️ 1. DNS Hijacking vs. DNS Poisoning

The goal is the same (redirection), but the method is different:

- **DNS Poisoning (Cache Poisoning):** * **The Method:** The attacker sends a fake response to a DNS resolver before the real server can answer. The resolver then "caches" (remembers) the fake IP.
    
    - **The Impact:** Every user who asks that DNS server for "bank.com" gets sent to the hacker's IP for the next few hours.
        
- **Domain Hijacking:**
    
    - **The Method:** The attacker doesn't touch the server. They hack the **Domain Registrar account** (like GoDaddy or Namecheap) using social engineering or brute force.
        
    - **The Impact:** They change the authoritative records. You "lose" your domain.
        
    - **Case Study (Brazil 2016):** Attackers took over 36 domains of a major bank for 6 hours. They controlled the bank's email and web traffic, even obtaining a valid SSL certificate to look legitimate.
        

---

### ⌨️ 2. URL Hijacking (Typosquatting / Brandjacking)

This takes advantage of human error rather than technical flaws.

- **The "Mistake" Revenue:** Attackers buy `professormesser.org` or `professormessor.com` (typo).
    
- **The Intent:**
    
    - **Phishing:** The site looks identical to the real one to steal logins.
        
    - **Malware:** A "drive-by download" infects you the second the page loads.
        
    - **Advertising:** They just want the traffic to sell ads or sell the domain back to the owner for a high price.
        

---

### 🧪 3. The "Host File" Trick

- **The Concept:** Your computer checks its local `hosts` file _before_ it asks a DNS server.
    
- **The Attack:** If an attacker gets administrative access to your Ubuntu or Windows machine, they can add one line: `123.123.123.123 google.com`.
    
- **The Result:** You will go to the hacker's IP every time you type "https://www.google.com/url?sa=E&source=gmail&q=google.com," and your browser won't even try to reach a real DNS server.
    

---

### 🛡️ Defensive Strategy

1. **For Domain Hijacking:** Use **2FA (Two-Factor Authentication)** on your domain registrar account. This would have prevented the Brazilian bank hack.
    
2. **For DNS Poisoning:** Implement **DNSSEC** (DNS Security Extensions), which adds a digital signature to DNS responses to prove they are authentic.
    
3. **For the Host File:** Monitor file integrity (like using **Tripwire**) to alert you if the `hosts` file is modified.

---

# 📶 2.4 Wireless Attacks (DoS & Interference)

### 🚪 1. Wireless Deauthentication (Logical Attack)

**The Concept:** Wireless networks use "Management Frames" to manage connections. A **Deauthentication (deauth) frame** tells a device: "You are no longer connected, please leave."

- **The Vulnerability:** In older standards (like 802.11n), these management frames were **unencrypted**.
    
- **The Attack:** An attacker can spoof your Access Point's MAC address and send a "Deauth" frame to your laptop. Your laptop obeys, disconnects, and then immediately tries to reconnect.
    
- **The Goal:** 1. **DoS:** Just to be annoying and kick you off. 2. **WPA Handshake Capture:** The attacker kicks you off so that when you reconnect, they can "sniff" the authentication handshake to try and crack your Wi-Fi password.
    
- **The Fix:** **802.11w (now part of 802.11ac/ax).** This standard encrypts Management Frames so they can't be spoofed.
    

---

### 📡 2. Wireless Jamming (Physical Attack)

**The Concept:** Overwhelming the wireless frequency (2.4GHz or 5GHz) with "noise" so the devices can't "hear" the legitimate signal.

- **Signal-to-Noise Ratio (SNR):** Jamming decreases the SNR. If the noise is louder than the data, the data is lost.
    
- **Types of Jamming:**
    
    - **Constant:** Non-stop noise or random bits.
        
    - **Reactive:** Only jams when it senses someone else trying to transmit (very stealthy).
        
- **The "Accidental" Jammer:** It’s not always a hacker. **Microwave ovens**, old cordless phones, and fluorescent lights can jam 2.4GHz Wi-Fi unintentionally.
    

---

### 🦊 3. "Fox Hunting" (Mitigation)

If someone is jamming you, you can't stop it with software. You have to find the physical source.

- **Directional Antenna:** Used to find the direction where the "noise" is strongest.
    
- **Attenuator:** Used to "turn down" the sensitivity as you get closer to the source so you can pinpoint the exact location.

![](../../Pasted%20image%2020260418011740.png)

---

---

# 🕵️‍♂️ 2.4 On-Path Attacks (formerly Man-in-the-Middle)

### 🛣️ 1. The On-Path Concept

**Definition:** An attacker places themselves between two devices (usually a user and a server) to intercept, read, or modify the data flowing between them.

- **The "Pass-Through":** The attacker doesn't just steal the data; they pass it on to the real destination. This makes the attack invisible because the website still loads normally for the victim.
    

---

### 🧪 2. ARP Poisoning (Network Level)

**How it works:** This happens on your **Local Subnet (LAN)**.

- **The Flaw:** ARP (Address Resolution Protocol) is "trusting." It has no security. If a computer says, "I am the router," every other computer believes it.
    
- **The Attack:** The attacker sends fake ARP messages to your computer saying, "I am the Gateway/Router." Your computer updates its MAC table and starts sending all its internet traffic to the attacker’s MAC address.
    
- **The Result:** The attacker sees everything you do before forwarding it to the real router.
    

---

### 🌐 3. On-Path Browser Attack (formerly Man-in-the-Browser)

**How it works:** The "middleman" isn't a separate device on the network; it's **Malware inside your browser.**

- **The Advantage:** Since the malware is _inside_ the browser, it sees the data **before it is encrypted** (HTTPS) and **after it is decrypted**.
    
- **The Scenario:** You go to your bank's website. Everything looks 100% normal. You log in. The malware waits until you click "Transfer Money," then silently changes the destination account number to the attacker's account before the request ever leaves your computer.
    

---

### 🛡️ 4. Mitigations

- **For ARP Poisoning:** Use **DAI (Dynamic ARP Inspection)** on your network switches. This prevents fake ARP messages from being broadcast.
    
- **For Browser Attacks:** * **Browser Hardening:** Keep the browser and extensions updated.
    
    - **Endpoint Protection:** Antivirus/EDR to catch the malware before it can hook into the browser.
        
- **For General Traffic:** **Encryption (TLS/SSL).** If the traffic is encrypted, the attacker might see _where_ you are going, but they can't see _what_ you are sending (unless they use a Man-in-the-Browser attack).

---

---

# 🔄 2.4 Replay Attacks & Session Hijacking

### 🔁 1. The Replay Attack

**Definition:** An attacker captures a sequence of network packets (like a login or a command) and "replays" them later to the server to mimic the original user.

- **The "Key" Difference:** The attacker doesn't need to know your password. They just need to "record" the encrypted hash you sent and play it back.
    
- **Is it On-Path?** No. The attacker can capture the data, go home, and replay it hours later. They don't have to stay "in the middle."
    
- **The Defense:** **Salting and Timestamps.** If every login request requires a unique "nonce" (number used once) or a timestamp that expires in 30 seconds, a "replayed" packet will be rejected by the server.
    

---

### 🍪 2. Session Hijacking (Cookie Hijacking)

**The Concept:** When you log into a site, the server gives you a **Session ID** (usually stored in a cookie) so you don't have to re-enter your password on every page.

- **The Attack:** If an attacker steals that Session ID, they can put it into their own browser and **become you** without ever needing your password.
    
- **How they get the ID:**
    
    - **Information Gathering:** Sniffing Wi-Fi using Wireshark or Kismet.
        
    - **Cross-Site Scripting (XSS):** Using a malicious script to "read" your cookies and send them to the attacker.
        
    - **Header Manipulation:** Tools like _Scapy_ or browser add-ons to tamper with the data sent to the server.
        

---

### 🛡️ 3. Mitigations

- **Encryption (HTTPS/TLS):** This is the ultimate fix. If the entire session is encrypted end-to-end, the attacker can't "see" the Session ID to steal it.
    
- **Session Expiry:** Making sessions short-lived so a stolen cookie becomes useless quickly.
    
- **Cookie Flags:** * **HttpOnly:** Prevents JavaScript (XSS) from reading the cookie.
- **Secure:** Ensures the cookie is only sent over HTTPS.

![](../../Pasted%20image%2020260418013034.png)

---

# 💻 2.4 Malicious Code & High-Impact Breaches

### 🧩 1. The "Unlocked Door" vs. "Breaking the Hinge"

**The Concept:** Security isn't just about stopping hackers; it's about closing the doors we leave open.

- **Low-Tech Entry:** Social engineering or using `admin/admin` (Default Credentials) is like walking through an unlocked door.
    
- **High-Tech Entry:** Using **Arbitrary Code Execution (ACE)** to force a system to run malicious instructions is like knocking the pins out of the door hinges.
    

---

### 🏛️ 2. Case Study Analysis

|Breach|Attack Type|Impact / Method|
|---|---|---|
|**WannaCry (2017)**|**Worm/Ransomware**|Exploited **SMBv1** (EternalBlue). It used a system-level vulnerability to move across networks without user interaction.|
|**British Airways**|**XSS (Cross-Site Scripting)**|22 lines of **JavaScript** were injected into the checkout page. It acted as a "digital skimmer," stealing credit card data as users typed it.|
|**Estonian Health**|**SQL Injection**|Attackers used malicious SQL queries in a web form to trick the database into dumping the records of the entire population.|

Export to Sheets

---

### 🛠️ 3. Defensive Layers (Defense in Depth)

Since attackers use any opportunity, you need a multi-layered response:

1. **Host-Based:** Anti-malware and Endpoint Detection (EDR) to stop executables.
    
2. **Network-Based:** Firewalls and IPS to block protocols like SMBv1 from being exposed to the internet.
    
3. **Application-Based:** Input validation and "Sanitizing" data to prevent SQLi and XSS.
    
4. **Operational:** Continuous **Patch Management**. WannaCry was only successful because organizations didn't apply a patch that had been available for months.

---

# 🧠 2.4 Memory & Session Vulnerabilities

### 🌊 1. Buffer Overflows

**The Concept:** An application receives more data than it can hold in its "buffer" (memory "box"). The extra data spills over into adjacent memory areas.

- **The Goal:** To overwrite the **Return Address** in memory so that when the program finishes its current task, it jumps to the attacker's malicious code instead of going back to normal operation.
    
- **The "Art" of the Overrun:** It’s difficult to do without crashing the app. A "pro" exploit is **repeatable** and silent.
    
- **Defense:**
    
    - **Bounds Checking:** Developers must ensure the "box" can't take more than it's built for.
        
    - **ASLR (Address Space Layout Randomization):** Scrambles where things are kept in memory so the attacker doesn't know where to "point" their exploit.
        
    - **DEP (Data Execution Prevention):** Marks certain memory areas as "non-executable" so code can't run from there.
        

---

### ⬆️ 2. Privilege Escalation

**Definition:** Gaining a higher level of access than you are supposed to have.

- **Vertical Escalation:** A standard user becoming an **Administrator** or **Root**.
    
- **Horizontal Escalation:** A user gaining access to another user's data (e.g., you log in as Mahdi but can see someone else's private notes).
    
- **Case Study (CVE-2023-29336):** A Win32k kernel driver flaw that allowed attackers to gain **SYSTEM privileges** (the highest level in Windows).
    
- **Defense:** Patching is the only real fix. These are always "Critical" priority.
    

---

### 🌊 3. CSRF / XSRF (Cross-Site Request Forgery)

**The Nickname:** "Sea-Surf" or "Session Riding."

- **The Concept:** It takes advantage of the **trust** a website has in your browser. If you are logged into your bank, your browser has a "session cookie."
    
- **The Attack:** You visit a malicious site in another tab. That site has a hidden script that tells your browser: _"Send a request to bank.com to transfer $1000 to the hacker."_ * **The Result:** Because you are already logged in, the bank sees a valid request coming from your browser and processes it. **You never even knew it happened.**
    
- **Defense:** **Anti-Forgery Tokens.** The website should require a unique, hidden "token" for every transaction that a malicious site wouldn't have access to.

![](../../Pasted%20image%2020260418014458.png)

---

# 🔐 2.4 Cryptographic & Downgrade Attacks

### 🎂 1. The Birthday Attack (Hash Collisions)

**The Concept:** Based on the "Birthday Paradox," which proves that in a surprisingly small group, the odds of a match are high.

- **The Digital Version:** A **Hash Collision** occurs when two different pieces of data produce the exact same hash value.
    
- **The Attack:** An attacker generates thousands of versions of a "malicious" document (like a fake contract) until its hash matches a "legitimate" document.
    
- **Why it matters:** If I can make a fake file have the same MD5 hash as a real file, I can swap them, and your security tools will think the fake file is the original.
    
- **The Victim:** **MD5.** It was the standard for years but is now considered "broken" because collisions are too easy to find.
    

---

### 📉 2. Downgrade Attacks

**The Concept:** Instead of trying to break strong encryption (which could take a trillion years), the attacker tricks the two systems into using **weak** encryption that is easy to crack.

- **The Logic:** Modern servers support old versions of security for "backward compatibility." The attacker tells the server: _"Hey, I'm an old computer, can we use the weakest security possible?"_
    

---

### 🧥 3. SSL Stripping (HTTPS Downgrade)

**The Concept:** A specific type of **On-Path Attack** where the attacker sits between the victim and the server.

- **The Method:** 1. The victim asks for `https://bank.com`. 2. The attacker intercepts this and asks the bank for the `https` version on the victim's behalf. 3. The attacker then sends the page back to the victim as **`http`** (unencrypted).
    
- **The Result:** The "S" is stripped away. The victim sees the website, but all their passwords and data are now sent in **Plaintext** to the attacker.
    
- **The Visual Cue:** The victim might notice the "Padlock" icon is missing in the browser, but many people don't look.
    

---

### 🛡️ Defensive Strategy

1. **For Birthday Attacks:** Use stronger hashing algorithms like **SHA-256** or **SHA-3**. They produce much longer hashes, making a collision mathematically "impossible" with current technology.
    
2. **For SSL Stripping:** Use **HSTS (HTTP Strict Transport Security).** This is a setting on the server that tells the browser: _"Never, ever communicate with me over plain HTTP. If someone tries to strip the S, block the connection."_

![](../../Pasted%20image%2020260419211022.png)

---
