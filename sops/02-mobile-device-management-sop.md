# Standard Operating Procedure: Mobile Device Management (MDM) & Fleet Onboarding

**Document ID:** SOP-IT-002  
**Version:** 1.0  
**Effective Date:** September 2026  
**Target Audience:** IT Coordinators, Mobile Operations Specialists, Service Desk Technicians  

---

## 1. Purpose & Scope
This procedure standardizes the intake, security staging, policy enrollment, and deployment of corporate mobile hardware (iPads, iPhones, cellular devices, and handheld radios). It ensures all mobile assets adhere to enterprise security policies prior to department release.

## 2. Prerequisites & Access Requirements
* **Apple Business Manager (ABM)** administrative console access.
* **MDM Portal** administrator rights.
* **Hardware:** Enterprise asset tag labels, USB-C provisioning cable, target mobile hardware.

---

## 3. Step-by-Step Provisioning Procedure

### Step 1: Intake & Asset Tagging
1. Unbox the device and inspect physical hardware for defects.
2. Record the device **Serial Number**, **IMEI** (if cellular), and **Wi-Fi MAC Address** in the IT Asset Management (ITAM) registry.
3. Affix a physical barcode asset tag to the lower-back portion of the device.

### Step 2: Automated Device Enrollment (ADE)
1. Verify the device order is recognized within **Apple Business Manager (ABM)** via the reseller ID.
2. Assign the device to the primary corporate **MDM Server Instance**.
3. Power on the device; connect to the staging Wi-Fi network (`Corp-Staging`).
4. During initial iOS setup, verify the **Remote Management** screen appears, confirming automated enrollment.

### Step 3: Security Configuration Profile Deployment
The MDM server automatically applies the **Corporate Mobile Baseline Policy**:
* **Passcode Enforcement:** Mandatory 6-digit alphanumeric passcode requirement.
* **Screen Lock:** Maximum 2-minute inactivity timeout before device auto-locks.
* **Data Protection:** Full-disk hardware encryption enabled.
* **Application Control:** App Store disabled; only approved enterprise applications (MS Outlook, Teams, OneDrive) deployed via the Private App Catalog.
* **Network Profile:** Automatic WPA2-Enterprise Wi-Fi certificate deployment.

### Step 4: User Assignment & Staging
1. Assign the device record to the designated employee in the MDM portal.
2. Configure Exchange Online profile for automated user sign-in.
3. Place device in protective enterprise casing.

---

## 4. Lost / Stolen Device Emergency Protocol

In the event an end-user reports a lost or stolen corporate mobile asset:

1. **Immediate Lock:** Log into the MDM portal, select the target Asset ID, and issue a **Device Lock** command with a custom contact message on the lock screen.
2. **Location Tracking:** Enable **Lost Mode** to track device GPS coordinates for security recovery.
3. **Remote Wipe:** If the device is unrecovered after **24 hours** (or immediately if compromised), execute a **Remote Erase** command to wipe all enterprise data and restore factory defaults.
4. **Carrier Notification:** Notify the cellular provider to suspend the SIM card and block the device IMEI.

---

## 5. Verification & User Handoff
1. Confirm all managed apps are installed and operational.
2. Have the end-user test biometrics (Face ID/Touch ID) and corporate email access.
3. Obtain employee signature on the **Mobile Asset Responsibility Agreement**.
