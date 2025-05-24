### 🔹 Exam before exam
---

## 🧩 Task 1: Switch Configuration – LAN_Switch

### 🔹 1. Set Hostname (Case-Sensitive)
```bash
Switch> enable
Switch# configure terminal
Switch(config)# hostname LAN_Switch
````

> Sets the hostname to `LAN_Switch` for identification.

---

### 🔹 2. Create VLAN 10 with Description

```bash
LAN_Switch(config)# vlan 10
LAN_Switch(config-vlan)# name Internal_Network
```

> Creates VLAN 10 and assigns it a name (description), which is visible in `show vlan brief`.

---

### 🔹 3. Port Configuration with Port Security

#### 📍 Fa0/1 — to\_Rougue\_DHCP\_Server

```bash
interface fa0/1
 description to_Rougue_DHCP_Server
 switchport mode access
 switchport access vlan 10
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
```

#### 📍 Fa0/3 — to\_PC3

```bash
interface fa0/3
 description to_PC3
 switchport mode access
 switchport access vlan 10
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation protect
 switchport port-security mac-address sticky
```

#### 📍 Gi0/2 — to\_Hub

```bash
interface gigabitEthernet0/2
 description to_Hub
 switchport mode access
 switchport access vlan 10
 switchport port-security
 switchport port-security maximum 2
 switchport port-security violation protect
 switchport port-security mac-address sticky
```

---

### 🔹 4. Configure Trunk (Gi0/1 — to\_Enterprise\_Router)

```bash
interface gigabitEthernet0/1
 description to_Enterprise_Router
 switchport mode trunk
 switchport trunk allowed vlan 10
 ip dhcp snooping trust
```

---

### 🔹 5. Enable DHCP Snooping

```bash
ip dhcp snooping
ip dhcp snooping vlan 10
```

> Enables DHCP snooping globally and limits it to VLAN 10.

---

## 🧩 Task 2: Router Configuration – Enterprise\_Router

### 🔹 1. Set Hostname

```bash
Router> enable
Router# configure terminal
Router(config)# hostname Enterprise_Router
```

---

### 🔹 2. Enable Gi0/0 and Configure Subinterface for VLAN 10

```bash
interface gigabitEthernet0/0
 no shutdown

interface gigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
 description to_LAN_Switch
```

> Subinterface enables router-on-a-stick for VLAN 10 and assigns the correct IP.

---

### 🔹 3. Configure DHCP Server

```bash
ip dhcp excluded-address 192.168.10.1

ip dhcp pool LAN_Network
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 192.168.10.1
```

> Sets up DHCP with exclusions and correct gateway/DNS settings.

---

## 🧩 Task 3: PC Configuration

### 🔹 1. PC3 – DHCP Client

* Go to **PC3 > Desktop > IP Configuration**
* Select **DHCP**

> PC3 should receive an IP from 192.168.10.x via Enterprise\_Router.

---

### 🔹 2. PC1, PC2, PC4 – Connect to HUB & Enable DHCP

* Connect PCs to the HUB, then HUB to **Gi0/2 on switch**.
* On each PC:

  * Go to **Desktop > IP Configuration**
  * Select **DHCP**

> Only 2 of these 3 should successfully get IPs due to port security (2 MAC max on Gi0/2).

---

## 🧪 Verification Commands

### On Switch:

```bash
show running-config
show vlan brief
show port-security interface [interface]
```

### On Router:

```bash
show ip dhcp binding
show ip interface brief
```

### On PCs:

```bash
ipconfig /all
ping 192.168.10.1
```

---

```
