## 📘 Exam_Practice

---

### ✅ **SWITCH CONFIGURATION TASKS**

---

#### 🔹 Task 1: Basic Switch Configuration

```bash
Switch(config)# hostname LAN_sw
```

> Sets the switch hostname for identification.

---

#### 🔹 Task 2: Configure VLAN and DHCP Snooping

```bash
Switch(config)# ip dhcp snooping
Switch(config)# ip dhcp snooping vlan 100
Switch(config)# no ip dhcp snooping information option
```

> Enables DHCP snooping globally, restricts it to VLAN 100, and disables Option 82 insertion.

---

#### 🔹 Task 3: Configure Access Ports (Fa0/1 to Fa0/3)

```bash
interface range FastEthernet0/1 - 3
 switchport mode access
 switchport access vlan 100
 spanning-tree portfast
 spanning-tree bpduguard enable
 description to_PC1
```

> Sets access mode, VLAN 100, fast STP, BPDU protection, and port description.

---

#### 🔹 Task 4: Configure the Trunk Uplink (Gi0/1)

```bash
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 100
 ip dhcp snooping trust
 description Link to Main Office
```

> Configures trunking, restricts VLANs, marks port trusted for DHCP snooping.

---

### ✅ **ROUTER CONFIGURATION TASKS**

---

#### 🔹 Task 1: Set Hostnames and Enable Password

```bash
Main_Office(config)# hostname Main_Office
Branch(config)# hostname Branch
Branch(config)# enable password admin
```

> Basic identity and console protection.

---

#### 🔹 Task 2: Configure DHCP on Main\_Office

```bash
Main_Office(config)# ip dhcp excluded-address 192.168.100.254
Main_Office(config)# ip dhcp pool LAN_Network
 network 192.168.100.0 255.255.255.0
 default-router 192.168.100.254
 dns-server 172.16.16.2
```

> DHCP setup with IP range, gateway, and DNS server.

---

#### 🔹 Task 3: VLAN Subinterface Configuration

```bash
interface GigabitEthernet0/1.100
 encapsulation dot1Q 100
 ip address 192.168.100.254 255.255.255.0
```

> Router-on-a-stick setup to route VLAN 100.

---

#### 🔹 Task 4: Configure WAN Link Between Main\_Office & Branch

```bash
! On Main_Office
interface GigabitEthernet0/0
 ip address 10.10.12.2 255.255.255.252
 no shutdown

! On Branch
interface GigabitEthernet0/0
 ip address 10.10.12.1 255.255.255.252
 no shutdown

! On both (for OSPF auth)
ip ospf authentication message-digest
ip ospf message-digest-key 1 md5 secret
```

> Point-to-point link with OSPF MD5 authentication.

---

#### 🔹 Task 5: Configure OSPF Routing

```bash
! On Main_Office
router ospf 100
 network 10.10.12.0 0.0.0.3 area 0
 network 192.168.100.0 0.0.0.255 area 0
 log-adjacency-changes

! On Branch
router ospf 100
 network 10.10.12.0 0.0.0.3 area 0
 network 172.16.16.0 0.0.0.3 area 0
 network 10.11.11.11 0.0.0.0 area 0
 log-adjacency-changes
```

> Enables OSPF with correct networks, MD5, and neighbor tracking.

---

#### 🔹 Task 6: Configure Loopback & DNS Interface (Branch)

```bash
interface Loopback0
 ip address 10.11.11.11 255.255.255.255

interface GigabitEthernet0/1
 ip address 172.16.16.1 255.255.255.252
```

> Loopback for testing, Gi0/1 to reach DNS.

---

#### 🔹 Task 7: User & Domain Configuration (Branch)

```bash
username admin password admin
ip domain-name khazar.org
```

> For SSH access and domain-based RSA keys.

---

### ✅ **DNS SERVER CONFIGURATION**

---

#### DNS Server (in Packet Tracer):

1. **Set Static IP**

   * IP: `172.16.16.2`
   * Subnet: `255.255.255.252`
   * Gateway: `172.16.16.1`

2. **Enable DNS Service**

   * Go to **Services > DNS**, turn **ON**

3. **Add DNS Record**

   * Name: `khazar.org`
   * IP: `172.16.16.2`

---

### ✅ **Verify DNS from Main Office PCs**

1. Set PCs to DHCP
2. Check they receive:

   * IP in `192.168.100.x`
   * Gateway: `192.168.100.254`
   * DNS: `172.16.16.2`
3. Test:

```bash
ping khazar.org
```

---

### ✅ **SSH Access to Branch Router**

```bash
hostname Branch
ip domain-name khazar.org
username admin password admin
crypto key generate rsa
# Choose 1024 bits
ip ssh version 2

line vty 0 4
 transport input ssh
 login local
```

**From PC:**

```bash
ssh -l admin 10.11.11.11
```

---

### ✅ **Verification & Troubleshooting Commands**

```bash
show ip ospf neighbor          # Check OSPF adjacencies
show ip route                  # Verify routing table
ping khazar.org                # Test DNS resolution
ssh -l admin 10.11.11.11       # Test SSH
show ip dhcp binding           # Check DHCP leases
show vlan brief                # Verify VLAN assignments
show ip interface brief        # Check interface status
```
