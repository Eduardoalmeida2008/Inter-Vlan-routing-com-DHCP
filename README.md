# Corporate Infrastructure: Multi-Switch VLAN Segmentation

## 📌 Project Overview
This project focuses on the Layer 2 architectural design of a corporate network. The goal was to implement departmental isolation through VLANs across multiple switches, ensuring network efficiency and security by controlling broadcast domains and organizing device connectivity.

## 🚀 Technical Features
* **Departmental Segmentation:** Precise configuration of named VLANs to isolate departments (e.g., Sales, HR, IT).
* **VLAN Assignment:** Strategic port assignment on multiple Access Switches.
* **802.1Q Trunking:** Implementation of trunk links between switches to carry VLAN traffic across the entire topology.
* **Naming Standardization:** Strict naming convention for both network devices and VLAN IDs for easier troubleshooting.

## 📊 VLAN & Device Inventory
| Switch Name | VLAN ID | VLAN Name | Purpose |
| :--- | :--- | :--- | :--- |
| **S1-CORE** | 10 | **Sales** | Commercial Dept |
| **S2-ACCESS**| 20 | **Human_Resources** | HR Dept |
| **S3-ACCESS**| 30 | **IT_Admin** | Network Management |

## ⚙️ Verified Configuration Snippets

### VLAN Creation and Naming
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Sales
Switch(config-vlan)# exit
!
Switch(config)# interface range fastEthernet 0/1 - 10
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10
```
Trunking Configuration
````
Switch(config)# interface gigabitEthernet 0/1
Switch(config-if)# switchport mode trunk
````
🧪 Verification & Results
VLAN Database: Confirmed via show vlan brief showing all names and active ports.

Trunk Status: Verified through show interfaces trunk to ensure 802.1Q encapsulation is active.

````
Developed by [Eduardo]
````
