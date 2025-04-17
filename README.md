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

*That is all for Lesson 2.*
