# Small-office-network
Simulated a small office network with VLSM Subnetting, VLAN creation, Inter-VLAN routing, Switch & Router Configuration & Static IP addressing for secure internal communication.

📌 Small Office Network Design (Cisco Packet Tracer)

A professionally structured Small Office Network designed in Cisco Packet Tracer, demonstrating practical networking skills including VLSM subnetting, VLAN configuration, inter-VLAN routing, switch port segmentation, and static device addressing.

<b>Network Topology Diagram<b>

<img width="801" height="437" alt="image" src="https://github.com/user-attachments/assets/5e344e11-0728-46a8-96b7-4fc381c774fa" />

<img width="1212" height="718" alt="Screenshot 2025-11-16 195019" src="https://github.com/user-attachments/assets/27007732-5958-456b-a528-b80c3b2f94ff" />

<img width="633" height="148" alt="Screenshot 2025-11-16 195104" src="https://github.com/user-attachments/assets/be82f80b-4a37-4fcc-b918-5c26dd69782b" />

🔧 Project Overview
This project simulates a small office environment with three functional departments, each placed in its own VLAN:

- VLAN 50 – Management
- VLAN 30 – Staff
- VLAN 20 – Guests

The network is designed using VLSM to optimize address allocation and ensure efficient IP usage across subnets.
🛠️ Technologies & Skills Demonstrated
- Cisco Packet Tracer
- VLSM Subnetting
- Router-on-a-Stick Inter-VLAN Routing
- VLAN Creation & Assignment
- Trunking Between Switch and Router
- Static IP Addressing
- Basic Network Documentation

🖧 Network Topology
The network consists of:
- 1 × Router (Router-on-a-Stick setup)
- 1 × Layer 2 Switch
- 6 × PCs assigned across 3 VLANs
- Static IPv4 addressing per subnet
- Trunk link between switch and router

📐 VLSM Subnetting Plan
A Class C network block is subnetted into three networks using VLSM.
Each subnet is assigned to one VLAN, with the default gateway configured on the router subinterfaces.

| VLAN | Subnet           | Gateway         | Host Range |
| ---- | ---------------- | --------------- | ---------- |
| 20   | `192.168.1.96/27` | `192.168.1.97` | 192.168.1.97 - 126         |
| 30   | `192.168.1.64/27` | `192.168.1.65` | 192.168.1.64 - 94          |
| 50   | `192.168.1.0/24` | `192.168.1.1` | 192.168.1.2 - 62        |

⚙️ Router Inter-VLAN Configuration 

```
interface GigabitEthernet0/0.50
 encapsulation dot1Q 50
 ip address  192.168.1.1 255.255.255.192

interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.1.65 255.255.255.225

interface GigabitEthernet0/0.20
 encapsulation dot1Q 30
 ip address 192.168.1.1 255.255.255.224
```
🖥️ Switch Configuration 

```
vlan 50
 name MANAGEMENT
vlan 30
 name STAFF
vlan 20
 name GUESTS

interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 20,30,50

interface range f0/1 - 2
 switchport mode access
 switchport access vlan 50

interface range f0/3 - 4
  switchport mode access
  switchport access vlan 30

intface range f0/5 - 6
  switchport mode access
  switchport access vlan 20

```

✔️ What This Project Demonstrates

This project highlights strong foundational networking skills such as:
- Correct subnetting & network planning
- Understanding VLAN segmentation
- Configuring inter-VLAN communication
- Applying router and switch IOS commands
- Designing clean, scalable small-office topologies

---


