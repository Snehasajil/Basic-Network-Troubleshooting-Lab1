# CST4585 – Enterprise Troubleshooting & Network Forensics Lab 1

This repository contains the configuration and documentation for **Lab 1** of the CST4585 course, focused on troubleshooting enterprise network issues related to VLANs, trunking, and DHCP.

## 📂 Repository Contents

- `CST4585_LAB_1.yaml` – Network topology and device configuration file.
- `Trouble shooting Lab 1.pdf` – Completed lab report with troubleshooting steps, root cause analysis, corrective actions, and verification results.

## 🧩 Lab Scenario

A previously working enterprise network experienced connectivity issues affecting both Staff and Student VLANs. The objective of this lab was to:

- Identify the network faults
- Analyze the root causes
- Apply corrective configurations
- Verify restoration of full connectivity

## 🔍 Issues Identified

1. **Incorrect VLAN Assignment**
   - Interface `Ethernet0/2` was assigned to VLAN 1 instead of VLAN 10.

2. **Trunk Misconfiguration**
   - Interface `Ethernet0/0` was configured as an access port rather than trunk mode.

3. **Incorrect DHCP Pool**
   - VLAN 20 DHCP pool used the wrong subnet (`10.0.1.0/24` instead of `10.0.0.32/27`).

## 🛠️ Corrective Actions

### Fix VLAN Assignment
```bash
interface Ethernet0/2
switchport access vlan 10
