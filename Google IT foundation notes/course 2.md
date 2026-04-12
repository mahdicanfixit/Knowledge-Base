### 🌐 Course 2: Bits & Bytes of Computer Networking

_Building the foundation for Network+ and understanding the "Plumbing" of the Internet._

#### 🏗️ The TCP/IP 5-Layer Model

_Understanding the flow from physical pulses to application data._

- **L1 - Physical:** The hardware. Bits over copper, fiber, or radio waves.
    
- **L2 - Data Link:** Ethernet frames and **MAC Addresses**. This is where **Switches** live.
    
- **L3 - Network:** The "GPS" of the model. **IP Addresses**, Subnetting (CIDR), and **Routers**.
    
    - _Key Protocol:_ **ARP** (Mapping the MAC address to an IP).
        
- **L4 - Transport:** The "Traffic Controller."
    
    - **TCP:** Reliable, connection-oriented, and uses the **3-way handshake** (SYN, SYN-ACK, ACK).
        
    - **UDP:** Fast, connectionless, and used for streaming/gaming where speed beats accuracy.
        
- **L5 - Application:** The human interface. Protocols like HTTP, DNS, and DHCP.
    

#### 🔢 Addressing & Subnetting

- **IPv4:** Dotted decimal format. Understanding how **Subnet Masks** define the size of a network.
    
- **NAT (Network Address Translation):** How my home router hides multiple private IPs behind a single public one.
    
- **IPv6:** The future—moving from 32-bit to 128-bit addresses to handle the billions of new devices.
    

#### 🛠️ Port & Protocol Cheat Sheet

_Crucial for both IT Support and Security analysis._

- **DNS (53):** Resolving names to IPs.
    
- **HTTP (80) / HTTPS (443):** Web traffic.
    
- **SSH (22):** Secure remote management.
    
- **RDP (3389):** Windows Remote Desktop.
    
- **DHCP (67/68):** Automatic IP assignment.
    

#### 🔍 Diagnostic Toolkit

- `ping`: Testing basic connectivity via ICMP.
    
- `traceroute`: Mapping the "hops" a packet takes across the globe.
    
- `nslookup / dig`: Querying DNS servers to verify records.

---

### 📝 My Personal "Net" Notes

- **Networking is deep:** This was the toughest module for me to wrap my head around. I spent extra time in **Packet Tracer** just to see the 3-way handshake happen in real-time.
    
- **The "Why":** Understanding how a switch differs from a router changed how I look at my own home setup. It’s not just "the Wi-Fi box"—it’s a multi-layered gateway.
    
- **Troubleshooting:** Now, when the internet is down, my first instinct isn't to restart the router; it's to `ping 8.8.8.8` and check the DNS resolution.