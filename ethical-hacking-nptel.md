# ⭐ WEEK-1 — ONE PAGE REVISION NOTES

*(Ethical Hacking • Pen Testing • Networking Basics • Switching • Virtual Circuits • Datagrams • OSI • TCP/IP • IP/TCP/UDP • Encapsulation)*

---

##  1. Introduction to Ethical Hacking (Lecture 1)

### What is Ethical Hacking? (pg. 3)

* Finding weaknesses & vulnerabilities by imitating malicious hackers.
* Also called: penetration testing / intrusion testing / red teaming.

### Penetration Test (pg. 4)

* Legal attempt to break into a network.
* Tester only reports findings, doesn’t give solutions.

### Security Test

* Includes analyzing policies & offering solutions.

### Key Terminologies (pg. 5)

* Hacking: showing computer expertise.
* Cracking: breaching system/software security.
* Spoofing: faking source IP.
* DoS: flooding a host to make it unavailable.
* Port Scanning: searching for vulnerabilities.

### How attackers gain access (pg. 6)

* Front door → password guessing/stealing
* Backdoors → left by developers
* Trojan Horses → hidden malware installing backdoors
* Software vulnerability exploitation → common & dangerous

### Once inside, attacker can… (pg. 7)

Modify logs, steal/destroy files, install backdoors, attack other systems.

### Pen-Testing Models (pg. 9–10)

* White Box: full info given
* Black Box: no info
* Grey Box: partial info
* Tiger Box: toolkit of OS + hacking tools for assessment

### Legal Restrictions (pg. 11–13)

* Access without permission → illegal
* Installing malware → illegal
* Laws vary by country; must know what’s allowed.

---

##  2. Networking Basics (Part-I) (Lecture 2)

### Computer Network (pg. 19)

Communication system connecting hosts for better connectivity, communication, resource sharing.

### Types of Networks (pg. 20)

* LAN: small area, faster, cheaper
* WAN: long distance, slower, expensive

### Data Communication Approaches (pg. 21)

1. Circuit Switching
2. Packet Switching

---

### Circuit Switching (pg. 22–24)

* Dedicated path established before communication.
* Three steps:

  1. Establish connection
  2. Transfer data
  3. Terminate connection
* Drawbacks: inefficient for bursty traffic, initial delay.

---

### Packet Switching (pg. 25–28)

* No dedicated path, links shared.
* Data broken into packets containing headers.
* Uses store-and-forward at each router.
* Advantages: better link utilization, handles bursty data, supports prioritization.

### Two packet switching models (pg. 29)

#### ✔ Virtual Circuits (pg. 30–32)

* Route established first.
* All packets follow same path.
* Nodes store virtual circuit tables.
* No dynamic routing.

#### ✔ Datagrams (pg. 35–37)

* No prior route.
* Each packet routed independently.
* Contains source & destination addresses.
* May arrive out-of-order; duplicates may exist.
* Faster for few packets; more flexible.

---

##  3. Layered Network Architecture (Lecture 3)

### 7-Layer OSI Model (pg. 42–45)

| Layer        | Purpose                       |
| ------------ | ----------------------------- |
| Application  | Interface for user apps       |
| Presentation | Data independence, encryption |
| Session      | Manage sessions               |
| Transport    | Reliable end-to-end delivery  |
| Network      | Routing of packets            |
| Data Link    | Framing, error & flow control |
| Physical     | Bit transmission              |

### Internetworking Devices (pg. 47)

* Hub: extends LAN
* Switch (Layer-2): connects LANs
* Router (Layer-3): connects LANs/WANs

---

##  4. TCP/IP Protocol Stack (Lecture 4 & 5)

### TCP/IP vs OSI (pg. 52–55)

TCP/IP 4-layer model:

1. Application
2. Transport (TCP/UDP)
3. Network (IP)
4. Data Link

### TCP/IP Characteristics (pg. 56–57)

* Based on datagrams
* Packets may take different routes
* Variable delay and ordering

---

### IP (Internet Protocol) (pg. 70–76)

#### IP Characteristics

* Connectionless
* Unreliable delivery
* Independent packets
* Fragmentation support
* Each packet carries source & destination IP

#### IP Header Fields

* VER: IP version
* HLEN: header length
* Total Length: up to 65,536 bytes
* Service Type: priority
* TTL: prevents loops (decrements each hop)
* Protocol: TCP/UDP/ICMP
* Identification, Flags, Offset: fragmentation
* Checksum: 1’s complement arithmetic

---

### TCP (Transmission Control Protocol) (pg. 61)

* Connection-oriented
* Reliable
* Splits and reassembles packets
* Retransmits lost packets
* Performs error control & flow control

### UDP (User Datagram Protocol) (pg. 62)

* Connectionless
* Unreliable
* Small messages (DNS, streaming)
* No splitting of packets
* Faster & simpler than TCP

---

###  Encapsulation (Important!) (pg. 64–65)

Data moves down the protocol stack → headers added.
Data moves up the stack → headers removed.

Example (TFTP):

* TFTP header → UDP header → IP header → Ethernet header.

---

## ⭐ SUPER QUICK EXAM SUMMARY

* Ethical hacking = legal vulnerability discovery.
* Pen testing models: white, black, grey, tiger box.
* Network types: LAN (fast), WAN (slow).
* Switching: Circuit (dedicated) vs Packet (shared).
* Packet switching models: Virtual Circuits vs Datagrams.
* OSI Layers: 7 layers with distinct functions.
* TCP/IP Layers: Application, Transport, Network, Data Link.
* IP: connectionless, unreliable, uses fragmentation & TTL.
* TCP vs UDP: reliable vs fast.
* Encapsulation = adding headers layer-by-layer.

---

# WEEK-2

---

##  Lecture 6 — IP Fragmentation & MTU

### 1. MTU (Maximum Transmission Unit)

* Every datalink/network has a maximum packet size limit (MTU).
* If the IP packet is larger than MTU → fragmentation is required.

### 2. Fragmentation

* Performed by routers.
* Reassembly happens only at the final destination host (in IP’s default method).
* Each fragment is treated as a separate IP packet.

### 3. IP header fields used in fragmentation

* Identification (ID): same for all fragments of a packet.
* Fragment Offset: where the fragment belongs; measured in units of 8 bytes.
* Flags (3 bits):

  * D bit (Don’t Fragment)
  * M bit (More Fragments → 1 = more fragments, 0 = last fragment)

### 4. Transparent Fragmentation

* Intermediate exit router reassembles fragments.
* Later networks are unaware that fragmentation happened.
* Drawbacks:

  * Must use the same exit router → reduces routing flexibility.
  * High overhead (counting fragments, etc.)

### 5. Non-Transparent Fragmentation (Used by IP)

