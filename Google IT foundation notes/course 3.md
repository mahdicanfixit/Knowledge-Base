### 🖥️ Course 3: Operating Systems & Power User

_A deep dive into managing Windows and Linux environments via GUI and CLI._

#### ⌨️ Command Line Navigation (The Basics)

|Action|Windows (PowerShell/CMD)|Linux (Bash)|
|---|---|---|
|**List Files**|`dir`|`ls`|
|**Change Dir**|`cd`|`cd`|
|**Create Folder**|`mkdir`|`mkdir`|
|**Delete File**|`del`|`rm`|
|**Copy File**|`copy`|`cp`|
|**Search/Filter**|`findstr`|`grep`|

#### 🔐 Users, Groups & Permissions

- **Privilege Management:** Understanding the jump from Standard User to **Admin (Windows)** or **Root (Linux)**.
    
- **Windows:** Managing **UAC (User Account Control)** and NTFS permissions via the Security tab.
    
- **Linux Permissions:** Mastering `chmod` (e.g., `755` for scripts) and `chown` for ownership. Using `sudo` for administrative execution.
    

#### 📦 Software & Package Management

- **Windows:** Installing via `.exe`/`.msi` or using `winget` for CLI-based installs.
    
- **Linux:** Managing the software lifecycle with `apt` (update, upgrade, install, remove) and managing third-party repositories.
    

#### 📂 Filesystems & Storage

- **Structure:** Windows (**NTFS/FAT32**) vs. Linux (**ext4/BTRFS**).
    
- **Maintenance:** Formatting, partitioning, and mounting drives via `mount/umount`.
    
- **Space Analysis:** Using `df -h` (Disk Free) and `du -sh` (Disk Usage) to find storage hogs.
    

#### ⚙️ Process & System Monitoring

- **Monitoring:** Using **Task Manager/Resource Monitor** (Win) and `top`/`htop` (Linux) to identify resource spikes.
    
- **Termination:** Using `taskkill` or the "Nuclear Option" in Linux: `kill -9 [PID]`.
    
- **Troubleshooting Logs:** Analyzing the **Windows Event Viewer** and navigating `/var/log` (e.g., `auth.log`, `syslog`) in Linux.
    

#### 🌐 Remote Access & Virtualization

- **Secure Shell (SSH):** Remote CLI management for Linux servers.
    
- **RDP:** Remote Desktop Protocol for Windows troubleshooting.
    
- **Hypervisors:** Running VMs to test "breaking" things without crashing the host OS.
    

---

### 💡 Mahdi's Hands-On Tips

- **Pipes (`|`):** My favorite way to work—taking the output of one command and shoving it into another (like `cat log.txt | grep "Error"`).
    
- **Snapshots:** Always take a snapshot of a VM before running a `sudo rm -rf` or a major update. It saves hours of rebuilding.
    
- **The "Man" Pages:** If you forget a flag in Linux, `man [command]` is your best friend.