# cisco-intervlan-routing-vlsm-lab

Inter-VLAN Routing (Router-on-a-Stick) and VLSM Subnetting lab built on Cisco Packet Tracer.

## 📐 Network Topology
![Network Topology](./1.%20Network%20Topology.png)

## 📊 VLSM Subnetting & Addressing Scheme

* **Base Network:** `10.0.0.0/8`

| Site / VLAN | Requirements | Network Address | Subnet Mask | 1st Usable IP | Last Usable IP | Broadcast Address |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **IT (VLAN 10)** | 100 hosts | `10.0.0.0` | `255.255.255.128` (`/25`) | `10.0.0.1` | `10.0.0.126` | `10.0.0.127` |
| **HR (VLAN 20)** | 59 hosts | `10.0.0.128` | `255.255.255.192` (`/26`) | `10.0.0.129` | `10.0.0.190` | `10.0.0.191` |
| **Sales (VLAN 30)** | 27 hosts | `10.0.0.192` | `255.255.255.224` (`/27`) | `10.0.0.193` | `10.0.0.222` | `10.0.0.223` |
| **Management (VLAN 90)** | 12 hosts | `10.0.0.224` | `255.255.255.240` (`/28`) | `10.0.0.225` | `10.0.0.238` | `10.0.0.239` |

---

## 🛠️ Tasks & Configuration Highlights
1. **VLSM Address Calculation:** Subnetted `10.0.0.0/8` using variable-length subnet masks (`/25`, `/26`, `/27`, `/28`) to fit department host requirements.
2. **VLAN Creation & Access Port Allocation:** Created VLANs 10, 20, 30, and 90 across all switches and assigned end devices to their respective ports.
3. **802.1Q Trunking & Native VLAN:** Configured trunking on inter-switch links with **VLAN 90** set as the Native VLAN.
4. **Router-on-a-Stick (ROAS):** Configured sub-interfaces on Router R1 (`Gig0/0/0.10`, `.20`, `.30`, `.90`) using `encapsulation dot1Q` for inter-VLAN routing.
5. **Switch SVI & Telnet Security:** Configured management IP addresses on switch SVIs (VLAN 90) and set up VTY lines for remote access.

---

## 🧪 Verification & Proof of Work
* **Routing Table:** Verified active sub-interfaces and connected subnets via `show ip route` on R1.
* **Trunking Status:** Confirmed 802.1Q trunk ports and Native VLAN 90 via `show interfaces trunk` on `Sw-1`.
* **Connectivity Test:** Successfully performed ICMP ping across different VLANs via R1.
* **Remote Management:** Verified Telnet connectivity from the Admin laptop to both R1 and switches.

---

## 📁 Repository Files
* `Lab Inter-VLAN routing-vlsm.pkt`: Packet Tracer topology and completed configuration file.
* `Inter-VLAN Routing Lab.pdf`: Blank lab worksheet for practice.
* `Inter-VLAN Routing Lab (with answers).docx`: Full solution guide with configurations.
* `1. Network Topology.png`: High-resolution network topology.
* `2. VLSM Table Address.png`: VLSM subnetting breakdown.
* `3. Routing Table.png`: Output of `show ip route` on R1.
* `4. Ping Test.png`: Verification of Inter-VLAN reachability.
* `5. Switche Config (Trunk).png`: Output of `show interfaces trunk` on Sw-1.
* `6. Telnet Access to Router and Switches.png`: Verification of Telnet remote login.

---

## 🚀 How to Use
1. Download and open [Cisco Packet Tracer](https://www.netacad.com/).
2. Clone or download this repository.
3. Open `Inter-VLAN Routing Lab.pdf` to attempt the exercise on your own.
4. Open `Lab Inter-VLAN routing-vlsm.pkt` or refer to `Inter-VLAN Routing Lab (with answers).docx` to inspect completed configurations.