* No reassembly at intermediate routers.
* Fragments travel independently.
* Reassembly done only at destination host.
* Advantage: supports multiple exit routers → higher throughput.
* Drawback: every fragment carries a 20-byte header → overhead.

---

##  Lecture 7 — IP Addressing & Classes

### 6. IP address basics

* IP address = 32 bits → dotted decimal W.X.Y.Z
* Divided into network portion + host portion (in classful model)

### 7. Class A

* Starts with 0xxxxxxx
* Range: 0–127
* Hosts: 16 million+
* Mask: 255.0.0.0

### 8. Class B

* Starts with 10xxxxxx
* Range: 128–191
* Hosts: 65,534
* Mask: 255.255.0.0

### 9. Class C

* Starts with 110xxxxx
* Range: 192–223
* Hosts: 254
* Mask: 255.255.255.0

### 10. Class D

* Multicast: 224–239

### 11. Class E

* Experimental: 240–255

### 12. Special Addresses

* Private:

  * Class A: 10.x.x.x
  * Class B: 172.16–31.x.x
  * Class C: 192.168.x.x
* Loopback: 127.x.x.x
* Broadcast: 255.255.255.255
* Default: 0.0.0.0

### 13. Network and Broadcast Address

* First address → network number (e.g., 118.0.0.0)
* Last address → directed broadcast (e.g., 118.255.255.255)

---

##  Lecture 8 — TCP, UDP & Ports

### 14. TCP (Transmission Control Protocol)

* Connection-oriented
* Reliable
* Uses sequence numbers & ACKs
* Full-duplex
* Stream-based communication
* Performs error control & flow control

### 15. UDP (User Datagram Protocol)

* Connectionless
* Unreliable
* Faster, simpler
* Used for DNS, VoIP, streaming
* Only 8-byte header

### 16. Port Numbers

* Size = 16 bits
* Identifies process-to-process communication
* Types of ports:

  * Well-known ports: 0–1023 (FTP→21, SMTP→25, HTTP→80)
  * Registered ports: 1024–49151
  * Ephemeral ports: temporary ports (>49152)

### 17. Association (5-tuple)

Defines a unique TCP/UDP connection:

* Protocol
* Local IP
* Local Port
* Remote IP
* Remote Port

---

##  Lecture 9 — TCP Header, 3-Way Handshake, UDP Header

### 18. TCP Header Fields (20-60 bytes header)

* Source port, destination port
* Sequence number
* Acknowledgement number
* Header length (HLEN)
* Window size
* Checksum
* Urgent pointer

### 19. TCP Flags

* SYN → request connection
* SYN+ACK → connection confirm
* ACK → acknowledge data
* FIN → terminate connection
* RST → reset connection
* URG → urgent pointer
* PSH → push data

### 20. TCP 3-Way Handshake

1. SYN
2. SYN + ACK
3. ACK

### 21. Half-Open Connection (DoS attack vector)

* Attackers flood server with SYN packets, never send ACK.
* Server’s connection table fills up → SYN Flood Attack.

### 22. UDP Header (8 byte header)

* Source port
* Destination port
* Length
* Checksum (optional in IPv4)

---

##  Lecture 10 — Subnetting, VLSM, CIDR

### 23. Subnetting

* Divides a network into smaller networks.
* Introduces a third part in addressing:

  * Network
  * Subnet
  * Host

### 24. Natural Masks (Classful Masks)

* Class A → 255.0.0.0
* Class B → 255.255.0.0
* Class C → 255.255.255.0

### 25. Subnet Masks

* Borrow host bits to create subnets
* More subnets → fewer hosts/subnet

### 26. VLSM (Variable Length Subnet Mask)

* Subnets of different sizes in the same network
* Allows efficient IP usage
* Example from PDF:

  * 192.203.17.0 divided using 255.255.255.128 → 2 subnets
  * Then further subnetting using 255.255.255.192

### 27. CIDR (Classless Inter-Domain Routing)

* Format: IP/prefix
* Removes concept of A/B/C classes
* Reduces routing table size
* Both subnetting & supernetting supported
* Rule:

  1. Block size must be power of 2
  2. Starting address must be multiple of block size

### 28. Classful networks in CIDR notation

* Class A → /8
* Class B → /16
* Class C → /24

---

## 🟩 Your Week-2 Revision Summary (Super Short for Last-Minute)

* IP fragmentation uses ID, Flags, Fragment Offset
* IP uses non-transparent fragmentation
* Class A/B/C → unicast, Class D → multicast, Class E → reserved
* Private IPs: 10.x, 172.16–31.x, 192.168.x
* TCP = reliable, UDP = fast
* Ports = 16 bits; 0–1023 well-known
* TCP flags: SYN, ACK, FIN, RST, PSH, URG
* 3-way handshake = SYN → SYN+ACK → ACK
* Subnetting borrows host bits
* VLSM = different mask sizes within same network
* CIDR = IP/prefix → classless model

---

# WEEK-3

---

##  Lecture 11 — Packet Delivery & Routing Methods

### 1. Two Internet Packet Delivery Types

* Direct Delivery – sender & receiver in same network
* Indirect Delivery – packet passes through 1 or more routers

### 2. Two Connection Options (Network Layer)

* Connection-oriented: route is established first
* Connection-less: each packet is independent (IP uses this)

### 3. Four Routing Methods

| Method                       | Key Idea                      | Notes                      |
| ---------------------------- | ----------------------------- | -------------------------- |
| Next-hop routing             | Router stores *only next hop* | Saves memory               |
| Network-specific routing     | Route stored per network      | Widely used                |
| Host-specific routing        | Route per host                | Large tables, rarely used  |
| Default routing              | Use default when no match     | Used in home routers, ISPs |

### 4. Routing Table Types

* Static – manually added, never changes
* Dynamic – automatically updated using routing protocols (RIP/OSPF/BGP)

### 5. Routing Table Fields

* Subnet mask
* Destination
* Next hop
* Interface (eth0, m0 etc.)
* Flags:

  * U = router up
  * G = destination in different network
  * H = host-specific
  * D/M = added/modified by redirection

---

##  Lecture 12 — RIP & OSPF

### 6. Autonomous System (AS)

* Group of routers under one administrative control
* Uses one *interior* protocol inside → RIP/OSPF
* Uses *exterior* protocol to communicate with other AS → BGP
* Each AS has a unique AS number

### 7. Classes of Routing Protocols

#### Interior (within AS)

* RIP
* OSPF

#### Exterior (between AS)

* BGP

### 8. RIP — Routing Information Protocol

#### RIP uses:

* Distance-vector algorithm
* Hop count metric
* Max hops = 15
* Frequent table updates
* Slow convergence

