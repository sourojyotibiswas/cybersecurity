## 🔎 **Common port numbers, their associated services, and the protocols they use:**

| **Port Number** | **Service Name**         | **Protocol (TCP/UDP)** | **Description**                                                                                       |
| --------------- | ------------------------ | ---------------------- | ----------------------------------------------------------------------------------------------------- |
| 20              | FTP Data                 | TCP                    | File Transfer Protocol (Data Channel)                                                                 |
| 21              | FTP Control              | TCP                    | File Transfer Protocol (Control Channel)                                                              |
| 22              | SSH                      | TCP                    | Secure Shell for secure remote login and other secure network services                                |
| 23              | Telnet                   | TCP                    | Unencrypted text communications; deprecated due to security concerns                                  |
| 25              | SMTP                     | TCP                    | Simple Mail Transfer Protocol for email routing between mail servers                                  |
| 53              | DNS                      | TCP/UDP                | Domain Name System for translating domain names to IP addresses                                       |
| 67              | DHCP Server              | UDP                    | Dynamic Host Configuration Protocol (Server) for assigning IP addresses to clients                    |
| 68              | DHCP Client              | UDP                    | Dynamic Host Configuration Protocol (Client)                                                          |
| 69              | TFTP                     | UDP                    | Trivial File Transfer Protocol, a simplified version of FTP                                           |
| 80              | HTTP                     | TCP                    | Hypertext Transfer Protocol for web traffic                                                           |
| 110             | POP3                     | TCP                    | Post Office Protocol v3 for retrieving emails from a server                                           |
| 123             | NTP                      | UDP                    | Network Time Protocol for clock synchronization between computer systems                              |
| 135             | RPC                      | TCP/UDP                | Microsoft Remote Procedure Call                                                                       |
| 137             | NetBIOS Name Service     | TCP/UDP                | NetBIOS over TCP/IP for name resolution in Windows networks                                           |
| 138             | NetBIOS Datagram Service | UDP                    | NetBIOS over TCP/IP for datagram messaging in Windows networks                                        |
| 139             | NetBIOS Session Service  | TCP                    | NetBIOS over TCP/IP for session services in Windows networks                                          |
| 143             | IMAP                     | TCP                    | Internet Message Access Protocol for accessing emails on a remote server                              |
| 161             | SNMP                     | UDP                    | Simple Network Management Protocol for network management                                             |
| 162             | SNMP Trap                | UDP                    | SNMP Trap for sending alerts and notifications                                                        |
| 179             | BGP                      | TCP                    | Border Gateway Protocol for exchanging routing information between systems on the internet            |
| 389             | LDAP                     | TCP/UDP                | Lightweight Directory Access Protocol for accessing and maintaining distributed directory information |
| 443             | HTTPS                    | TCP                    | HTTP Secure for secure web traffic over SSL/TLS                                                       |
| 445             | SMB                      | TCP                    | Server Message Block for file sharing in Windows networks                                             |
| 465             | SMTPS                    | TCP                    | SMTP over SSL/TLS for secure email transmission                                                       |
| 514             | Syslog                   | UDP                    | System Logging Protocol for message logging                                                           |
| 515             | LPD                      | TCP                    | Line Printer Daemon for printer spooling                                                              |
| 520             | RIP                      | UDP                    | Routing Information Protocol for network routing                                                      |
| 587             | SMTP (Submission)        | TCP                    | Email message submission (SMTP) with STARTTLS                                                         |
| 636             | LDAPS                    | TCP                    | Secure LDAP over SSL                                                                                  |
| 993             | IMAPS                    | TCP                    | IMAP over SSL for secure email retrieval                                                              |
| 995             | POP3S                    | TCP                    | POP3 over SSL for secure email retrieval                                                              |
| 1433            | Microsoft SQL Server     | TCP                    | Microsoft SQL Server database management system                                                       |
| 1521            | Oracle Database          | TCP                    | Oracle database system                                                                                |
| 3306            | MySQL                    | TCP                    | MySQL database system                                                                                 |
| 3389            | RDP                      | TCP                    | Remote Desktop Protocol for remote desktop access                                                     |
| 5432            | PostgreSQL               | TCP                    | PostgreSQL database system                                                                            |
| 5900–5903       | VNC                      | TCP                    | Virtual Network Computing for remote desktop access                                                   |
| 6379            | Redis                    | TCP                    | Redis in-memory data structure store                                                                  |
| 8080            | HTTP Alternate           | TCP                    | Alternative port for HTTP services                                                                    |
| 8443            | HTTPS Alternate          | TCP                    | Alternative port for HTTPS services                                                                   |
| 9000            | SonarQube                | TCP                    | SonarQube code quality and security analysis server                                                   |
| 9090            | Prometheus               | TCP                    | Prometheus monitoring system and time series database                                                 |
| 9100            | JetDirect                | TCP                    | Printing over IP for network printers                                                                 |
| 9200            | Elasticsearch            | TCP                    | Elasticsearch search engine                                                                           |
| 11211           | Memcached                | TCP/UDP                | Memcached distributed memory object caching system                                                    |
| 27017           | MongoDB                  | TCP                    | MongoDB NoSQL database system                                                                         |
| 5000–5001       | Docker Registry          | TCP                    | Docker container registry service                                                                     |
| 5672            | AMQP                     | TCP                    | Advanced Message Queuing Protocol used by RabbitMQ                                                    |
| 15672           | RabbitMQ Management      | TCP                    | RabbitMQ management console                                                                           |
| 27015–27050     | Steam Gaming             | TCP/UDP                | Ports used by Steam for gaming traffic                                                                |
| 25565           | Minecraft Server         | TCP                    | Default port for Minecraft server                                                                     |
| 8000–8001       | Internet Radio           | TCP                    | Ports commonly used for internet radio streams                                                        |
| 8888            | HTTP Alternate           | TCP                    | Alternative port for HTTP services                                                                    |
| 9092            | Apache Kafka             | TCP                    | Apache Kafka messaging system                                                                         |
| 1883            | MQTT                     | TCP                    | Message Queuing Telemetry Transport for IoT communication                                             |
| 8883            | MQTTS                    | TCP                    | Secure MQTT over SSL/TLS                                                                              |
| 4789            | VXLAN                    | UDP                    | Virtual Extensible LAN for network virtualization                                                     |
| 5353            | mDNS                     | UDP                    | Multicast DNS for service discovery                                                                   |
| 1900            | SSDP                     | UDP                    | Simple Service Discovery Protocol                                                                     |
| 2049            | NFS                      | TCP/UDP                | Network File System for distributed file sharing                                                      |
| 111             | RPCbind                  | TCP/UDP                | Open Network Computing Remote Procedure Call (ONC RPC)                                                |
| 5357            | WSDAPI                   | TCP                    | Web Services for Devices API                                                                          |
| 49152–65535     | Ephemeral Ports          | TCP/UDP                | Dynamic/private ports for client-side communications                                                  |

