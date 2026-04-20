# Domain 3.0: Security Architecture
## 3.1 Cloud Infrastructure & Responsibility

> [!ABSTRACT]
> Moving to the cloud doesn't remove security responsibility; it just shifts it. The "Shared Responsibility Model" defines where the provider's job ends and the customer's job begins.

---

### ☁️ Cloud Service Models (The "Control vs. Ease" Scale)

| Model | Who does the work? | Pro Example | Security Ownership |
| :--- | :--- | :--- | :--- |
| **IaaS** (Infrastructure) | **Client** mostly | AWS EC2 / Azure VM | You manage the OS, Apps, and Data. High control, high effort. |
| **PaaS** (Platform) | **Shared** | Google App Engine | You just manage the code/data. Provider handles the OS and hardware. |
| **SaaS** (Software) | **Provider** mostly | Office 365 / Gmail | Everything is managed by the vendor. You only manage your data/users. |

#### ⚠️ The "Difficult Factor": Responsibility Gaps
* **The Confusion:** If my AWS server gets hacked, it's Amazon's fault, right?
* **The Reality:** No. In **IaaS**, Amazon is only responsible for the "Physical" security of the building and the hardware. If you leave your Windows Server unpatched, that is **your** security failure.

---

### 🔄 Deployment Models
* **Public:** Shared resources (AWS, Google Cloud).
* **Private:** Your own "cloud" on your own hardware.
* **Hybrid:** A mix of Public and Private.
	* **The "Mess" Factor:** As noted, Hybrid requires complex integration. If your local identity management (Active Directory) doesn't sync perfectly with your Cloud identity, you create "Ghost Accounts" that hackers love.
* **Community:** Shared by organizations with similar goals (e.g., several hospitals sharing a secure medical cloud).

---

### 🧠 Active Recall / Scenario
**Scenario:** A startup wants to launch a new app. They don't have a dedicated IT team to manage Linux servers or update Python versions. They just want to upload their code and go.
**The Fix:** They should use **PaaS (Platform as a Service)**. It strikes the balance between the restriction of SaaS and the heavy management of IaaS.

---

![](../../Pasted%20image%2020260420015052.png)

---

# Domain 3.0: Security Architecture
## 3.1 Physical vs. Logical Segmentation & Control Planes

> [!ABSTRACT]
> To prevent lateral movement, we must separate users and data. We can do this physically (separate hardware) or logically (virtual separation).

---

### 🛡️ Segmentation: Keeping "A" away from "B"

| Method | The "How" | Security Level |
| :--- | :--- | :--- |
| **Air Gap** | Physical separation. No cables/wireless link between Switch A and B. | **Extreme.** Used for nuclear plants or secure vaults. |
| **Physical** | Separate hardware (Switch A for Customer A, Switch B for Customer B). | **High.** Harder to misconfigure, but expensive. |
| **VLAN** | One physical switch split into virtual "halves." | **Efficiency.** Most common in offices. Logical separation via software. |

---

### ✈️ The Three Planes (How the Network "Thinks")
Think of a network switch like an airport:

1. **Management Plane:** **The Admin Office.**
   - *What it does:* Where you log in (SSH, HTTPS, API) to configure the switch.
   - *Security:* If this is breached, the attacker owns the whole network. **MFA is a must here.**

2. **Control Plane:** **The Air Traffic Control.**
   - *What it does:* The "brains." It builds the routing tables and decides where data *should* go. It handles the "directions."

3. **Data Plane (Forwarding Plane):** **The Runway.**
   - *What it does:* The "muscle." It actually moves the bits and bytes from port 1 to port 5 based on the Control Plane's instructions.

---

### ⚠️ The "Difficult Factor": VLAN Hopping
* **The Confusion:** Is a VLAN as secure as an Air Gap?
* **The Reality:** **No.** Since a VLAN is software-based, a clever attacker can sometimes "hop" from one VLAN to another if the switch is misconfigured. In an Air Gap, there is no physical path to hop onto.

---

# Domain 3.0: Security Architecture
## 3.1 Infrastructure Selection & Availability Strategies