#### Problems:

* Routing loops
* Counting-to-infinity problem
* Slow response to failures
* Consumes bandwidth

### 9. OSPF — Open Shortest Path First

#### Characteristics:

* Link-state routing protocol
* Uses Dijkstra’s shortest path algorithm
* Builds complete topology map
* Supports metrics like delay, bandwidth, cost
* Uses Link-State Advertisements (LSAs)
* LSAs refreshed every 30 minutes
* Routers send “Hello” packets every 10 seconds
* Failure detected if no Hello for 40 seconds

#### OSPF messages:

1. Hello
2. Database Description
3. Link-State Request
4. Link-State Update
5. Link-State Acknowledgement

---

##  Lecture 13 — BGP (Border Gateway Protocol)

###  10. What is BGP?

* The main Internet routing protocol
* Exterior routing protocol (inter-AS)
* Runs on TCP port 179

#### Features:

* Distance-vector like protocol
* Contains complete routes
* Initially exchanges full table
* Later only incremental updates

###  11. BGP Message Types

1. OPEN – establish connection
2. UPDATE – advertise/withdraw routes
3. KEEPALIVE – maintain peer connection
4. NOTIFICATION – report errors

###  12. BGP Functional Procedures

* Neighbor Acquisition – establish peer relation
* Neighbor Reachability – ensure peers are alive
* Network Reachability – maintain reachable networks

---

##  Lectrue 14 — IPv6

###  13. Why IPv6?

*(Problems with IPv4 — PDF pg. 25–26)*

* 32-bit address space too small
* No real-time support
* Limited routing flexibility

---

###  14. Key Features of IPv6

* 128-bit address space
* Simplified 40-byte base header
* Uses extension headers for optional data
* Supports real-time traffic
* Supports anycast addressing
* More flexible addressing & routing

###  15. IPv6 Header Fields

* Version = 6
* Priority
* Flow label (QoS support)
* Payload length
* Next header
* Hop limit
* Source (128-bit)
* Destination (128-bit)

###  16. IPv6 Address Types

* Unicast – one device
* Multicast – group of devices
* Anycast – nearest device among a group

###  17. IPv6 Notation

* Colon-hexadecimal format
* Leading zeros can be compressed
* Consecutive zero blocks → "::"

Example:

```
7BD6:0:0:0:0:0:0:B6 = 7BD6::B6
```

---

###  18. IPv6 Transition Mechanisms

1. Dual Stack – IPv4 + IPv6 both supported
2. Tunneling – IPv6 packet inside IPv4
3. Header Translation – IPv4 ↔ IPv6 conversion

---

##  Lecture 15 — Routing Examples

###  19. Longest Prefix Match Rule

* Router selects the most specific subnet mask
* e.g., /26 is preferred over /24 for same address

###  20. How to determine output interface

You check:

1. Destination IP
2. Match with subnet mask
3. Choose the entry with largest number of matching bits
4. If none match → use default route

###  21. Practice includes:

* Matching destination to correct subnet
* Using tables with overlapping masks
* Using default route
* Using host-specific routes
* Calculating which interface gets the packet

---

##  SUPER QUICK REVISION (ULTIMATE SHORT NOTES)

* IP uses connection-less packet delivery
* Direct vs Indirect delivery
* Routing methods: next-hop, network-specific, host-specific, default
* Static vs Dynamic routing
* RIP = hop count, max 15, slow
* OSPF = link-state, Dijkstra, LSAs, fast
* AS = group managed by one authority
* BGP = inter-AS, TCP 179, UPDATE & KEEPALIVE
* IPv6 = 128-bit, extension headers, flow label, anycast
* IPv6 notation uses compression (::)
* Longest prefix match determines routing

---

#  WEEK-4

##  LECTURE 16 — LAB SETUP & VIRTUAL ENVIRONMENT

### 1. Hacking real systems is illegal

Practice only on virtual machines.

### 2. Hypervisor (Virtual Machine Monitor)

* Software that creates & runs multiple VMs
* Shares memory, CPU, disk, network of host
* Examples: VirtualBox, VMware
* Course uses VirtualBox

### 3. Kali Linux

* Debian-based penetration testing OS
* Contains 1000+ security tools: Nmap, Metasploit, Burp Suite
* Best OS for beginners in hacking labs

### 4. Victim Machines

* Metasploitable 2 → vulnerable Linux
* Metasploitable 3 → vulnerable Windows
* Windows XP / Windows 7 can also be used

### 5. VirtualBox Network Modes

* NAT → VM is isolated; gets virtual IP; only internet access
* Bridged Adapter (recommended) → VM gets IP from router;
  Attacker ↔ Victim ↔ Host communication possible

### 6. System Requirements

* Min 4 GB RAM
* 30–40 GB storage
* If low specs → use Live Kali from USB

---

##  Lecture 17 — PASSIVE INFORMATION GATHERING

### 7. Reconnaissance = First Stage of Hacking

Collect as much info as possible about:

* Target network
* Target system
* Organization

Used to identify possible attack vectors.

### 8. Objectives of Reconnaissance

* Network info: IP, domain, services
* System info: usernames, routing table, architecture
* Organization info: employees, policies, contact info

### 9. Two Types of Reconnaissance

* Passive → No direct contact; safe
* Active → Direct queries; more detail but detectable


### Passive Reconnaissance Tools

### 10. archive.org (Wayback Machine)

* Provides historical website versions
* Reveals directories, hidden pages, exposed files

### 11. Whois Lookup

Reveals:

* Owner name
* Email, phone
* IP range
* Registration date
* Name servers

---

### 12. Netcraft

Shows:

* Subdomains
* Server OS
* Web server info
  Helpful during exploitation.

---

### 13. Search Engines + Search Operators

* `site:` — search inside specific domain
* `cache:` — find cached pages
* `intitle:` — find title keyword
* `inurl:` — keyword in URL
* `filetype:` — find specific file types
* `"` `" ` — exact phrase
* `@` — restrict to social media

---

##  Lecture 18 — ACTIVE INFORMATION GATHERING

### 14. Active Recon = Direct Interaction

* More accurate, but risk of detection
* Tools: Nmap, dig, nslookup, Nessus, Metasploit

---

### 15. DNS & Mail Server Enumeration

* Find DNS servers & DNS records
* Identify mail servers (MX) → reveals users, IPs, computers
* Tools: `nslookup`, `host`, `dig`

### 16. Scanning (Nmap)

Used to detect:

* Live hosts
* Open ports
* Running services
* OS version
* Vulnerabilities

### Nmap Host Discovery Techniques

### 17. ICMP Echo Sweep (Ping Sweep)

* Sends ICMP type 8 → expects type 0 reply
* Option: `-PE`
* Easy but blocked often