**Notes:**

- **Ephemeral Ports (49152–65535):** These are dynamic or private ports that are typically assigned temporarily for client-side communications. They are not associated with

Great! Here's a **cybersecurity-focused, robust layer-wise protocol list**, tailored for documentation, compliance auditing, threat modeling, and pen-testing reference. It includes **attack surfaces**, **common vulnerabilities**, and **security tools/protocol hardening notes** where relevant.

---

## 🧱 **Layer-Wise Protocols**

### 📡 **1. Physical Layer (OSI Layer 1)**

**Focus**: Signal transmission, hardware interfaces  
**Attack Surface**: Physical tampering, hardware implants, signal jamming

| **Protocol/Standard** | **Use**                    | **Security Notes**                            |
| --------------------- | -------------------------- | --------------------------------------------- |
| Ethernet (IEEE 802.3) | LAN cabling and data       | Use port security, cable shielding            |
| Wi-Fi (IEEE 802.11)   | Wireless communication     | Enforce WPA3, disable WPS                     |
| DSL, Fiber, ISDN      | Internet over copper/fiber | Protect access points                         |
| USB, RS-232           | Peripheral data transfer   | Disable unused ports, use device whitelisting |

---

### 🔌 **2. Data Link Layer (OSI Layer 2)**

**Focus**: Frame transfer between nodes  
**Attack Surface**: MAC spoofing, ARP poisoning, VLAN hopping

| **Protocol**  | **Use**                     | **Security Notes**                                       |
| ------------- | --------------------------- | -------------------------------------------------------- |
| ARP           | IP to MAC resolution        | Mitigate ARP poisoning with dynamic ARP inspection (DAI) |
| Ethernet II   | Framing format              | Monitor traffic with Wireshark/tshark                    |
| PPP           | Serial point-to-point links | Use EAP authentication                                   |
| VLAN (802.1Q) | Network segmentation        | Use ACLs, prune unused VLANs                             |
| STP (802.1D)  | Loop prevention             | Enforce BPDU Guard                                       |

---

### 🌐 **3. Network Layer (OSI Layer 3)**

**Focus**: Routing, logical addressing  
**Attack Surface**: IP spoofing, routing attacks, DoS via ICMP

