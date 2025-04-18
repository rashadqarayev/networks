# Lesson 1
# 🔐 Information Security Concepts

- **Information Security** involves protecting all forms of sensitive data (print, electronic, etc.) from unauthorized access, misuse, or disruption.
- **Cybersecurity** focuses on defending systems, networks, and programs from digital attacks that aim to steal, alter, or destroy data, extort users, or disrupt operations.
- **Network Security** protects the networking infrastructure through physical and software measures to ensure secure and authorized communication between systems and users.

---

## 🔒 CIA Triad

**Confidentiality (C)** – Keep data private, prevent unauthorized access.  
**Integrity (I)** – Keep data accurate and unchanged, prevent unauthorized modification.  
**Availability (A)** – Ensure that authorized users can access systems, applications, and data when they need to.

---

## 🧠 Common Security Terms

- **Asset** – Organization üçün dəyərli olan şeylər: Employees, Computers, Properties, Plants, Buildings  
- **Vulnerability** – Sistemin zəifliyi, səhvləri və s.  
- **Exploit** – Sistemdə zəifliklərdən istifadə etmək üçün hacker-in istifadə etdiyi method və ya tool  
- **Threat** – Asset-lərə zərər verə biləcək şeylər (hacker, viruslar, slow response)  
- **Attack** – Asset-ə zərər vermək üçün edilən hadisə  
- **Risk** = Asset + Threat + Vulnerability  
- **Countermeasure** – Zəifliyi aradan qaldırmaq üçün edilən addımlar. (Məs: Firewall qurmaq, parolu gücləndirmək)  
- **On-premises** – Proqram və resurslar öz ofislərində saxlanılır. Fiziki serverlərdə olur məlumatlar.  
  - **Üstünlüyü**: Daha təhlükəsiz, customize edilə bilər  
  - **Zəifliyi**: Serverlər və texniki heyət üçün yüksək xərc tələb edir  
- **Cloud Computing** – Məlumat və tətbiqlər uzaq serverlərdə saxlanılır və internet üzərindən idarə olunur.  
  - **Müsbət**: Disaster recovery, Accessibility, Cost-effective, Scalability  
  - **Mənfi**: Lack of control, Internet dependent, Privacy concern, Fixed contract

---

## 🦠 Malware

**Malware** (qısa olaraq "malicious software") – zərərli proqram və ya kod. Şəbəkə üzərindən yayılır, kompüterləri infeksiya edir və məlumatları oğurlayır.

### 🔍 Malware Tipləri:

1. **Viruses** – Özünü digər fayllara və proqramlara yayır, sistemə zərər verir.  
2. **Worms** – Şəbəkə üzərindən yayılır, istifadəçi müdaxiləsinə ehtiyac olmadan çoxalır.  
3. **Trojans** – Zərərsiz görünən, amma gizli şəkildə zərərli fəaliyyət göstərən proqram.  
4. **Rootkits** – Həssas fəaliyyətləri və ya proqramları gizlətmək üçün istifadə olunur.  
5. **Spyware** – İstifadəçini izləyir və şəxsi məlumatları oğurlayır.  
6. **Adware** – Reklamlar göstərərək istifadəçini narahat edir və sistem performansını azaldır.  
7. **Scareware** – Saxta təhlükə xəbərdarlıqları ilə istifadəçini qorxudur.  
8. **Botnets** – Zərərli proqramlarla infeksiya olunmuş və uzaqdan idarə olunan kompüterlər şəbəkəsi.  
9. **Logic Bombs** – Müəyyən bir hadisə və ya tarixdə aktiv olan zərərli proqram.  
10. **Key Loggers** – Klaviatura yazılarını qeyd edərək, şifrə və digər məlumatları oğurlayır.

---

## 🕵️ Threat Actor

**Threat actor** – Hücum həyata keçirən və ya təhlükəsizlik hadisələrinə səbəb olan şəxslər və ya qruplar.

### Threat Actor Növləri:

1. **Script Kiddies** – Təcrübəsiz hackerlər, əvvəlcədən hazırlanmış alətlərlə hücum edirlər.  
2. **Organized Crime Groups** – Məlumat oğurlamaq və ya pul qazanmaq üçün hücum edən cinayətkar qruplar.  
3. **State Sponsors or Governments** – Dövlət tərəfindən dəstəklənən hücumçular, casusluq və ya siyasi müdaxilə məqsədilə.  
4. **Hacktivists** – Sosial/siyasi məqsədlərlə fəaliyyət göstərən hackerlər.  
5. **Terrorist Groups** – Kritikal infrastruktur və digər məqsədlər üçün terror hücumları həyata keçirirlər.

---

## 💻 Hacker