### 18. Broadcast ICMP Sweep

* Sends request to broadcast address
* All hosts reply
* Fast but often blocked

### 19. Non-Echo ICMP Sweep

* Type 13 (Timestamp) → `-PP`
* Type 17 (Address Mask) → `-PM`
* Good alternative when ping is blocked

### 20. TCP SYN/ACK Sweep

* Detect live hosts using TCP packets
* Options:

  * `-PS` → SYN sweep
  * `-PA` → ACK sweep
* Common ports: 21, 22, 23, 25, 80

---

### 21. UDP Sweep

* Sends UDP datagram
* If ICMP Port Unreachable received → host down
* If no reply → host alive
* Option: `-PU`
* Unreliable due to blocking

---

##  Lecture 19 — PORT SCANNING USING NMAP

### 22. Port Scanning Purpose

To find which ports are:

* OPEN
* CLOSED
* FILTERED

Important because open ports = entry points.

### 23. TCP Connect Scan

* Completes 3-way handshake
* Easy to detect
  Command: `-sT`

### 24. TCP SYN Scan (Half-Open Scan)

* Sends SYN → receives SYN/ACK → sends RST
* Most common, stealthy
  Command: `-sS`

### 25. TCP Stealth Scans

Uses unusual flags:

* FIN
* NULL
* XMAS (FIN+URG+PSH)

Rules:

* Open port → no response
* Closed port → RST/ACK

### 26. FTP Bounce Scan

* Abuses FTP server to scan other systems
* Very slow
* Rare today but important in exam

---

##  Lecture 20 — OTHER FEATURES OF NMAP

### 27. Service & Version Detection

Command:

```
nmap -sV
```

Identifies:

* Software version
* Vulnerable services

---

### 28. OS Detection

Uses TCP/IP fingerprinting
Command:

```
nmap -O
```

Uses factors like:

* TCP ISN
* Window size
* ACK behavior
* ICMP quoting behavior

### 29. Important Nmap Discovery Options

* `-sL` → list targets
* `-sP` / `-sn` → ping scan
* `-PS/PA/PU` → SYN/ACK/UDP probes
* `-PE/PP/PM` → ICMP echo/timestamp/mask
* `-n` → skip DNS
* `-sU` → UDP scan

### 30. Important Port Scan Options

* `-sN`, `-sF`, `-sX` → Null / FIN / Xmas
* `-p` → specify port
* `-F` → fast scan
* `--top-ports <n>` → most common n ports

### 31. Countermeasures Against Reconnaissance

Organizations can prevent recon by:

* Do not publish sensitive info
* Disable directory listing
* Restrict DNS zone transfers
* Educate employees
* Keep systems patched
* Encrypt passwords
* Analyze suspicious logs
* Use server banners wisely

---

## ⭐ SUPER QUICK REVISION (CHEAT-SHEET)

* Use VirtualBox Bridge Mode for hacking labs
* Reconnaissance = info gathering → *first step* of hacking
* Passive recon uses archive.org, Whois, Netcraft, search operators
* Active recon uses DNS enumeration, Nmap scans
* ICMP sweep → `-PE`, timestamp → `-PP`, address mask → `-PM`
* TCP SYN sweep → `-PS`, ACK sweep → `-PA`
* UDP sweep → `-PU`
* Connect scan = `-sT`, SYN scan = `-sS`, Stealth scan = `-sN/sF/sX`
* Version detection = `-sV`, OS detection = `-O`
* Protect organization: disable listing, restrict DNS, remove sensitive info

---

# ⭐ WEEK-5 — ONE PAGE REVISION NOTES

---

##  1. Vulnerability Scanning (Nmap NSE)

* Nmap Scripting Engine (NSE) location:
  `/usr/share/nmap/scripts`
* Run a script:
  `nmap --script <name> <target>`
* Run category:
  `nmap --script "http-*"`
* Vulnerability scan:
  `nmap -sV --script vuln <target>`
* Detects: weak services, outdated apps, misconfig, backdoors, SMB vulns, Heartbleed, Shellshock.

---

##  2. Nessus Security Scanner

* Professional vulnerability scanner.
* Detects CVEs, missing patches, malware, policy violations.
* GUI-based, plugin-driven.
* Used during enterprise vulnerability assessments.

---

##  3. Proxy Preparation

* Proxies hide attacker’s identity.
* Used to: bypass firewall, avoid detection, hide IP, mask location.
* Works as intermediary between attacker & victim.

---

##  4. System Hacking (Steps)

### A. Password Cracking Methods

* Shoulder surfing
* Social engineering
* Dictionary & Brute-force
* Rule-based attack
* Keyloggers
* Wire sniffing
* Default passwords
* Rainbow tables

Tools: John the Ripper, Hydra, Hashcat, Crunch.

### B. Privilege Escalation

* Vertical: user → admin
* Horizontal: user A → user B
* Exploits OS bugs, weak permissions, misconfig.

Defenses: restrict privileges, encrypt data, least privilege.

### C. File Hiding / Execution

* Install backdoors
* Remote execution tools
* Screenshot capture, keylogging, spyware.

---

##  5. Malware Concepts

### Malware Types

* Trojan
* Backdoor
* Virus
* Worm
* Ransomware
* Adware
* Rootkit
* Botnet
* Spyware

### Trojan

* Malicious code hidden in useful software.
* Provides backdoor, screenshot capture, DDoS, spam.

### Virus

* Requires host file (.exe, boot sector).
* Two phases: Infection & Attack.
* Types: hoax, spooky, stealth, polymorphic.

### Worm

* Standalone; replicates automatically; very fast spreading.

### Ransomware

* Encrypts files → demands payment (usually crypto).

### Malware Defense

* Antivirus
* Patch OS
* Firewalls
* Avoid malicious sites
* Don’t open unknown attachments
* Strong passwords

---

##  6. Sniffing & Protocol Attacks

### Sniffing

* Capturing packets in network.
* NIC set to promiscuous mode.
* Passive sniffing → hubs
* Active sniffing → switches (via MAC flooding, ARP poisoning)

### Vulnerable Protocols (clear text)

HTTP, Telnet, Rlogin, POP, IMAP, SMTP, FTP.

---

##  7. MAC Attack

* Switch CAM table overloaded with fake MACs.
* Switch fails → acts like hub → attacker sniffs all traffic.

---

##  8. DHCP Starvation

* Attacker floods DHCP server with fake requests.
* IP pool exhausted → legit users can't connect.

---

##  9. ARP Spoofing / ARP Poisoning

* Fake ARP replies sent to victim.
* Redirects traffic through attacker (MITM).
* Tools: Cain & Abel, WinArpAttacker.

---