| **Protocol** | **Use**                       | **Security Notes**                                     |
| ------------ | ----------------------------- | ------------------------------------------------------ |
| IPv4/IPv6    | Routing packets               | Apply ingress/egress filtering                         |
| ICMP         | Diagnostic (ping, traceroute) | Limit rate, disable unnecessary types (e.g., redirect) |
| IGMP         | Multicast group management    | Disable if unused                                      |
| IPsec        | Secure IP communication       | Use AH/ESP for encrypted/authenticated comms           |
| BGP          | Internet routing              | BGP hijacking protection with RPKI                     |
| OSPF/RIP     | Internal routing              | Use MD5 authentication                                 |

---

### 📦 **4. Transport Layer (OSI Layer 4)**

**Focus**: End-to-end connections, flow control  
**Attack Surface**: Port scanning, TCP hijacking, DoS

| **Protocol** | **Use**                 | **Security Notes**                  |
| ------------ | ----------------------- | ----------------------------------- |
| TCP          | Reliable transport      | Use SYN cookies, monitor open ports |
| UDP          | Low-latency transport   | Monitor for amplification attacks   |
| SCTP         | Multi-stream transport  | Rarely used, monitor for anomalies  |
| DCCP         | Real-time data transfer | Use access control                  |

🛠️ Tools: `nmap`, `hping3`, `tcpdump`, `netstat`, `iptables`

---

### 🧑‍💻 **5. Session Layer (OSI Layer 5)**

**Focus**: Session control and authentication  
**Attack Surface**: Session hijacking, replay attacks

| **Protocol** | **Use**                   | **Security Notes**                        |
| ------------ | ------------------------- | ----------------------------------------- |
| NetBIOS      | Legacy Windows networking | Block or restrict                         |
| RPC          | Remote service calls      | Restrict via firewalls, use auth          |
| SMB          | File/printer sharing      | Use SMBv3 only, disable guest access      |
| PPTP         | VPN tunneling             | **Deprecated**, use IPsec/OpenVPN instead |

---

### 📂 **6. Presentation Layer (OSI Layer 6)**

**Focus**: Data formatting, encryption  
**Attack Surface**: Weak ciphers, padding attacks, downgrade attacks

| **Protocol**      | **Use**            | **Security Notes**                           |
| ----------------- | ------------------ | -------------------------------------------- |
| SSL/TLS           | Encrypted sessions | Use TLS 1.3+, disable SSLv2/3 & weak ciphers |
| MIME              | Email formatting   | Sanitize attachments                         |
| JPEG, MPEG, ASCII | Encoding formats   | Validate input to avoid malformed payloads   |

🛠️ Tools: `testssl.sh`, `sslscan`, `OpenVAS`, `Burp Suite`

---

### 🧠 **7. Application Layer (OSI Layer 7)**

**Focus**: Services like web, mail, DNS  
**Attack Surface**: XSS, SQLi, CSRF, DNS poisoning, RCE

| **Protocol**   | **Use**            | **Security Notes**                    |
| -------------- | ------------------ | ------------------------------------- |
| HTTP/HTTPS     | Web traffic        | Use HTTPS everywhere, enforce HSTS    |
| FTP/SFTP       | File transfer      | Disable plain FTP, use SCP/SFTP       |
| DNS            | Name resolution    | Use DNSSEC, monitor for tunneling     |
| SMTP/IMAP/POP3 | Email services     | Enforce SPF/DKIM/DMARC                |
| SSH            | Remote access      | Use key auth, disable root login      |
| SNMP           | Network monitoring | Use v3, restrict community strings    |
| LDAP/LDAPS     | Directory services | Use secure bind methods               |
| MQTT           | IoT messaging      | Authenticate clients, encrypt traffic |
| REST/SOAP      | API communication  | Use token-based auth, rate limiting   |

🛠️ Tools: `Burp Suite`, `Nikto`, `Dirb`, `OWASP ZAP`, `Metasploit`

---

### 🔐 **Extra Layer: Cryptographic Protocols** (cross-layer relevance)

| **Protocol** | **Use**                 | **Security Notes**                 |
| ------------ | ----------------------- | ---------------------------------- |
| TLS/SSL      | Web/app encryption      | Use strong ciphers only            |
| Kerberos     | Auth in Windows domains | Clock sync is critical             |
| GPG/PGP      | Email encryption        | Protect private keys               |
| SRTP         | VoIP encryption         | Encrypt media streams              |
| IPsec        | VPN & secure IP comms   | Use strong algorithms (AES, SHA-2) |

---

> _notes_: IANA(Internet Assigned Numbers Authority) only manage ports from 0-1023