> [!ABSTRACT]
> Choosing between Physical (On-Prem) and Cloud is a balance of **Capital Expenditure (CapEx)** vs. **Operational Expenditure (OpEx)** and **Control** vs. **Scalability**.

---

### 🏗️ On-Premise vs. Cloud
| Feature | On-Premise (Physical) | Cloud-Based |
| :--- | :--- | :--- |
| **Control** | Full control over hardware/OS. | Limited to what the provider allows. |
| **Cost** | High (Cooling, Electricity, Staff, Hardware). | Lower entry cost (Pay-as-you-go). |
| **Risk** | Physical disasters (fire/flood) at your site. | Shared fate; if the provider is breached, you might be too. |
| **Scalability** | Slow (must buy/install new servers). | Instant (click a button to add RAM/Storage). |

---

### 🏎️ Specialized Systems: RTOS
* **RTOS (Real-Time Operating System):** * **Purpose:** Tasks must be completed within a strict time constraint.
    * **Example:** Industrial robots, automobile braking systems, medical devices.
    * **Key Logic:** It doesn't matter how "fast" it is; it matters that it is **predictable (Deterministic).**

---

### 🛡️ High Availability (HA) & Redundancy
* **The Goal:** Zero downtime.
* **Active/Passive:** One device (Firewall A) does all the work. If it dies, the "Passive" one (Firewall B) wakes up and takes over.
* **Active/Active:** Both devices work at the same time, sharing the load. If one dies, the other just takes on the full 100%.
* **Failover:** The automatic process of moving to the "next best thing" when a failure is detected.

---

### ⚠️ The "Difficult Factor": The "Single Point of Failure"
* **The Concept:** If you have two firewalls but they both plug into the **same** power outlet, that outlet is your "Single Point of Failure." 
* **The Pro Move:** True High Availability means redundant power, redundant ISP links, and redundant hardware.

---

# Domain 3.0: Security Architecture
## 3.1 IoT, Embedded Systems, and Virtualization

> [!ABSTRACT]
> Not every "computer" has a screen and a keyboard. Security must extend to specialized hardware and virtual environments.

---

### 🏭 SCADA / ICS (Industrial Control Systems)
* **What it is:** The tech that runs power plants, water treatment, and factories.
* **The "Difficult Factor":** These systems are often **OLD** (20+ years) and cannot be rebooted or patched without stopping a city's power.
* **Security Strategy:** **Isolation.** You never connect a SCADA system directly to the internet. You "Air Gap" it or use extreme segmentation.

---

### 🏠 IoT & Embedded Systems
* **IoT (Internet of Things):** Smart lights, cameras, thermostats.
    * *The Risk:* They usually have weak security and "hardcoded" passwords. They are perfect for botnets.
* **Embedded Systems:** A computer designed for **one specific task** (e.g., a printer controller or a smart fridge).
* **The Pro Move:** Always put IoT devices on their own **Guest VLAN**. Don't let your smart lightbulb talk to your Database server.

---

### 💻 Virtualization (Hypervisors)
You already know this from running Ubuntu VMs, but here is the Exam Logic:

* **Type I (Bare Metal):** The hypervisor is the OS. It runs directly on the hardware. (Faster, more secure). *Examples: VMware ESXi, Proxmox.*
* **Type II (Hosted):** The hypervisor runs as an app on top of Windows/macOS. *Example: VirtualBox.*
* **Containerization (Docker):** Instead of virtualizing the whole hardware, you only virtualize the **App**. 
    * *Benefit:* Much faster and uses less RAM than a full VM.

---

### ⚠️ The "Difficult Factor": VM Escape
* **The Concept:** A "VM Escape" is a nightmare scenario where an attacker hacks a Virtual Machine and then "jumps" out of it to take control of the physical host server. 
* **The Fix:** Keep the Hypervisor patched and use **Sandboxing**.

---

# Domain 3.0: Security Architecture
## 3.1 Availability, Resilience, and Resource Management