# ⭐ SUPER QUICK LAST-MINUTE SUMMARY

* NSE = automated vulnerability detection.
* Nessus = enterprise grade scanner.
* Password cracking → brute force, dictionary, keylogger, sniffing.
* Privilege escalation → vertical/horizontal.
* Malware: Trojan, virus, worm, ransomware.
* Sniffing → passive/active, promiscuous mode.
* MAC attack → CAM table overflow.
* DHCP starvation → exhaust IP pool.
* ARP spoofing → MITM via fake ARP replies.

---

# WEEK-6

---

###  1. Cryptography Basics

### Types of Attacks

* Interruption → availability attack
* Interception → confidentiality attack
* Modification → integrity attack
* Fabrication → authenticity attack

### Passive vs Active Attacks

* Passive: eavesdropping, traffic analysis (hard to detect)
* Active: modification, replay, masquerade, DoS (easy to detect)

### Security Services

* Confidentiality
* Integrity
* Authentication
* Non-repudiation
* Access control
* Availability

---

###  2. Symmetric (Private-Key) Cryptography

### Key idea: Same key used for encryption & decryption.

### Classical Ciphers

✔ Caesar Cipher: shift by k positions
✔ Monoalphabetic: random substitution (26! keys)
✔ Transposition: reorder letters

Weakness: classical ciphers breakable with frequency analysis.

### Stream vs Block Ciphers

* Stream: encrypt bit-by-bit
* Block: encrypt fixed blocks (64-bit, 128-bit)

---

###  3. DES, 3DES, AES

### DES

* Block size: 64 bits
* Key size: 56 bits
* Structure: 16-round Feistel
* Weak today (small key)

### 3DES

* EDE (Encrypt–Decrypt–Encrypt)
* Effective key: 168 bits
* Stronger but very slow

### AES

* Block size: 128 bits
* Key sizes: 128/192/256 bits
* Rounds: 10/12/14
* Operations: SubBytes, ShiftRows, MixColumns, AddRoundKey
  👉 Fast, secure, modern standard (WiFi, VPN, SSL)

---

###  4. Public-Key Cryptography (RSA)

### Two keys:

* Public key → shared
* Private key → secret

### RSA Key Generation

1. Choose primes p, q
2. Compute n = pq
3. φ(n) = (p−1)(q−1)
4. Choose e (gcd(e, φ(n)) = 1)
5. Compute d = e⁻¹ mod φ(n)
6. Public key = (e, n)
7. Private key = (d, n)

### Encryption:

`C = Mᵉ mod n`

### Decryption:

`M = Cᵈ mod n`

Security: based on difficulty of factoring n.

---

###  5. Diffie–Hellman Key Exchange

Allows two parties to create a shared secret key over insecure network.

### Steps:

1. Public values: `g`, `n`
2. A chooses secret `x`: sends `X = gˣ mod n`
3. B chooses secret `y`: sends `Y = gʸ mod n`
4. Shared key:

   * A computes: `Yˣ mod n`
   * B computes: `Xʸ mod n`
     Both equal g^(xy) mod n

### Weakness:

* Vulnerable to Man-in-the-Middle attack

---

###  6. Hash Functions & MAC

### Hash Functions

* Output fixed-size digest
* Used for integrity
  Examples: MD5, SHA-1, SHA-256, SHA-512, RIPEMD

### MAC (Message Authentication Code)

`MAC = F(K, M)`
Provides:

* Authentication
* Integrity

Used in banking, API calls, secure messaging, etc.

---

###  7. Symmetric vs Asymmetric Speed

* Symmetric (DES/AES) is 100× faster
* Asymmetric (RSA) is slow
  👉 RSA is used only for key exchange, not bulk data.

---

## ⭐ SUPER QUICK SUMMARY (LAST 30 SECONDS)

* DES = 56-bit (weak), 3DES = secure but slow
* AES = modern, fast, secure
* RSA = public-key → used for encryption + signatures
* DH = key exchange → vulnerable to MITM
* Hash = integrity
* MAC = authentication + integrity
* 4 attacks: interruption, interception, modification, fabrication
* Security services = CIA + Auth + Non-rep + Access control

---

# WEEK-7

---

#  1. Cryptographic Hash Functions

### What is a Hash?

* Function that maps message → fixed-length digest
* One-way (irreversible)
* Collision-prone but should be hard to find collisions

### Properties of a Secure Hash

1. Preimage Resistance – hard to find M from H(M)
2. Second Preimage Resistance – hard to find M′ with same hash
3. Collision Resistance – hard to find any two messages with same hash
4. Variable input, fixed output, fast, deterministic

### Important Algorithms

* MD2, MD4, MD5 (128-bit)
* SHA-1 (160-bit)
* SHA-256, SHA-384, SHA-512
* RIPEMD-128/160

### Message Authentication Methods

* With encryption
* Without encryption (tag)
* MAC = H(K || M) → authentication + integrity

---

#  2. HMAC (Keyed Hash Function)

* Faster than symmetric-key encryption
* Structure:

  ```
  HMAC = H( K ⊕ opad || H( K ⊕ ipad || M ) )
  ```
* Used in: TLS, IPSec, APIs, banking.

### Attacks

* Birthday attack → needs ≥160-bit hash
* Attacks on compression function & chaining

---

#  3. Digital Signatures

### What they provide

* Authentication
* Integrity
* Non-repudiation

### Signing Process

* Sender signs using private key
* Receiver verifies using public key

### Types of Signatures

* With appendix (sign hash only)
* With message recovery
* Deterministic vs Probabilistic
* Blind signatures (used in e-cash)
* Undeniable signatures

### Common Algorithms

* RSA signatures
* DSA, ECDSA
* ElGamal, Schnorr

---

#  4. Digital Certificates (X.509)

### Purpose

Bind identity → public key.

### Issued by: CA (Certification Authority)

Contains:

* Name, email, domain
* Public key
* Validity
* Issuer
* Signature of CA

### Revocation

Stored in CRL (Certificate Revocation List).

---

#  5. SSL (Secure Socket Layer)

### Purpose

Secure communication for:

* HTTPS (443)
* POP3-SSL (995)
* SMTP-SSL (465)

### SSL Record Protocol

Fragment → Compress → MAC → Encrypt.

### SSL Handshake Steps

1. Client Hello
2. Server Hello
3. Server Certificate + Key Exchange
4. Finished messages → Secure session starts

SSL ensures:

* Confidentiality
* Integrity
* Authentication

---

#  6. TLS (Transport Layer Security)

* Successor to SSL; more secure
* Used in ALL modern browsers
* Uses certificate + key exchange + MAC

---

#  7. SSH (Secure Shell)

### Purpose

Secure replacement for:

