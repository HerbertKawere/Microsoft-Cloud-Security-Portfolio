# Build Guide

## Objective

Deploy and manage Windows 11 endpoints using Microsoft Intune and Windows Autopilot while enforcing security controls through compliance policies, configuration profiles, and BitLocker encryption.

## Prerequisites

### Licensing

- Microsoft Intune
- Microsoft Entra ID
- Windows 11 Enterprise or Professional
- Microsoft 365 Business Premium, E3, or E5

### Requirements

- Microsoft Entra ID Tenant
- Windows 11 Test Device
- Local Administrator Account
- Internet Connectivity
- Microsoft Intune Administrator Role

---

## Architecture Components

### Identity

- Microsoft Entra ID
- User Accounts
- Security Groups
- Dynamic Device Groups

### Device Management

- Microsoft Intune
- Windows Autopilot
- Compliance Policies
- Configuration Profiles

### Endpoint Security

- BitLocker
- Microsoft Defender
- Microsoft Security Baselines

---

# Step 1 - Create User Groups

Navigate to:

```text
Microsoft Entra Admin Center
→ Groups
→ New Group
```

Create:

```text
Corporate Users
Corporate Devices
Pilot Devices
IT Administrators
```

Purpose:

- User assignments
- Policy assignments
- Device targeting

---

# Step 2 - Configure Automatic Enrollment

Navigate to:

```text
Microsoft Intune Admin Center
→ Devices
→ Enrollment
→ Automatic Enrollment
```

Configure:

```text
MDM User Scope = All
```

Verification:

```text
Microsoft Intune Enrollment Enabled
```

---

# Step 3 - Configure Windows Autopilot

Navigate to:

```text
Devices
→ Windows
→ Windows Enrollment
→ Devices
```

Import device hardware hash.

Create deployment profile:

```text
Corporate Windows Deployment
```

Settings:

```text
Join to Microsoft Entra ID as:
Azure AD Joined

Deployment Mode:
User Driven

Automatically Configure Device:
Yes

Skip Privacy Settings:
Yes
```

Assign:

```text
Pilot Devices
```

---

# Step 4 - Create Device Compliance Policy

Navigate to:

```text
Devices
→ Compliance Policies
→ Create Policy
```

Platform:

```text
Windows 10 and Later
```

Compliance Requirements:

```text
BitLocker Enabled
Secure Boot Enabled
TPM Enabled
Firewall Enabled
Microsoft Defender Enabled
```

Assign:

```text
Corporate Devices
```

---

# Step 5 - Create Configuration Profile

Navigate to:

```text
Devices
→ Configuration Profiles
→ Create Profile
```

Platform:

```text
Windows 10 and Later
```

Profile Type:

```text
Settings Catalog
```

Configure:

### Password Policy

```text
Minimum Length: 12
Complexity Enabled
```

### Screen Lock

```text
15 Minute Timeout
```

### Firewall

```text
Enabled
```

### Microsoft Defender

```text
Real-Time Protection Enabled
```

Assign:

```text
Corporate Devices
```

---

# Step 6 - Configure BitLocker

Navigate to:

```text
Endpoint Security
→ Disk Encryption
→ Create Policy
```

Platform:

```text
Windows 10 and Later
```

Configuration:

```text
Enable BitLocker
Store Recovery Keys in Entra ID
Encryption Method: XTS-AES 256
Silent Encryption Enabled
```

Assign:

```text
Corporate Devices
```

---

# Step 7 - Deploy Test Device

Perform a Windows Reset on the test device.

During setup:

```text
Connect to Internet
Sign in using Entra ID Account
```

Expected Result:

```text
Device registered with Entra ID
Device enrolled into Intune
Policies automatically applied
```

---

# Step 8 - Verify Device Enrollment

Navigate to:

```text
Devices
→ All Devices
```

Verify:

```text
Device appears in Intune
Device is Entra ID Joined
Ownership = Corporate
```

---

# Step 9 - Verify Compliance

Navigate to:

```text
Devices
→ Monitor
→ Compliance
```

Verify:

```text
Status = Compliant
```

Review:

```text
Encryption Status
Firewall Status
Defender Status
```

---

# Step 10 - Verify BitLocker

Navigate to:

```text
manage-bde -status

