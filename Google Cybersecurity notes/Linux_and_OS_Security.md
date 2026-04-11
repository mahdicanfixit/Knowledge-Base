
*Back to [[Cybersecurity_Knowledge_Base]]*
# Linux & Operating System Security

## 1. Hardware & Boot Process
* **Hardware:** The physical components.
* **Booting:** The startup process.
    * **BIOS:** Basic Input/Output System (Older chip). Vulnerable to malware as antivirus often skips it.
    * **UEFI:** Unified Extensible Firmware Interface (Newer, more secure replacement since ~2007).

## 2. Linux Architecture

* **Kernel:** The core of the OS. Manages memory and CPU processes.
* **Shell:** The command-line interpreter (e.g., **Bash**). It translates your text commands into machine language.
* **FHS (Filesystem Hierarchy Standard):** The structure of folders (directories) in Linux.
    * **Root (`/`):** The highest-level directory.

### Distributions (Distros)
* **Debian Family:** Includes **Ubuntu** and **Kali Linux**.
* **Red Hat Family:** Includes CentOS and Fedora.

### Kali Linux & Security Tools
A specialized distribution for **Penetration Testing** (simulating attacks to find flaws) and **Digital Forensics**.
* **Metasploit:** Framework for exploiting vulnerabilities.
* **Burp Suite:** Web application security testing.
* **John the Ripper:** Password cracking.
* **Wireshark/Tcpdump:** Packet analysis.
* **Autopsy:** Digital forensics platform.

---

## 3. The Linux Command Line (CLI)

### Navigation & File Management
| Command | Description | Example |
| :--- | :--- | :--- |
| `pwd` | **P**rint **W**orking **D**irectory. Shows where you are. | `pwd` |
| `ls` | **L**i**s**t files. | `ls -la` (Lists hidden + details) |
| `cd` | **C**hange **D**irectory. | `cd /home/user` |
| `mkdir` / `rmdir` | Make / Remove directory. | `mkdir new_folder` |
| `touch` | Create an empty file. | `touch notes.txt` |
| `cp` | **C**o**p**y a file. | `cp file.txt /backup/` |
| `mv` | **M**o**v**e (or rename) a file. | `mv old.txt new.txt` |
| `rm` | **R**e**m**ove (delete) a file. | `rm junk.txt` |
| `cat` | View file content. | `cat passwords.txt` |

### Search & Manipulation
| Command | Description | Example |
| :--- | :--- | :--- |
| `grep` | Search for a specific text string inside a file. | `grep "error" log.txt` |
| `|` (Pipe) | Sends output of one command to another. | `cat log.txt | grep "error"` |
| `echo` | Prints text to the screen. | `echo "Hello World"` |
| `man` | **Man**ual. Shows help for a command. | `man ls` |

---

## 4. Permissions & Users

### User Management
* **Root:** The "Superuser" or Administrator. High risk if compromised.
* **Sudo:** "SuperUser DO". Temporarily grants root permissions.
    * *Best Practice:* Log in as a normal user, use `sudo` only when needed.

### File Permissions (chmod)
Permissions are assigned to **U**ser (Owner), **G**roup, and **O**thers.
* **R (Read):** Can view contents.
* **W (Write):** Can modify contents.
* **X (Execute):** Can run the file as a program.

**Command:** `chmod` (Change Mode)
* Syntax: `chmod [Who][+/-][Permission] [File]`
* *Example:* `chmod g-w file.txt` (Remove **w**rite permission from the **g**roup).