* Telnet
* Rlogin
* Remote shells

### Features

* Public-key authentication
* Encrypted terminal access
* Supports password, RSA challenge-response, smartcards

---

#  8. IPSec (IP Security)

### Provides

* Confidentiality
* Integrity
* Authentication
* Anti-replay

### Operating Modes

* Transport Mode – encrypts payload only
* Tunnel Mode – encrypts entire IP packet (used in VPNs)

### Issues

* Complex
* NAT-unfriendly
* Requires IPSec-aware routers

---

#  9. S-HTTP (Secure HTTP)

### Difference:

* SSL/TLS → secures connection
* S-HTTP → secures individual messages

Supports:

* Symmetric + asymmetric encryption
* Flexible algorithms
* No need for client certificates

---

# ⭐ SUPER QUICK LAST-MINUTE SUMMARY

* Hash = one-way, fixed-length digest.
* Properties: preimage + 2nd preimage + collision resistance.
* HMAC = MAC using hash + key.
* Digital signatures: private key signs, public key verifies.
* Certificates: public key + identity, issued by CA, stored in CRL if revoked.
* SSL handshake: Client Hello → Server Hello → Certificate → Finished.
* TLS = newer, stronger SSL.
* SSH = secure remote login (replaces telnet).
* IPSec = security at IP layer (transport/tunnel).
* S-HTTP = message-level security.

---

# ⭐ WEEK-8

*(Steganography • Biometrics • Network Attacks • DNS Security • Email Security)*

---

#  1. Steganography

### Definition

Hiding secret data inside innocent media (image/audio/video).
Unlike cryptography, the goal is no suspicion.

### Key Terms

* Cover-medium → original file
* Stego-key → key used for hiding
* Stego-medium → final output with hidden data

### Methods

* LSB (Least Significant Bit)

  * Modify last bit of each pixel
  * Easy but fragile

* Masking & Filtering

  * Modify brightness/contrast in noisy regions

* Algorithmic/JPEG DCT

  * Embed bits into DCT coefficients (stronger)

### Digital Watermarking

* Same concept, but goal = ownership/copyright protection.

---

#  2. Biometric Authentication

### What is Biometrics?

Automated recognition based on biological/behavioral traits.

### Types

* Fingerprint (minutiae-based)
* Hand Geometry
* Iris Scan (IR camera)
* Face Recognition (geometry, sensitive to lighting)
* Voice Verification (pitch, tone)
* Retina Scan (very accurate; stressful)
* Behavioral: signature, keystroke, gait

### Applications

* Authentication (1:1)
* Identification (1:N)
* Forensic work, border control, attendance systems

---

#  3. Network-Based Attacks (DoS, DDoS, TCP/ICMP Attacks)

### DoS Attack

Goal: Make service unavailable.

### Smurf Attack

* ICMP Echo Request sent to broadcast address
* All hosts reply to victim → flood

### Ping of Death

* ICMP packet > 65,536 bytes crashes system.

### SYN Flooding

* Attacker sends many SYN requests with spoofed IPs
* Server fills half-open queue
* Defense: SYN cookies

### DDoS Attack

* Uses botnets → massive traffic
* Hard to trace & block

### HTTP Floods

* GET flood → request images/files repeatedly
* POST flood → heavy DB operations
* Defenses: CAPTCHA, WAF, filtering

---

#  4. DNS Security

### DNS Basics

* Resolves names → IPs
* Hierarchy: Root → TLD (.com) → Authoritative server

### Query Modes

* Iterative: server returns referral
* Recursive: server resolves fully

### DNS Vulnerabilities

* Uses UDP (spoofable)
* No authentication
* Data in plaintext

### DNS Cache Poisoning

* Attacker injects fake IP mappings into DNS cache
* Redirects users to malicious sites

### DNSSEC

Adds:

* Digital signatures
* Integrity
* Authenticity

Protects DNS responses using public-key crypto.

---

#  5. Email Security — PGP (Pretty Good Privacy)

### Why PGP?

* Free, widely used
* Strong crypto
* No dependence on CAs

### PGP Provides

* Authentication → digital signature
* Confidentiality → hybrid encryption
* Compression → ZIP
* ASCII armor → Base-64 encoding
* Segmentation → breaks data into 50 KB chunks

### How PGP Works

Uses combination of:

* Symmetric key (encrypt message)
* Asymmetric key (encrypt session key)
* Hashing (signature & integrity)

---

# ⭐ SUPER FAST LAST-MINUTE SUMMARY

* Steganography = hiding, cryptography = encrypting.
* LSB = simplest stego; DCT-based = strongest.
* Biometrics: physiological (fingerprint, iris) vs behavioral (voice, signature).
* DoS: Smurf, SYN flood, PoD; defense → SYN cookies, filtering.
* DDoS = botnets → harder to trace.
* DNS lacks integrity → cache poisoning.
* DNSSEC solves authenticity issues.
* PGP = strong hybrid encryption + signature + compression + encoding.

---

# ⭐ WEEK-9 

*(Sniffing • Wireshark • Ettercap • BurpSuite • Social Engineering • DoS/DDoS)*

---

#  1. Packet Sniffing (Wireshark)

### Sniffing = capturing and analyzing packets

* NIC must be in promiscuous mode
* Needs root/admin privileges
* On switches, attacker needs MITM/ARP spoofing to sniff others’ traffic

### Sniffer Tools

* Wireshark
* Kismet
* SolarWinds
* BurpSuite

### Wireshark Basics

* Shows source, destination, protocol, length, info
* Views: packet list, protocol tree, hex dump
* Filter bar:

  * `http`
  * `tcp.port == 80`
  * `ip.addr == 10.0.0.5`

### Sniffer Detection

```
nmap --script=sniffer-detect <target>
```

### Sniffing Countermeasures

* Use encryption: SSH, SFTP, HTTPS, TLS, PGP, VPN
* Static ARP entries
* Prefer IPv6
* Disable unused ports/services
* Use switches instead of hubs

---

#  2. Sniffing Tools: Ettercap & BurpSuite

### Ettercap

* MITM attack tool
* Sniffs IP/MAC-based traffic
* Password interception
* SSH-1 sniffing
* HTTPS sniffing
* Packet injection & dropping
* Plugin support

### BurpSuite

* Proxy: intercept requests
* Spider: web crawling
* Intruder: automated attacks
* Repeater: resend modified requests
* Scanner (Pro): vulnerability detection
  Used for web pentesting + HTTPS interception.

---

#  3. Social Engineering

### Definition

Manipulating people to give confidential information.

### Phases

1. Research
2. Select victim
3. Build trust
4. Exploit

### Human-Based Attacks

* Impersonation
* Tailgating / Piggybacking
* Shoulder surfing
* Reverse social engineering
* Eavesdropping

