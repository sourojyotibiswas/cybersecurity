# Nmap

## **Timing Templates in Nmap Scan**

Nmap provides several timing templates to control the speed and aggressiveness of the scan. These templates range from `-T0` (paranoid) to `-T5` (insane). Here is a brief overview:

- `-T0` (Paranoid): Very slow, useful for avoiding detection.
- `-T1` (Sneaky): Slow, useful for avoiding detection.
- `-T2` (Polite): Slower than default, useful for reducing load on the network.
- `-T3` (Normal): Default timing, balanced between speed and stealth.
- `-T4` (Aggressive): Faster than default, may be detected.
- `-T5` (Insane): Very fast, likely to be detected.

Here's a **clean, categorized, and efficient reference sheet of Nmap commands** tailored for your OSCP prep. It merges your commands with the content from the uploaded file, adds helpful notes, and prioritizes utility and clarity for pentesting use cases.

---

## 🛠️ **Nmap Command Reference for OSCP**

---

### 🔹 1. Target Discovery (Host Enumeration)

| Command                         | Purpose                                         |
| ------------------------------- | ----------------------------------------------- |
| `nmap -sn 10.0.0.1`             | Ping scan – check if host is up (no port scan). |
| `nmap -sn 10.0.0.1-50`          | Scan a range of IPs.                            |
| `nmap -sn 10.0.0.0/24`          | Scan a subnet.                                  |
| `nmap -sn -iL targets.txt`      | Read targets from file.                         |
| `nmap -sn --exclude 10.0.0.5`   | Exclude specific IPs.                           |
| `nmap -Pn 10.0.0.1`             | Skip host discovery (assumes host is up).       |
| `nmap -sn -PS 10.0.0.1`         | TCP SYN ping.                                   |
| `nmap -sn -PA 10.0.0.1`         | TCP ACK ping.                                   |
| `nmap -sn -PU 10.0.0.1`         | UDP ping.                                       |
| `nmap -sn -PR 10.0.0.1`         | ARP request (for LAN discovery).                |
| `nmap -sn --traceroute`         | Trace route to host.                            |
| `nmap -PE`, `-PP`, `-PM`, `-PO` | ICMP echo, timestamp, netmask, IP proto ping.   |

> **Use case**: Initial host up/down check before deeper scanning.

---

### 🔹 2. Port Scanning

| Command                                  | Purpose                         |
| ---------------------------------------- | ------------------------------- |
| `nmap -p 80 10.0.0.1`                    | Scan single port.               |
| `nmap -p 1-1000 10.0.0.1`                | Scan port range.                |
| `nmap -p- 10.0.0.1`                      | Scan all 65535 ports.           |
| `nmap -F 10.0.0.1`                       | Fast scan (top 100 ports).      |
| `nmap -p 53,67,123 -sU 10.0.0.1`         | UDP scan on specific ports.     |
| `nmap -F --exclude-ports 22,80 10.0.0.1` | Fast scan excluding some ports. |

> **Use case**: Understand open services; use full or fast depending on time.

---

### 🔹 3. Scan Techniques

| Command                       | Purpose                                           |
| ----------------------------- | ------------------------------------------------- |
| `nmap -sS 10.0.0.1`           | TCP SYN (Stealth) scan. Default, fast & reliable. |
| `nmap -sT 10.0.0.1`           | TCP connect scan (fallback when not root).        |
| `nmap -sU -p 161 10.0.0.1`    | UDP scan. Slower and noisier.                     |
| `nmap -sA -p 21 10.0.0.1`     | ACK scan (firewall detection).                    |
| `nmap -sN`, `-sF`, `-sX`      | Null, FIN, Xmas scans – for evading firewalls.    |
| `nmap -f -p 80 10.0.0.1`      | Fragmented packets – evade some filters.          |
| `nmap -mtu 24 -p 80 10.0.0.1` | Custom MTU to manipulate packet size.             |
| `nmap -D RND:10 10.0.0.1`     | Decoy scan – hide your real IP.                   |

> **Use case**: Use stealth techniques for bypassing detection; fallbacks for restricted environments.

---

### 🔹 4. Version & OS Detection

| Command                                   | Purpose                                             |
| ----------------------------------------- | --------------------------------------------------- |
| `nmap -sV 10.0.0.1`                       | Detect service versions.                            |
| `nmap -A 10.0.0.1`                        | Aggressive scan: OS, services, scripts, traceroute. |
| `nmap -O 10.0.0.1`                        | OS detection.                                       |
| `nmap -O --osscan-guess 10.0.0.1`         | Guess OS more aggressively.                         |
| `nmap -sV --version-intensity 5 10.0.0.1` | Aggressive service detection.                       |
| `nmap -sV --version-intensity 0 10.0.0.1` | Light banner grabbing.                              |

> **Use case**: Service fingerprinting and OS guessing for better exploit targeting.

---

### 🔹 5. Output Handling

