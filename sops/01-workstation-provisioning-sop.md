# Standard Operating Procedure: Workstation Provisioning & Deployment

**Document ID:** SOP-IT-001  
**Version:** 1.0  
**Target Audience:** Tier 1/2 IT Support Technicians, Operations Coordinators  

---

## 1. Purpose & Scope
This procedure standardizes the unboxing, OS staging, baseline configuration, and Active Directory domain onboarding of corporate laptops and desktop workstations prior to user assignment.

## 2. Prerequisites
* **Local Admin Credentials** for initial staging.
* **Domain Admin Access** for Active Directory joining.
* **Hardware:** Ethernet cable, target workstation, hardware asset tag.

## 3. Step-by-Step Staging Procedure

### Step 1: Asset Tagging & Intake
1. Unbox the device and verify hardware specs match the Purchase Order (PO).
2. Affix a physical asset tag barcode to the bottom/back panel of the machine.
3. Log the **Asset Tag ID**, **Serial Number**, and **MAC Address** into the IT Asset Management (ITAM) registry.

### Step 2: OS Staging & System Prep
1. Boot system and initiate corporate OS image deployment (Windows 11 Enterprise).
2. Name the device using corporate naming convention: `WS-[DEPT]-[ASSETTAG]` (e.g., `WS-ACCT-1042`).

### Step 3: Domain Onboarding & Group Policy
1. Connect device to staging VLAN (VLAN 10).
2. Open PowerShell as Administrator and join machine to Active Directory domain:
   ```powershell
   Add-Computer -DomainName "corp.domain.local" -OUPath "OU=Workstations,DC=corp,DC=local" -Restart
3. Upon reboot, force a Group Policy update:
   ```cmd
   gpupdate /force
