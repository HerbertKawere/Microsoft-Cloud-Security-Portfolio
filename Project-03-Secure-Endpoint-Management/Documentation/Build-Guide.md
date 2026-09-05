# Build Guide

## Objective

Deploy and manage Windows 11 endpoints using Microsoft Intune and Windows Autopilot while enforcing security controls through compliance policies, configuration profiles, endpoint security policies, and BitLocker encryption.

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

- BitLocker Disk Encryption
- Microsoft Defender Antivirus
- Microsoft Defender for Endpoint (EDR)
- Microsoft Defender Firewall
- Endpoint Privilege Management (EPM)
- Attack Surface Reduction (ASR) Rules
- Security Baselines
- Device Compliance Monitoring
- Threat & Vulnerability Management

---

## Step 1 - Create User Groups

Navigate to:

Microsoft Entra Admin Center

```text
Groups
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
- Device assignments
- Policy assignments
- Endpoint security targeting

---

## Step 2 - Configure Automatic Enrollment

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

Validation:

```text
Automatic device enrollment enabled
```

---

## Step 3 - Configure Windows Autopilot

Navigate to:

```text
Devices
→ Windows
→ Windows Enrollment
→ Devices
```
Autopilot device preparations
Import the hardware hash.

Create a deployment profile:

```text
Corporate Windows Deployment
```

Configuration:

```text
Deployment Mode: User Driven
Join Type: Microsoft Entra Joined
Automatically Configure Device: Yes
Skip Privacy Settings: Yes
```

Assign:

```text
Pilot Devices
```

---

## Step 4 - Create Device Compliance Policy

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

Configure:

```text
BitLocker Enabled
Firewall Enabled
TPM Enabled
Secure Boot Enabled
Microsoft Defender Enabled
Password Required
```

Assign:

```text
Corporate Devices
```

---

## Step 5 - Create Configuration Profile

Navigate to:

```text
Devices
→ Configuration Profiles
→ Create Profile
```

Profile Type:

```text
Settings Catalog
```

Configure:

### Password Policy

```text
Minimum Length: 12
Password Complexity Enabled
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
Cloud Protection Enabled
```

Assign:

```text
Corporate Devices
```

---

## Step 6 - Configure BitLocker

Navigate to:

```text
Endpoint Security
→ Disk Encryption
→ Create Policy
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

## Step 7 - Configure Endpoint Security

Navigate to:

```text
Endpoint Security
```

### Configure Firewall

Create Firewall Policy:

```text
Domain Profile = Enabled
Private Profile = Enabled
Public Profile = Enabled
```

Assign:

```text
Corporate Devices
```

---

### Configure Endpoint Privilege Management (EPM)

Create Endpoint Privilege Management Policy:

```text
Allow approved application elevation
Reduce permanent local administrator accounts
Implement just-in-time elevation
```

Assign:

```text
Corporate Devices
```

---

### Configure Endpoint Detection and Response (EDR)

Integrate Microsoft Defender for Endpoint.

Configure:

```text
EDR in Block Mode
Threat Detection
Automated Investigation
Device Risk Assessment
```

Validate device onboarding.

---

### Configure Attack Surface Reduction (ASR)

Create Attack Surface Reduction Policy.

Enable rules such as:

```text
Block Office applications from creating child processes
Block executable content from email and webmail
Block credential stealing from LSASS
Block untrusted and unsigned processes
```

Assign:

```text
Corporate Devices
```

---

### Configure Security Baselines

Navigate to:

```text
Endpoint Security
→ Security Baselines
```

Deploy:

```text
Windows 11 Security Baseline
Microsoft Defender Security Baseline
Microsoft Edge Security Baseline
```

Assign:

```text
Corporate Devices
```

---

### Configure Threat and Vulnerability Management

Within Microsoft Defender:

```text
Review Security Recommendations
Monitor Exposure Score
Assess Device Vulnerabilities
Track Remediation Activities
```

---

## Step 8 - Deploy Test Device

Perform a Windows reset on the test device.


