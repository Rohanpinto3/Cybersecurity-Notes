
# Network based attack

---

Attack that targets communication on a network between system, rather than system themselves.

- exploits traffic flow or protocol or service that runs on network.
- large blast radius - one successful network attack can impact multiple users or devices.
- Impact on CIA :
    - C : eavesdrops on sensitive data
    - I : tampering with data in transit, impersonating
    - A : flooding networks  to knock on them offline ( ddos)

# **Network Reconnaissance, Scanning & Enumeration**

## **1. Reconnaissance (Recon) - "The Watch"**

**Goal:** Passive information gathering **without** touching the target.

**Methods:**

- **OSINT** (Open Source Intelligence):
    - `whois` domain lookups
    - Social media/LinkedIn (employee names)
    - Google dorking: `site:company.com filetype:pdf`
- **DNS Enumeration:**
    
    bash
    
    ```
    dig target.com ANY           # Get all DNS records
    host target.com              # Basic DNS lookup
    nslookup                     # DNS query tool
    ```
    

## **2. Scanning - "Knocking on Doors"**

**Goal:** Discover live hosts, open ports, services.

**Tools & Techniques:**

- **Ping Sweep:** Find live hosts
    
    bash
    
    ```
    nmap -sn 192.168.1.0/24      # Ping scan entire subnet
    ```
    
- **Port Scanning:** Find open doors
    
    bash
    
    ```
    nmap -sS 192.168.1.100       # Stealth SYN scan
    nmap -sV 192.168.1.100       # Version detection
    nmap -A 192.168.1.100        # Aggressive scan (OS + version)
    ```
    
- **Network Mapping:**
    
    bash
    
    ```
    netdiscover                   # Find local hosts
    ```
    

## **3. Enumeration - "Checking What's Inside"**

**Goal:** Gather detailed information about services and resources.

**Common Enumeration:**

- **SMB Shares** (Windows file sharing):
    
    bash
    
    ```
    smbclient -L //192.168.1.100    # List shares
    enum4linux 192.168.1.100        # Comprehensive SMB enum
    ```
    
- **HTTP/Web Services:**
    
    bash
    
    ```
    dirb http://192.168.1.100       # Directory brute force
    nikto -h http://192.168.1.100   # Web vulnerability scanner
    ```
    
- **SNMP** (Network devices):
    
    bash
    
    ```
    snmpwalk -c public 192.168.1.100  # SNMP enumeration
    ```
    

# **Common Network-Based Attacks**

## **1. Eavesdropping & Sniffing 👂**

**"Listening to conversations you shouldn't hear"**

**What:** Passively capturing network traffic

- **Methods:**
    - **Promiscuous Mode:** NIC captures ALL traffic, not just its own
    - **Switch Port Mirroring:** Copy traffic to your port (authorized)
    - **Wireless Sniffing:** Capture all WiFi frames in range

**Tools:**

bash

```
wireshark          # GUI packet analyzer
tcpdump            # Command-line packet capture
tshark             # Terminal version of Wireshark
```

**🔵 Blue Team Defense:**

- **Encryption** (HTTPS, SSH, VPNs) - makes sniffed data useless
- **Network Segmentation** - limits what can be overheard
- **Monitor for promiscuous mode** - detect unauthorized sniffers

---

## **2. Spoofing & MITM 🎭**

**"Pretending to be someone you're not"**

**What:** Actively manipulating communications

- **Types:**
    - **ARP Spoofing:** "I'm the gateway! Send traffic to me"
    - **DNS Spoofing:** "[google.com](https://google.com/) = 192.168.1.99 (my server)"
    - **IP Spoofing:** Fake source IP to bypass filters

**MITM Flow:**

1. Position between victim and target
2. Intercept all communications
3. Read/modify traffic without detection

**Tools:** `ettercap`, `arpspoof`

**🔵 Blue Team Defense:**

- **Dynamic ARP Inspection** (DAI) on switches
- **DNSSEC** for DNS integrity
- **Certificate Pinning** to prevent fake SSL certs
- **Monitor for ARP table anomalies**

---

## **3. DoS/DDoS 💥**

**"Overwhelming the target until it collapses"**

**What:** Make services unavailable to legitimate users

- **DoS** = One attacker
- **DDoS** = Many attackers (botnets)

**Common Methods:**

- **SYN Flood:** Send endless connection requests
- **UDP Flood:** Spam with UDP packets
- **HTTP Flood:** Overwhelm web servers with requests
- **Amplification Attacks:** Use protocols that generate large responses (DNS, NTP)

**🔵 Blue Team Defense:**

- **Rate Limiting** - block excessive requests
- **Cloudflare/Akamai** - DDoS protection services
- **Load Balancers** - distribute traffic
- **Anomaly Detection** - spot traffic spikes early
- **Blackhole Routing** - divert attack traffic to nowhere

# common  network based defense

<img width="1335" height="620" alt="image" src="https://github.com/user-attachments/assets/0116294b-3800-4f7a-aac5-0d49a4d5e99c" />