> [!ABSTRACT]
> Security isn't just about blocking hackers; it's about keeping the business running ("Uptime") and making sure recovery is fast and cost-effective.

---

### 📉 Measuring Recovery (The Metrics)
* **MTTR (Mean Time to Repair):** How long does it actually take to fix a device once it breaks?
* **MTBF (Mean Time Between Failures):** How reliable is the hardware? 
* **The Goal:** Maximize MTBF (reliability) and minimize MTTR (repair speed).

---

### 💰 The Economics of Security
* **TCO (Total Cost of Ownership):** It’s not just the price of the server. It includes power, cooling, taxes, and the salary of the IT person (like you!) managing it.
* **Cybersecurity Insurance:** A financial "fail-safe." It won't stop the hack, but it helps pay for the recovery and legal fees after a ransomware attack.

---

### 🎈 Scalability vs. Elasticity (Cloud Logic)
* **Scalability:** The *ability* to handle growth (adding more "horsepower" to a server).
* **Elasticity:** The *automation* of that growth. 
	* *Example:* Your web server automatically adds more RAM at 8 PM when traffic is high and shrinks back at 3 AM to save money. This prevents paying for "empty space."

---

### 🛠️ Maintenance & Patching
* **Corporate Images:** Instead of a slow 1-hour OS install, we use a "Golden Image." We "flash" the drive with a pre-configured, secure OS in 10 minutes.
* **The Patch Gap:** If a system (like an AC unit or an old time clock) can't be patched, it's a **Legacy System**. 
	* *Security Move:* Put these on a separate, isolated VLAN so they can't infect the rest of the network.

---

### ⚡ Power & Hardware
* **UPS (Uninterruptible Power Supply):** A battery backup that keeps the server alive for a few minutes during a blackout—long enough to shut it down safely or switch to a generator.
* **GPU Offloading:** Using the GPU for heavy math (like encryption or AI) to keep the CPU free for general tasks.

---

# Domain 3.0: Security Architecture
## 3.1 & 3.2 Network Zones and Attack Surface Management

> [!ABSTRACT]
> Security is about "Layers." We don't just rely on a firewall; we minimize the ways to get in (Attack Surface) and group our assets into "Zones" based on how much we trust them.

---

### 🏰 Security Zones (The Trust Hierarchy)
We move traffic between zones based on specific rules. 

* **Untrusted Zone:** The Public Internet. Dangerous territory.
* **Screened Subnet (DMZ):** The "Lobby." This is where your Web Servers live. They talk to the Internet, but they are kept away from your private data.
* **Trusted Zone:** Your internal private network. This is where employee workstations and internal files live.
* **The Flow:**
    * **Untrusted ⮕ Screened:** (Safe) People viewing your website.
    * **Screened ⮕ Trusted:** (Strictly Monitored) The web server asking the database for info.
    * **Untrusted ⮕ Trusted:** (Forbidden) Never allow the internet direct access to your private database.

---

### 🛡️ Minimizing the "Attack Surface"
**The Home Analogy:** A house with 1 door and 2 windows is easier to defend than a house with 10 doors and 50 windows.

* **Hardening:** Closing every "window" (port/service) that isn't needed. If you aren't using Port 21 (FTP), shut it down.
* **Human Error:** The "Unlocked Door." Training and strict permissions (Least Privilege) prevent people from making mistakes that let attackers in.
* **Code Vulnerabilities:** Making sure the "locks" (the application code) aren't broken from the factory.

---

### 🔒 Connectivity & Encryption
When data leaves your "Home" (Network), it needs a bodyguard.

1. **Network Level (The Tunnel):** * **VPN / IPsec:** Encrypts the entire "pipe." Everything inside is hidden. Great for connecting your Jeddah office to a cloud server in Dubai.
2. **Application Level (The Package):**
   * **HTTPS / SSH:** Encrypts the specific message. Even if someone sees the packet, they can't read the contents.
3. **Physical Level:**
   * **Protected Cabling:** Using metal conduits for ethernet cables so hackers can't physically "tap" the wire to steal data.

![](../../Pasted%20image%2020260420035709.png)

---

