# Network Security & Architecture

## 1. Network Basics

### Types of Networks
* **LAN (Local Area Network):** Spans a small area (Home, Office).
* **WAN (Wide Area Network):** Spans a large geographical area (City, Country).
* **Cloud Computing:** Using remote servers hosted on the internet rather than local devices.
    * *Cloud Service Providers* offer: Storage, Processing Power, Analytics.

### Network Hardware

1.  **Hub:** Broadcasts data to *every* device (dumb device).
2.  **Switch:** Sends data only to the specific intended device (intelligent device).
3.  **Router:** Connects multiple networks together (e.g., Your LAN $\leftrightarrow$ The Internet). reads destination IP addresses.
4.  **Modem:** Connects the router to the ISP (Internet Service Provider).

### Virtualization
Software that mimics hardware functions. It allows you to run multiple "virtual" network functions on a single physical server.

---

## 2. Data & Addressing

### Data Packets
The basic unit of information. Like a physical letter, it has three parts:
1.  **Header:** Contains Source/Dest IP, MAC address, and Protocol.
2.  **Body:** The actual message/data.
3.  **Footer:** Signals the end of the packet.

### IPv4 vs. IPv6

* **IPv4:** 32-bit address (e.g., `192.168.1.1`). Running out of addresses.
* **IPv6:** 128-bit alphanumeric address. Developed to solve address exhaustion.

### The IPv4 Header Structure

* **TTL (Time to Live):** A counter that lowers by 1 at every router to prevent infinite loops.
* **Flags:** Indicates if a packet is fragmented.
* **Source/Destination IP:** Where it came from and where it is going.
* **Header Checksum:** Detects corruption in transit.

---

## 3. Protocols & Models

### TCP/IP Model
The standard framework for communication.
1.  **Network Access Layer:** Hardware, cables, MAC addresses.
2.  **Internet Layer:** IP addresses, routing (LAN vs. WAN).
3.  **Transport Layer:** TCP/UDP, flow control, reliability.
4.  **Application Layer:** Where users interact (Email, File Transfer).

### Common Protocols
| Protocol | Port | Function |
| :--- | :--- | :--- |
| **TCP** | N/A | Reliable connection-oriented stream. |
| **IP** | N/A | Routing and addressing. |
| **ARP** | N/A | Finds the MAC address associated with an IP. |
| **DNS** | 53 | Translates names (google.com) to IPs (8.8.8.8). |
| **HTTPS** | 443 | Secure web browsing (Encrypted via SSL/TLS). |
| **SMTP** | 25 | Email transmission. |

---

## 4. Network Defense & Hardening

### Firewalls

* **Stateless:** Filters based on static rules (e.g., "Block Port 80").
* **Stateful:** Tracks the *context* of active connections.
* **NGFW (Next-Gen Firewall):** Adds Deep Packet Inspection (DPI) and Intrusion Prevention.

### Segmentation & Zones
Dividing the network to limit access.
* **DMZ (Demilitarized Zone):** A buffer zone between the Public Internet (Uncontrolled) and the Private Network (Controlled).
* **Proxy Server:**
    * *Forward Proxy:* Regulates user access *out* to the internet.
    * *Reverse Proxy:* Regulates internet access *in* to internal servers.

### VPN (Virtual Private Network)
* **Function:** Hides IP and encrypts data on public networks.
* **Mechanism:** Uses **Encapsulation** (wrapping a packet inside another packet) to create a secure tunnel.

### Defense Tools Comparison
| Tool | Action | Scope |
| :--- | :--- | :--- |
| **Firewall** | Blocks/Allows | Header-based rules. |
| **IDS** (Detection) | Alerts only | Scans for known attacks. |
| **IPS** (Prevention) | Stops attacks | Inline active blocking. |
| **SIEM** | Aggregates Logs | Centralized monitoring/reporting. |

---
*Back to [[Cybersecurity_Knowledge_Base]]*