**Hacker** – Əvvəllər sistemlərə maraq göstərən şəxs, indi isə müxtəlif niyyətlərlə fəaliyyət göstərən fərdlər.

### Hacker Növləri:

1. **White Hat Hackers** – Etik hackerlər, şirkətlərin sistemlərini test və qorumaq üçün fəaliyyət göstərirlər.  
2. **Black Hat Hackers** – Qanunsuz və zərərli fəaliyyət göstərən şəxslərdir.  
3. **Gray Hat Hackers** – Qanuni və qeyri-qanuni fəaliyyətlər arasında olan hackerlər.

---

## ⚠️ SPOF – Single Point of Failure

**Single Point of Failure (SPOF)** – Bir sistemin fəaliyyətinin dayandığı kritik nöqtə. Bir hissə sıradan çıxarsa, bütün sistem çökə bilər.

> **Tövsiyə**: SPOF qarşısını almaq üçün şəbəkədə redundans (redundant devices və fiziki bağlantılar) artırılmalıdır.

---

## 🚨 Attack Types

1. **SQL Injection Attack**  
2. **XSS – Cross Site Scripting Attack**  
3. **Phishing – Social Engineering Attack**  
4. **Buffer Overflow Attack**  
5. **Path Traversal Attack**  
6. **MITM – Man-in-the-Middle Attack**  
7. **DOS – Denial of Service Attack**

# Lesson 2
## OSI Model:

1. Application Layer  
2. Presentation Layer  
3. Session Layer  
4. Transport Layer  
5. Network Layer  
6. Data Link Layer  
7. Physical Layer  

---

## TCP/IP Encapsulation – De-Encapsulation  
### Headers Content

---

## OSI Model: Application Layer

- Sits at Layer 7 (top) of the OSI model.  
- Ensures applications can communicate across networks.  
- It's *not* an application, but a part that controls communication.  
- Defines protocols like: *HTTP, FTP, SMTP, Telnet, SSH*.  
- Network applications *use* the Application Layer Protocols but do not reside in it.  
- Also called the *Software Layer*.

[Reference](https://www.techtarget.com/searchnetworking/definition/OSI)

---

## OSI Model: Presentation Layer

- Handles *data formatting, **conversion, **encryption/decryption, and **compression*.  
- Converts characters/numbers into binary – *Translation*.  
- Reduces data size – *Compression*.  
- Encrypts/Decrypts data (e.g., using *SSL*).

---

## OSI Model: Session Layer

*1) Setting Up Sessions*  
- Checks credentials  
- Assigns session ID  
- Negotiates services  

*2) Maintaining Sessions*  
- Transfers data  
- Re-establishes sessions  

*3) Tearing Down Sessions*  
- By mutual agreement or intervention  

*Examples:* NFS, PAP, RTP

---

## OSI Model: Transport Layer

- Manages *Segmentation, **Flow Control, **Error Control*  
- Protocols: *TCP* and *UDP*  
- Data Unit: *Segments*

### Segmentation  
- Divides data into segments with sequence and port numbers.

### Flow Control  
- Controls data transmission rate (e.g., notebook 10Mb vs server 100Mb NIC).

### Error Control  
1. *Checksum* – Detects corrupted segments.  
2. *Acknowledgement* – Confirms receipt of segments.  
3. *Retransmission* – Sends missing or corrupted segments again.

---

## OSI Model: Network Layer

- Data Unit: *Packets*  
- Functions:  
  - *Logical Addressing* (IP)  
  - *Routing*  
  - *Path Determination* (RIP, EIGRP, OSPF, ISIS, BGP)  

*Protocols:* IPv4, IPv6, ICMP

---

## OSI Model: Data Link Layer

- Two Sublayers:  
  - *MAC (Media Access Control):* Physical addressing  
  - *LLC (Logical Link Control):* Frame preparation  

### Functions

*Framing*  
- Converts packets into frames for transmission.

*Addressing*  
- Adds source and destination MAC addresses to frames.

