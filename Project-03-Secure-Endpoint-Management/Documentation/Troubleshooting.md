# Troubleshooting

## Issue 1 - Device Not Enrolling in Intune

### Problem

A Windows 11 device successfully joined Microsoft Entra ID but did not appear in Microsoft Intune.

### Root Cause

Automatic MDM enrollment was not configured for the user account.

### Resolution

Verified the MDM user scope configuration:

```text
Intune Admin Center
→ Devices
→ Enrollment
→ Automatic Enrollment
```

Configured:

```text
MDM User Scope = All
```

### Result

The device successfully enrolled in Microsoft Intune.

---

## Issue 2 - Windows Autopilot Profile Not Assigned

### Problem

The device completed setup without receiving the Windows Autopilot deployment profile.

### Root Cause

The device was not assigned to the correct Autopilot device group.

### Resolution

Verified:

- Hardware hash upload
- Dynamic group membership
- Deployment profile assignment

Forced device synchronization and reassigned the profile.

### Result

The device received the Autopilot deployment profile successfully.

---

## Issue 3 - Device Shows as Non-Compliant

### Problem

A Windows 11 device reported a non-compliant status in Microsoft Intune.

### Root Cause

BitLocker encryption was not enabled on the device.

### Resolution

Reviewed compliance policy requirements and confirmed BitLocker settings.

Forced policy synchronization:

```text
Settings
→ Accounts
→ Access Work or School
→ Info
→ Sync
```

### Result

The device became compliant after BitLocker encryption completed.

---

## Issue 4 - BitLocker Encryption Not Starting

### Problem

The assigned BitLocker policy was deployed but encryption did not begin.

### Root Cause

The Trusted Platform Module (TPM) was not properly initialized.

### Resolution

Verified:

```text
TPM Enabled
TPM Activated
TPM Ready for Use
```

Initialized TPM and synchronized Intune policies.

### Result

BitLocker encryption started successfully and recovery keys were uploaded to Microsoft Entra ID.

---

## Issue 5 - Recovery Key Missing from Entra ID

### Problem

BitLocker encryption completed but recovery keys were not visible in Microsoft Entra ID.

### Root Cause

The device had not completed policy synchronization.

### Resolution

Forced device sync and verified device registration status.

Confirmed encryption policy assignment.

### Result

Recovery keys appeared in Microsoft Entra ID successfully.

---

## Issue 6 - Configuration Profile Not Applying

### Problem

Password and screen lock settings were not applied to the endpoint.

### Root Cause

The device was not included in the target assignment group.

### Resolution

Verified group membership and reassigned the configuration profile to the correct device group.

### Result

The configuration profile applied successfully.

---

## Issue 7 - Microsoft Defender Policy Not Applying

### Problem

Defender settings configured in Intune were not visible on the endpoint.

### Root Cause

Multiple policies contained conflicting settings.

### Resolution

Reviewed policy conflicts in Intune:

```text
Devices
→ Monitor
→ Configuration
```

Removed overlapping configurations and redeployed the policy.

### Result

Microsoft Defender settings applied correctly.

---

## Issue 8 - Firewall Policy Failed Deployment

### Problem

Firewall policy deployment status displayed an error.

### Root Cause

A locally configured firewall setting conflicted with the Intune policy.

### Resolution

Reset the local firewall configuration and synchronized the device.

### Result

Firewall policy deployed successfully.

---

## Issue 9 - Endpoint Privilege Management (EPM) Elevation Failure

### Problem

A standard user could not elevate an approved application.

### Root Cause

The application rule was not configured correctly in the EPM policy.

### Resolution

Verified:

- Elevation settings
- Target application path
- Rule assignment

Republished the EPM policy.

### Result

Application elevation worked as expected.

---

## Issue 10 - Microsoft Defender for Endpoint Onboarding Failed

### Problem

The device did not appear in Microsoft Defender for Endpoint.

### Root Cause

The Defender onboarding policy had not been assigned to the device group.

### Resolution

Verified:

```text
Endpoint Security
→ Microsoft Defender for Endpoint
```

Assigned onboarding policy to the Corporate Devices group.

### Result

The device appeared in Microsoft Defender for Endpoint successfully.

---

## Issue 11 - Attack Surface Reduction Rules Not Enforced

### Problem

Attack Surface Reduction policies were visible in Intune but not enforced on the endpoint.

### Root Cause

The device had not completed policy synchronization.

### Resolution

Forced synchronization and validated policy deployment using:

```powershell
Get-MpPreference
```

### Result

Attack Surface Reduction rules became active.

---

## Issue 12 - Device Missing from Dynamic Device Group

### Problem

The endpoint did not receive assigned applications or policies.

### Root Cause

The dynamic membership rule did not match the device attributes.

### Resolution

Reviewed and corrected the dynamic membership rule.

Example:

```text
(device.deviceOwnership -eq "Company")
```

### Result

The device was successfully added to the target group.

---

# Key Troubleshooting Lessons

- Proper group assignments are critical for policy deployment.
- Intune synchronization should always be verified before investigating policy failures.
- TPM readiness is essential for successful BitLocker deployment.
- Testing policies with pilot devices helps identify issues before broad deployment.
- Dynamic groups require careful validation to ensure devices receive the correct configurations.
- Monitoring compliance and endpoint security status provides early visibility into deployment issues.