| Command                        | Purpose               |
| ------------------------------ | --------------------- |
| `nmap -oN scan.txt 10.0.0.1`   | Normal output.        |
| `nmap -oG scan.grep 10.0.0.1`  | Greppable output.     |
| `nmap -oX scan.xml 10.0.0.1`   | XML output.           |
| `nmap -oA allformats 10.0.0.1` | All formats together. |

> **Use case**: Store scans for later analysis or parsing in tools.

---

### 🔹 6. NSE (Nmap Scripting Engine)

| Command                                 | Purpose                          |
| --------------------------------------- | -------------------------------- |
| `nmap -sV -sC 10.0.0.1`                 | Default scripts (safe & useful). |
| `nmap --script-help=ssl-heartbleed`     | Show script details.             |
| `nmap --script=ssl-heartbleed 10.0.0.1` | Check Heartbleed vuln.           |
| `nmap --script=http-title 10.0.0.1`     | Grab web page titles.            |
| `nmap --script=http-enum 10.0.0.1`      | Brute-force common web dirs.     |
| `nmap --script=smb* 10.0.0.1`           | Run all SMB-related scripts.     |

> **Use case**: Powerful extension for vuln discovery, brute forcing, enum, etc.

---

### 🔹 7. HTTP/HTTPS Recon

| Command                               | Purpose                       |
| ------------------------------------- | ----------------------------- |
| `nmap --script=http-title 10.0.0.1`   | Enumerate titles of websites. |
| `nmap --script=http-headers 10.0.0.1` | Grab HTTP headers.            |
| `nmap --script=http-enum 10.0.0.1`    | Discover common web paths.    |

> **Use case**: Quick web recon before using tools like Dirb, Nikto, etc.

---

### 🔹 8. Vulnerability/Exploitation-Oriented Scans

| Command                                                                                             | Purpose                                |
| --------------------------------------------------------------------------------------------------- | -------------------------------------- |
| `nmap -sV --script=ssl-heartbleed -p 443 10.0.0.1`                                                  | Detect Heartbleed.                     |
| `nmap -sU -A -Pn -n -pU:19,53,123,161 --script=ntp-monlist,dns-recursion,snmp-sysdescr 10.0.0.0/24` | Detect reflection-based DDoS services. |

> **Use case**: Identify vulnerable services that can be used for exploits or misconfigurations.

---

### 🔹 9. IP Intelligence & Info Gathering

| Command                                                         | Purpose                         |
| --------------------------------------------------------------- | ------------------------------- |
| `nmap --script=asn-query,whois,ip-geolocation-maxmind 10.0.0.1` | Basic IP recon/intel gathering. |

> **Use case**: Add context to IPs during OSCP reporting or targeting external infrastructure.

---

### 🔍 **1. Fast & Quiet Top Port Scan with Output**

```bash
nmap -T4 -F --open --min-rate=1000 -oA quick-scan 10.0.0.1
```

- **`-T4`**: Faster timing
- **`-F`**: Top 100 ports
- **`--open`**: Only show open ports
- **`--min-rate`**: Increase packet rate
- **`-oA`**: All output formats
  > Great for quick sweeps without raising alerts.

---

### 🧠 **2. Full TCP + Version + Default NSE + Output**

```bash
nmap -sS -sV -sC -p- -T4 -oA full-tcp 10.0.0.1
```

- Full port scan + service enum + default scripts
  > One of the most used **OSCP scan combos**.

---

### 👣 **3. UDP + Vulnerability Detection**

```bash
nmap -sU -sV --top-ports 20 --script=default,vuln -T4 -oA udp-vuln 10.0.0.1
```

- UDP scan + service version + vuln scripts
  > Useful for finding open SNMP, NTP, DNS, TFTP, etc.

---

### 🌐 **4. Web Recon with Aggressive Scripts**

```bash
nmap -p80,443 -sV --script=http-enum,http-title,http-methods,http-headers -oN web-recon.txt 10.0.0.1
```

> Perfect initial recon for HTTP/HTTPS services.

---

### 🛡️ **5. Firewall/IDS Evasion**

```bash
nmap -sS -Pn -f -D RND:10 --data-length 50 -p80,443 10.0.0.1
```

- Fragment packets, spoof decoys, increase payload length
  > Helps evade weak IDS systems.

---

### 📡 **6. SMB Recon (Great for OSCP AD Machines)**

```bash
nmap -p 139,445 -sC -sV --script=smb-enum-shares,smb-enum-users,smb-os-discovery -oN smb-scan.txt 10.0.0.1
```

> Commonly helps in escalating or pivoting in AD networks.

---

### 🧨 **7. All-Purpose Vuln Discovery Scan**

```bash
nmap -sS -sV --script=vuln -T4 -p- -oA vuln-scan 10.0.0.1
```

- Runs vulnerability scan across all ports + service version
  > Use when you need fast attack surface assessment.

---
