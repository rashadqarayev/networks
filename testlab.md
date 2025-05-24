### 📘 Cisco Packet Tracer TestLab Cheatsheet (with Explanations)

---

## ✅ **SWITCH CONFIGURATION — Hostname: LAN**

---

### 🔹 1. Set the Hostname

```bash
Switch> enable
Switch# configure terminal
Switch(config)# hostname LAN
```

> 🎯 Sets the switch hostname to `LAN` (case-sensitive for assessment tools).

---

### 🔹 2. Enable DHCP Snooping for VLAN 16 Only

```bash
LAN(config)# ip dhcp snooping
LAN(config)# ip dhcp snooping vlan 16
LAN(config)# no ip dhcp snooping information option
```

> 🧠 Globally enables DHCP snooping, restricts it to VLAN 16, and disables Option 82 (which can interfere with basic DHCP setups).

---

### 🔹 3. Interface Configuration

#### ✅ **FastEthernet0/1 – to\_PC1**

```bash
interface FastEthernet0/1
 description to_PC1
 switchport mode access
 switchport access vlan 16
 spanning-tree portfast
 spanning-tree bpduguard enable
```

> 🖥️ Configures Fa0/1 for VLAN 16, enables PortFast for fast host startup, and BPDU Guard to protect against rogue switches.

---

#### ✅ **FastEthernet0/2 – to\_PC2**

```bash
interface FastEthernet0/2
 description to_PC2
 switchport mode access
 switchport access vlan 16
 spanning-tree portfast
 spanning-tree bpduguard enable
```

> 🖥️ Same configuration as Fa0/1, for PC2.

---

#### ✅ **FastEthernet0/3 – to\_DHCP\_Server**

```bash
interface FastEthernet0/3
 description to_DHCP_Server
 switchport mode access
 switchport access vlan 16
 ip dhcp snooping trust
 spanning-tree portfast
 spanning-tree bpduguard enable
```

> 🛡️ Trusts the DHCP server to prevent DHCP snooping from dropping valid offers.

---

#### ✅ **GigabitEthernet0/1 – to\_R1 (Trunk Port)**

```bash
interface GigabitEthernet0/1
 description to_R1
 switchport mode trunk
 switchport trunk allowed vlan 16
```

> 🌉 Trunk interface to the router, carrying only VLAN 16 traffic (router-on-a-stick).

---

## ✅ **ROUTER R1 CONFIGURATION**

---

### 🔹 1. Set Hostname to R1

```bash
Router> enable
Router# configure terminal
Router(config)# hostname R1
```

---

### 🔹 2. Configure Subinterface for VLAN 16

```bash
interface GigabitEthernet0/0.16
 description to_LAN
 encapsulation dot1Q 16
 ip address 172.16.16.1 255.255.255.240
```

> 🌐 Enables inter-VLAN routing using router-on-a-stick. Matches VLAN 16.

---

### 🔹 3. Configure Link to R2 (Point-to-Point)

```bash
interface GigabitEthernet0/1
 description to_R2
 ip address 10.10.12.1 255.255.255.252
 duplex auto
 speed auto
 no shutdown
```

> 🌐 Configures a routed point-to-point WAN link.

---

### 🔹 4. Add Static Route to Host 2.2.2.2

```bash
ip route 2.2.2.2 255.255.255.255 10.10.12.2
```

> 📍 Routes packets destined for loopback on R2 through the WAN link.

---

## ✅ **ROUTER R2 CONFIGURATION**

---

### 🔹 1. Set Hostname to R2

```bash
Router> enable
Router# configure terminal
Router(config)# hostname R2
```

---

### 🔹 2. Enable Password Encryption & Local Auth

```bash
service password-encryption
enable password admin
username admin password admin
```

> 🔐 Enables encryption for all plain-text passwords and creates login credentials.

---

### 🔹 3. Configure SSH Access

```bash
ip domain-name test.lab
crypto key generate rsa
# Choose at least 1024 bits

ip ssh version 2

line vty 0 15
 transport input ssh
 login local
```

> 🔐 Enables secure access only over SSH using local authentication.

---

### 🔹 4. Configure Interfaces

#### ✅ Loopback0

```bash
interface Loopback0
 ip address 2.2.2.2 255.255.255.255
```

#### ✅ Gi0/1 – to\_R1

```bash
interface GigabitEthernet0/1
 description to_R1
 ip address 10.10.12.2 255.255.255.252
 no shutdown
```

> 🧭 Needed for static route exchange and SSH testing.

---

### 🔹 5. Add Static Route to VLAN 16 LAN

```bash
ip route 172.16.16.0 255.255.255.240 10.10.12.1
```

---

## ✅ **DHCP SERVER CONFIGURATION (Packet Tracer Server)**

---

### 🔹 Step 1: Set Interface IP Info

In Config tab > FastEthernet0:

* IP: `172.16.16.2`
* Subnet: `255.255.255.240`
* Default Gateway: `172.16.16.1`

---

### 🔹 Step 2: DHCP Pool Setup (Services tab > DHCP)

```text
Service: ON
Pool Name: VLAN16_POOL
Default Gateway: 172.16.16.1
DNS Server: 172.16.16.2
Start IP Address: 172.16.16.3
Subnet Mask: 255.255.255.240
Max Users: 10
```

> 🧠 This assigns DHCP IPs from `.3` to `.12` in VLAN 16.

---

## ✅ **DHCP CLIENT VERIFICATION (PC1 & PC2)**

1. Open each PC.
2. Go to **Desktop > IP Configuration**
3. Set to **DHCP**

> ✅ Expected values:

* IP: `172.16.16.3–12`
* Gateway: `172.16.16.1`
* DNS: `172.16.16.2`

---

## ✅ **Verification Commands**

```bash
show running-config                # See full config
show ip dhcp snooping              # Verify snooping status
show vlan brief                    # Confirm VLAN 16 setup
show ip interface brief            # Check IP assignments
ping 2.2.2.2                       # Ping R2 loopback
ssh -l admin 2.2.2.2               # Test SSH access
```