[More Info](https://www.geeksforgeeks.org/network-layer-services-packetizing-routing-and-forwarding)  
[More Info](https://www.geeksforgeeks.org/physical-layer-in-osi-model)  
[More Info](https://www.geeksforgeeks.org/introduction-of-mac-address-in-computer-network)

---

### Additional DLL Functions

*Error Control*  
- Detects and corrects transmission errors using *error detection bits*.

*Flow Control*  
- Synchronizes sender and receiver speeds to avoid data loss.

[More Info](https://www.geeksforgeeks.org/error-detection-in-computer-networks)  
[More Info](https://www.geeksforgeeks.org/hamming-code-in-computer-network)

---

## OSI Model: Physical Layer

- Handles *physical representation* of data.  
- Converts data to binary (e.g., 0101011101).  

---

## TCP/IP Model

- Developed by U.S. DoD for a *vendor-neutral* networking model.  
- *Application Layer* in TCP/IP = Application + Presentation + Session (OSI).  
- Encapsulation = Data passes *top-down* (adds headers).  
- De-encapsulation = Reverse.

### Layers:

1. Application Layer  
2. Transport Layer  
3. Internet Layer  
4. Link Layer  

*Updated Model* also maps to:  
Application → Transport → Network → Data Link → Physical

---

## TCP/IP Encapsulation – De-Encapsulation

- Each layer *adds/removes headers* during packet transmission.

---

## Headers Content

- *Transport Layer: Source & destination **port numbers*  
- *Network Layer: Source & destination **IP addresses*  
- *Data Link Layer*:  
  - *Header: Source & destination **MAC addresses*  
  - *Trailer: **FCS (Frame Check Sequence)* for error detection using CRC

---
# ✅ Lesson 3: OSI Layer 2 Attacks & Mitigations

This lesson covers four common **Layer 2 (Data Link Layer)** attacks in the OSI model and the methods to defend against them.

---

## 🔹 1. MAC Address Flooding Attack

- **Description:** Attacker floods a switch with fake MAC addresses to overflow its MAC address table.
- **Effect:** Switch starts broadcasting traffic to all ports like a hub, enabling data interception.
- **Mitigation:**  
  - **Port Security:**
    - Limit the number of allowed MAC addresses per port.
    - Violation actions: shutdown, restrict, or protect.
    - Tracks and blocks unknown devices.

---

## 🔹 2. DHCP Starvation Attack

- **Description:** Attacker sends fake DHCP requests to exhaust the IP pool.
- **Effect:** Legitimate devices can’t obtain IP addresses (DoS).
- **Mitigation:**
  - **Port Security**
  - **DHCP Snooping:**
    - Classifies switch ports as trusted or untrusted.
    - Allows DHCP offers only from trusted ports.
    - Builds a **binding table** (MAC-to-IP mappings).
    - 🔧 **Config Example:**
      ```bash
      Switch(config)# ip dhcp snooping
      Switch(config)# ip dhcp snooping vlan 1
      Switch(config-if)# ip dhcp snooping trust
      ```

---

## 🔹 3. Rogue DHCP Server

- **Description:** Unauthorized DHCP server assigns incorrect IP or gateway info.
- **Effect:** Causes misconfiguration, traffic redirection, or MITM.
- **Mitigation:**
  - **Port Security**
  - **DHCP Snooping**

---

## 🔹 4. ARP Spoofing / ARP Poisoning

- **Description:** Attacker sends fake ARP replies linking their MAC to another device’s IP.
- **Effects:**
  - Man-in-the-Middle (MITM) attacks
  - Denial of Service (DoS)
  - Data interception or manipulation
- **Mitigation:**
  - Static ARP entries
  - ARP monitoring tools (e.g., `arpwatch`, `XArp`)
  - **Dynamic ARP Inspection (DAI):**
    - Validates ARP packets using DHCP snooping binding table.
    - Drops malicious ARP packets.
    - 🔧 **Config Example:**
      ```bash
      Switch(config)# ip arp inspection vlan 1
      Switch(config-if)# ip arp inspection trust
      ```

---

Here's **Lesson 4** summarized and formatted in Markdown:

```md
# ✅ Lesson 4: Spanning Tree Protocol (STP) Attacks & Mitigations

This lesson focuses on **Layer 2 attacks** that exploit the **Spanning Tree Protocol (STP)** and how to secure against them—particularly the **Root Bridge Spoofing Attack**.

---

## 🔹 Attack: Root Bridge Spoofing

- **Description:** 
  - Attacker sends BPDUs with lower bridge priority or fake MAC address.
  - This tricks switches into electing the attacker's switch as the **Root Bridge**.
- **Effect:**
  - Attacker gains control of network topology.
  - Enables **MITM attacks** or network disruption.

---

## 🔐 Mitigation Techniques

### 1. **PortFast**
- Skips STP listening and learning states on ports connected to end devices.
- Useful for faster boot and preventing participation in STP.
- ⚙️ **Config:**
  ```bash
  Sw1(config-if)# spanning-tree portfast
  ```

---

### 2. **BPDU Guard**
- Disables a port if it receives **any BPDU** (unexpected on access ports).
- Prevents accidental loops and unauthorized switches.
- ⚙️ **Config:**
  ```bash
  Sw1(config-if)# spanning-tree bpduguard enable
  Sw1(config)# errdisable recovery cause bpduguard
  ```

---

### 3. **Root Guard**
- Protects the role of the current root bridge.
- If a port receives a superior BPDU, it goes into **root-inconsistent (blocked)** state.
- ⚙️ **Config:**
  ```bash
  Sw1(config-if)# spanning-tree guard root
  ```

---

### 4. **BPDU Filter**
- Filters (blocks) BPDUs **in and out** on selected ports.
- Prevents the port from participating in STP.
- ⚠️ Use with caution—can cause loops if topology changes.
- ⚙️ **Config:**
  ```bash
  Sw(config-if)# spanning-tree bpdufilter enable
  ```

---

### 5. **Loop Guard**
- Detects unidirectional link failures where BPDUs are not received but still sent.
- Prevents such ports from transitioning to forwarding state (places in loop-inconsistent state).
- ⚙️ **Config:**
  ```bash
  Sw(config-if)# spanning-tree guard loop
  ```

---

## 🧠 Real-World Example

- A switch receives BPDUs from a neighbor and blocks its port.
- If one direction of a fiber link fails (e.g., due to hardware damage), BPDUs stop being received.
- The port mistakenly moves to **forwarding**, forming a **unidirectional loop**.
- **Loop Guard** prevents this scenario.

---
```

Let me know if you'd like Lesson 5 next or want these bundled into downloadable `.md` files!

Here’s the full **Lesson 5** summary formatted in Markdown:

```md
# ✅ Lesson 5: VLAN Hopping, Storm Control & Network Planes

This lesson covers advanced Layer 2 security topics including **VLAN hopping attacks**, **storm control**, and the **network planes model** (management, control, data).

---

## 🔹 1. VLAN Hopping Attacks

VLAN hopping allows an attacker to gain access to traffic on VLANs they shouldn't have access to. Two types:

### A. Switch Spoofing
- **Description:** Attacker pretends to be a switch using DTP packets to form a trunk link.
- **Effect:** Attacker can access multiple VLANs.
- **Mitigation:**
  ```bash
  switchport mode access
  switchport nonegotiate
  switchport mode trunk
  interface range Gi0/1 - 24
  shutdown
  ```

### B. Double Tagging
- **Description:** Attacker sends frames with two VLAN tags. Outer tag is stripped by first switch; inner tag forwards to another VLAN.
- **Mitigation:**
  ```bash
  switchport trunk native vlan 999
  switchport trunk allowed vlan remove 1
  switchport trunk allowed vlan 10,20,30
  ```

- **Bonus:** Use **ACLs** to restrict inter-VLAN traffic (covered in future lessons).

---

## 🔹 2. Storm Control

### 🚦 What It Does:
Limits and prevents **broadcast, multicast, and unicast storms** that can flood a network.

### 🛠 Configuration Example:
```bash
interface FastEthernet0/1
storm-control broadcast level 50.00
storm-control multicast level 30.00
storm-control action shutdown
```

- Default: **Disabled**
- Thresholds can be set by **percent**, **pps**, or **bps**

---

## 🔹 3. Network Planes: Management, Control, and Data

Modern network devices have three logical layers ("planes") of operation:

### 🧑‍💻 A. Management Plane
- **Purpose:** Administrative access (SSH, Telnet, SNMP, GUI)
- **Risks:** Unauthorized access, brute force, misconfigurations

### 🧠 B. Control Plane
- **Purpose:** Makes routing decisions (OSPF, BGP, EIGRP, etc.)
- **Risks:** Route injection, protocol spoofing
- **Mitigation:** 
  - Control Plane Policing (CoPP)
  - Route filtering
  - Protocol authentication

### 🚚 C. Data Plane
- **Purpose:** Forwards user data (IP forwarding, NAT, QoS, MPLS)
- **Security Measures:** NAT rules, ACLs, inspection

---

## 🧵 Additional Concepts

### Console Port
- Used for **Out-of-Band** access when the device has no network connection.
- Secure and direct management.

### In-Band vs Out-of-Band Management
- **In-Band:** SSH, Telnet, HTTP over IP
- **Out-of-Band:** Direct console cable (no network required)

---

## 🔐 Cisco Password Types

| Type | Method          | Security Level | Notes                            |
|------|------------------|----------------|----------------------------------|
| 0    | Plain Text       | ❌ Very Weak    | Avoid completely                 |
| 7    | XOR (Weak Hash)  | ❌ Very Weak    | Reversible                       |
| 5    | MD5 Hash         | ✅ Moderate     | One-way hash, still common       |
| 8    | SHA256 / PBKDF2  | ✅✅ Strong     | Newer and recommended            |
| 9    | Scrypt           | ✅✅✅ Very Strong | Best option for secure storage   |

---
```

Let me know if you want this bundled with the others into downloadable files or converted to PDF!
