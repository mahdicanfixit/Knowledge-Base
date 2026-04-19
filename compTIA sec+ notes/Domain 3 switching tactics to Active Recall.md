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