### Computer-Based Attacks

* Phishing / Spear phishing
* Pop-ups
* Chat information gathering
* Fake error messages

### Mobile-Based Attacks

* Malicious apps
* Fake bank SMS
* Credential harvesting via SMS

### Countermeasures

* Employee training
* Strong passwords
* 2FA
* Anti-phishing tools
* Physical security
* Background checks

---

#  4. DoS & DDoS Attacks

### DoS = single attacker, DDoS = multiple attackers (botnet)

Goal: make service unavailable.

### Major Attacks

* Smurf Attack: ICMP Echo Request to broadcast → all reply to victim
* Ping of Death: ICMP > 65,536 bytes → crash
* SYN Flood: many SYN packets with spoofed IPs → server half-open queue full
* ICMP Flood: excessive ping packets
* HTTP GET/POST Flood: overloads web apps & databases

### DDoS Tools

* Slowloris: many half-open HTTP connections
* LOIC: high-volume TCP/UDP/HTTP floods
* RUDY: very slow, long POST requests → server exhaustion

### Countermeasures

* Disable unused services
* Patch vulnerabilities
* Anti-virus / Anti-trojan
* Traffic filtering
* Increase bandwidth
* Load balancing / server replication
* Detect abnormal traffic patterns

---

# ⭐ SUPER QUICK 30-SECOND SUMMARY

* Sniffing = capturing packets. NIC must be in promiscuous mode.
* Wireshark = main sniffer; filters analyze traffic.
* Ettercap = MITM + sniffing; BurpSuite = HTTP/HTTPS manipulation.
* Social engineering = human manipulation → phishing, impersonation, tailgating.
* DoS: SYN flood, Smurf, Ping of Death; DDoS uses botnets.
* Slowloris, LOIC, RUDY = major DDoS tools.

---

# ⭐ WEEK-10

*(Hardware Security • Side-Channel Attacks • Timing • Power Analysis • PUF • Hardware Trojans)*

---

#  1. Hardware Security

### Hardware Attacks

* Physical attacks: direct probing, opening chips
* Planned attacks: malicious circuits inserted during manufacturing
* Non-invasive (black-box): observe input/output behavior
* Reverse engineering: layer removal + microscopy

### Side Channels (Leakage)

* Power usage
* Timing
* EM radiation
* Faulty outputs
* Temperature
  *(as shown in Week-10 diagrams)*

### Countermeasures

* Data obfuscation (encrypted buses, scrambled values)
* Layout obfuscation (dummy logic, 3D stacking)
* Metal mesh shield (tamper detection)
* PUF-based authentication
* Side-channel resistant design (noise, random delays)

---

#  2. Timing Attacks (Kocher, 1995)

### Key Idea

Execution time depends on the secret key bits.
Used to attack:

* RSA
* Diffie-Hellman
* ECC

### Example (Square-and-Multiply)

More `1` bits → more multiplication operations → longer execution time.

### Time Formula

```
Time = n * t_square + k * t_mul  
```

`k` = number of 1-bits in exponent.

### Countermeasure

Make execution time constant:

```
Time = n * (t_square + t_mul)
```

---

#  3. SPA & DPA — Power Analysis Attacks (Kocher, 1998)

### ⭐ SPA (Simple Power Analysis)

* Observes single power trace
* Distinguishes instructions (square vs multiply)
* Extracts key bit-by-bit
* Used on smart cards, AES/DES hardware

### ⭐ DPA (Differential Power Analysis)

* Collect many traces
* Group traces by guessed key bit
* Average → subtract → peak indicates correct key
* Extremely powerful, breaks many devices

### Countermeasures

* Noise generators
* Random delays
* Masking intermediate values
* Balanced logic
* Desynchronization

---

#  4. PUF — Physical Unclonable Function

### Definition

Hardware “fingerprint” created from manufacturing variations.

### Properties

* Unique
* Unclonable
* Unpredictable
* Many challenge–response pairs

### Types

* Arbiter PUF – delay difference
* RO PUF (Ring Oscillator) – frequency comparison
* SRAM PUF – power-up state

### Uses

* Device authentication (anti-counterfeit)
* Secret key generation
* Avoid storing keys in NVM

---

#  5. Hardware Trojans

### What is a Hardware Trojan?

Malicious modification of IC during design or fabrication.

### Two Main Parts

* Trigger – when Trojan activates
* Payload – leak data, alter function, disable chip

### Types

* Combinational
* Sequential
* Asynchronous
* Analog (temperature-based, EM-based)
* Hybrid

### What They Do

* Information leakage
* Backdoor access
* Denial of service
* Performance degradation
* Kill switch

### Detection Methods

* Functional testing
* Side-channel analysis (power, EM, delay)
* Reverse engineering
* Run-time monitoring
* Hard because Trojans can be tiny + deeply hidden.

---

# ⭐ SUPER QUICK LAST-MINUTE SUMMARY

* Timing attack: execution time leaks key bits.
* SPA: single power trace reveals operations.
* DPA: statistical attack over many traces → extracts key.
* PUF: hardware fingerprint → used for authentication/key generation.
* Hardware Trojan: malicious circuit added; trigger + payload; hard to detect.
* Countermeasures: noise, masking, random delays, encrypted buses, tamper mesh.

---

# ⭐ WEEK-11

*(Metasploit • SQL Injection • SQLMAP • XSS)*

---

#  1. Metasploit Framework (MSF)

### What is Metasploit?

Pen-testing framework used for:

* Vulnerability scanning
* Exploitation
* Payload delivery
* Post-exploitation

### Key MSF Modules

* Exploits: attack vulnerabilities
* Payloads: shell, meterpreter
* Auxiliary: scanners, brute force, DoS
* Encoders: obfuscate payloads (AV evasion)
* NOPS: padding to prevent crashes
* Post: actions after compromise (password dump, sysinfo)

### Common MSF Commands

* `search <term>`
* `use <module>`
* `show options`
* `set RHOST <target>`
* `exploit`
* `msfvenom` → create payloads

### Workflow

Scan → Select exploit → Set options → Choose payload → Encode → Launch.

---

#  2. Webserver Vulnerabilities & SQL Injection

### Why web servers are vulnerable?

* Global availability
* Complex software
* Misconfigurations
* Weak input validation

### Common Web Attacks

SQLi, XSS, Session Hijacking, DoS, Buffer Overflow.

---

### ⭐ SQL Injection (SQLi)

Attacker injects SQL code into input fields to manipulate DB.

### Major Types of SQLi

* Error-Based: DB error messages reveal data
* UNION-Based: combine results from injected queries
* Boolean-Based Blind: true/false responses used
* Time-Based Blind: server delays indicate truth
* Stacked Queries: multiple SQL statements
* Out-of-Band: DNS/HTTP-based data exfiltration

