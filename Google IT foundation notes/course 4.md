### 🏛️ Course 4: System Administration & IT Infrastructure

_Managing the scale, reliability, and security of organizational technology._

#### 🛠️ The SysAdmin Mindset

- **Core Responsibilities:** Provisioning hardware, user lifecycle management, server maintenance, and enforcing security policies.
    
- **The "Safety Net":** Designing backup strategies and disaster recovery plans to ensure 100% uptime.
    

#### 🌐 Critical Infrastructure Services

- **Networking Essentials:** * **DHCP:** Managing IP address pools (Static vs. Dynamic).
    
    - **DNS:** Configuring A-records, CNAMEs, and MX records (The "Phonebook" of the internet).
        
- **Server Roles:** Configuring File/Print sharing, and managing Web Servers (**Apache** for Linux, **IIS** for Windows).
    
- **Email Protocols:** Understanding the flow of mail via **SMTP** (Send), and **POP3/IMAP** (Receive).
    

#### 📁 Directory Services (Identity Management)

- **Active Directory (AD):** * Managing Users, Groups, and Organizational Units (OUs).
    
    - **Group Policy Objects (GPOs):** Pushing configurations and security restrictions across an entire Windows Domain.
        
- **LDAP:** Understanding the industry-standard protocol for accessing directory information.
    

#### ☁️ Cloud & Virtualization

- **Cloud Service Models:** * **IaaS:** Infrastructure (spinning up VMs in AWS/Azure).
    
    - **PaaS:** Platforms for developers.
        
    - **SaaS:** Software as a Service (Google Workspace, Office 365).
        
- **The Lab Environment:** Using Type-1 and Type-2 Hypervisors (**VMware/VirtualBox**) to build scalable testing environments.
    

#### 💾 Data Integrity & Redundancy

- **RAID:** Implementing hardware redundancy to survive disk failures.
    
- **Backup Strategy:** Balancing **Full** vs. **Incremental** backups.
    
    - _Rule #1: A backup isn't real until you've successfully performed a **Test Restore**._
        

---

### 📝 My Take on Infrastructure

- **Documentation is Life:** If you change a setting and don't write it down, you're setting a trap for your future self. I use Obsidian to make sure I never have to solve the same problem twice.
    
- **The "Change" Rule:** Always patch and update in a sandbox/dev environment first. Production is sacred.
    
- **Automation:** Whenever I find myself doing a task for the third time, I start looking for a way to automate it with a script.