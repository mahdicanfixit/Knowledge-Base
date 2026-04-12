# Threats, Vulnerabilities, and History

## The Web Landscape

1.  **Surface Web:** Publicly accessible (News, Shopping).
2.  **Deep Web:** Requires authorization (Corporate Intranets).
3.  **Dark Web:** Requires special software (Tor); hub for illegal activity like data leaks.

## Malware & Attacks

### Ransomware
**Definition:** Malicious attack where actors encrypt data (Plaintext $\rightarrow$ Ciphertext) and demand payment for a decryption key.
* **Impacts:** Financial loss, Identity theft, Reputation damage.

### Social Engineering
* **Definition:** Manipulating human error to gain access.
* **Vishing:** Voice phishing (often exploiting VoIP or AI voice impersonation).
* **Phishing:** Deceptive emails (e.g., the *LoveLetter* attack).

## Historical Attacks (Timeline)

* **1986: Brain Virus**
    * *Origin:* Created by Alvi brothers to track illegal software copies.
    * *Method:* Spread via floppy disks; arguably the first PC virus.
* **1988: Morris Worm**
    * *Impact:* Crashed ~6,000 machines (10% of the internet at the time).
    * *Lesson:* Highlighted the need for network security.
* **2000: LoveLetter Malware (ILOVEYOU)**
    * *Method:* Email attachment "Love Letter For You".
    * *Impact:* Infected 45 million PCs. First major **Social Engineering** scale attack.
* **2017: Equifax Breach**
    * *Impact:* Stole records of 143 million people (40% of US population).
    * *Cost:* Equifax paid >$575 million in fines.

## Network Attacks

### Denial of Service (DoS)
Attacks designed to shut down a machine or network, making it inaccessible to its intended users.

* **SYN Flood:** Exploits the TCP "Handshake".
    * *Mechanism:* Attacker sends many `SYN` requests but never completes the handshake with `ACK`.
    * 
* **ICMP Flood:** Overwhelms the target with Echo Request (Ping) packets.
* **Ping of Death:** Sending a malformed packet larger than 64KB to crash the system.
* **DDoS (Distributed DoS):** Using a botnet (multiple devices) to flood the target.

### Spoofing & Interception
* **IP Spoofing:** Falsifying the Source IP address to mimic a trusted device.
    * *Smurf Attack:* A combination of Spoofing + DoS (flooding a victim by spoofing their IP to the network broadcast).
* **Packet Sniffing:**
    * *Passive:* Just reading/collecting data (loss of Confidentiality).
    * *Active:* Modifying data in transit (loss of Integrity).
* **On-Path Attack (Man-in-the-Middle):** Intercepting and relaying messages between two parties who believe they are communicating directly.
* **Replay Attack:** Intercepting a valid data transmission and repeating it later to gain unauthorized access.

---
*Back to [[Google Cybersecurity Knowledge Base]]*
--