### Impact

* Unauthorized login
* Dump/modify/delete data
* Full database takeover
* Server compromise

---

#  3. SQLMAP Tool

### What is SQLMAP?

Automated SQLi detection + exploitation tool.

### Key Features

* Detects SQLi
* Fingerprints DB (MySQL, Oracle, MSSQL, PostgreSQL…)
* Dump DB & tables
* Retrieve passwords
* Find users/privileges
* File system access (some DBs)
* Works with Metasploit payloads

### Important Commands

* `--current-user` → show DB user
* `--current-db` → show current DB
* `--dbs` → list DBs
* `--tables -D <db>` → list tables
* `--columns -T <table> -D <db>` → list columns
* `--dump -T <table> -D <db>` → dump data
* `--users` `--passwords` `--is-dba`

### Workflow

Find vuln → Test with SQLMAP → Enumerate → Dump → Escalate.

---

#  4. Cross-Site Scripting (XSS)

### What is XSS?

Injecting malicious JavaScript into trusted websites → browser executes it.

### Attack Capabilities

* Steal cookies & session tokens
* Bypass login
* Deface website
* Redirect users
* Keylogging
* Account takeover

---

### ⭐ Types of XSS

#### 1. Stored XSS (Persistent)

Malicious script stored in DB; affects every viewer.

#### 2. Reflected XSS (Non-persistent)

Payload in URL/query string; executed instantly.

#### 3. DOM-Based XSS

Vulnerability in client-side JavaScript; payload never touches server.

---

### New Category (Important for Exams)

* Server XSS: Vulnerability on server output

  * Stored Server XSS
  * Reflected Server XSS
* Client XSS: Vulnerability in DOM

  * Stored Client XSS
  * Reflected Client XSS

---

### XSS Countermeasures

* Input validation
* Output encoding (HTML/JS escaping)
* Disable/limit scripts when possible
* Content filtering proxy
* Cookie security flags (HttpOnly, Secure)
* Patch servers and libraries
* Block malicious domains
* Avoid unsanitized DOM operations

---

# ⭐ SUPER QUICK LAST-MINUTE SUMMARY

* Metasploit = exploit + payload + post-exploitation framework.
* SQLi types: Error, UNION, Blind (Boolean/Time), Stacked.
* SQLMAP = automated SQLi → dump DB, users, passwords.
* XSS = JavaScript injection → Stored, Reflected, DOM.
* XSS protection = input validation + output encoding + cookie security.

---

# WEEK-12 

*(NMAP Host Discovery • NMAP Port Scanning • NMAP Service/OS Detection • NSE Scripts • Wireshark)*

---

# 1. NMAP Host Discovery (Ping Scans)

*(Which hosts are alive?)*

### ICMP Scans

* -PE → ICMP Echo Request
* -PP → ICMP Timestamp
* -PM → ICMP Netmask
  ✘ Many networks block ICMP → unreliable.

### TCP-Based Discovery

* -PS → TCP SYN ping
* -PA → TCP ACK ping
  ✔ Works even if ICMP blocked
  ✘ Firewalls may spoof responses.

### UDP Discovery

* -PU → UDP ping
  ✘ Very unreliable (UDP often filtered).

### Other Options

* -sn → Ping sweep (formerly -sP)
* -sL → List scan (no packets sent)
* -PN → Treat all hosts as online (skip ping)
* -n/-R → DNS resolution control

---

# 2. NMAP Port Scanning

### TCP Connect Scan (-sT)

* Full 3-way handshake
  ✔ Works everywhere
  ✘ No stealth (logged easily)

### TCP SYN Scan (-sS)

* Half-open (SYN → SYN/ACK → RST)
  ✔ Fast & stealthy
  ✔ Most popular scan
  ✘ Requires root/administrator

### Stealth Scans (RFC 793)

* Null scan (no flags)
* FIN scan
* Xmas scan (FIN+URG+PSH)
  ✔ Very stealthy
  ✘ Windows always replies RST → ineffective

### FTP Bounce Scan (-b)

Uses FTP server to relay packets.
✔ Hides attacker
✘ Rarely works today

### Useful Options

* `-p22` or `-p1-1000` → specific ports
* `-F` → fast scan
* `--top-ports N` → scan most common N ports
* `-sO` → IP protocol scan

---

# 3. NMAP Service / Version / OS Detection

### Service/Version Detection (-sV)

Finds:

* Service name (http, ssh…)
* Version (Apache 2.4.x…)
* App fingerprint
  Intensity: 0–9 (`--version-all` = 9)

### OS Detection (-O)

Uses:

* TCP/IP stack behavior
* TTL, window size
* Flags
* ICMP responses
  Extra options:
* `--osscan-limit`
* `--osscan-guess`

---

# 4. NMAP Scripting Engine (NSE)

Automated scripts for:

* Vulnerabilities
* Brute forcing
* Malware scanning
* HTTP/S services
* SMB, DNS, FTP attacks

### Usage

```
nmap --script <script-name> <target>
```

### Important Script Categories

* `vuln` → general vulnerabilities
* `http-*` → HTTP checks
* `smb-brute` → SMB password attacks
* `malware` → malware fingerprinting

---

# 5. Wireshark: Network Analysis

### What Wireshark Does

* Packet capture
* Protocol breakdown
* Forensics & troubleshooting
* Works in promiscuous mode

### Wireshark Display Windows

* Packet list (source, destination, protocol)
* Protocol tree
* Hex/ASCII view

### Filters

* `http`
* `tcp.port == 80`
* `ip.addr == X.X.X.X`
  Valid filter → green, invalid → red.

### Important Wireshark Menus

* Analyze → enable/disable protocols, follow TCP streams
* Statistics → protocol hierarchy, conversations, endpoints
* Capture → select interfaces, start/stop capture

### What Can Be Captured

* HTTP credentials (plaintext)
* Session cookies
* TCP handshakes
* Malformed packets
* DNS queries/responses

### What Cannot Be Seen

* Encrypted HTTPS payload (only handshake visible)

---

# ⭐ SUPER-QUICK LAST-MINUTE SUMMARY

* Host Discovery: ICMP (-PE), SYN (-PS), ACK (-PA), UDP (-PU).
* Port Scanning: SYN (-sS) best; Connect (-sT) noisy; Xmas/FIN/Null stealthy.
* Service Detection: -sV → app/version fingerprinting.
* OS Detection: -O → TCP/IP behavior analysis.
* NSE Scripts: automate vulnerability scans (`--script vuln`).
* Wireshark: sniff packets in promiscuous mode; filter & analyze protocols.

---