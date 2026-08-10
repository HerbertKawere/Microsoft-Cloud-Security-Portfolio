# Troubleshooting

## Issue 1 - Unable to Join DC02 to the Domain

### Problem

DC02 was unable to join the `snl.herbertlab.local` domain.

### Root Cause

DNS was not configured to point to DC01.

### Resolution

Configured the preferred DNS server on DC02 to use the IP address of DC01 and verified connectivity using:

```powershell
nslookup snl.herbertlab.local
```

### Result

DC02 successfully joined the domain.

---

## Issue 2 - Active Directory Replication Failure

### Problem

Replication between DC01 and DC02 was not occurring as expected.

### Root Cause

DNS records had not fully replicated and firewall rules were preventing communication.

### Resolution

Verified AD replication services, DNS configuration, and executed:

```powershell
repadmin /replsummary
```

```powershell
repadmin /syncall
```

### Result

Replication completed successfully with no failures.

---

## Issue 3 - Users Not Synchronizing to Microsoft Entra ID

### Problem

Newly created Active Directory users did not appear in Microsoft Entra ID.

### Root Cause

The synchronization cycle had not completed.

### Resolution

Forced synchronization using:

```powershell
Start-ADSyncSyncCycle -PolicyType Delta
```

### Result

Users successfully synchronized to Microsoft Entra ID.

---

## Issue 4 - MFA Not Being Applied

### Problem

Administrative accounts were able to sign in without MFA.

### Root Cause

The Conditional Access policy did not include the target users.

### Resolution

Reviewed policy assignments and added the appropriate administrative groups.

### Result

Users were prompted for MFA during sign-in.

---

## Issue 5 - Self-Service Password Reset Not Working

### Problem

Users could not reset their passwords using SSPR.

### Root Cause

Authentication methods were not configured.

### Resolution

Enabled:

- Microsoft Authenticator
- Mobile Phone

### Result

Users were able to complete password resets successfully.

---

## Issue 6 - Microsoft Entra Connect Installation Failed

### Problem

Microsoft Entra Connect setup could not validate credentials.

### Root Cause

Incorrect administrative permissions were used during setup.

### Resolution

Used a Global Administrator account and reran the installation.

### Result

Microsoft Entra Connect installed successfully.

---

## Issue 7 - Conditional Access Lockout Risk

### Problem

A newly created Conditional Access policy had the potential to lock out administrators.

### Root Cause

No exemptions were configured.

### Resolution

Created a break-glass account and excluded it from Conditional Access policies before deployment.

### Result

Administrative access remained available during testing and future policy changes.
