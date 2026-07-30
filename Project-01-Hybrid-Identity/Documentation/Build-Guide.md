# Build Guide

## Objective

Deploy a hybrid identity environment by synchronizing an on-premises Active Directory environment with Microsoft Entra ID using Microsoft Entra Connect.

## Prerequisites

- On-premises Windows Server 2022
- Microsoft 365 Developer Tenant or Microsoft Entra ID Tenant
- Global Administrator Account
- Local Domain Administrator Account
- Internet Connectivity
- Microsoft Entra Connect

## Architecture Overview

- Windows Server 2022 (DC01)
- Windows Server 2022 (DC02)_Replication
- Windows Server 2022 (DC03_SSO)_Replication
- Active Directory Domain Services (AD DS)
- Domain Name System
- File & Storage Services
- Organizational Units (OUs)
- Users and Groups
- Microsoft Entra Connect
- Microsoft Entra ID
- Multi-Factor Authentication (MFA)
- Self-Service Password Reset (SSPR)
- Conditional Access

## Step 1 - Install Windows Server

- Install Windows Server 2022
- Configure a static IP address
- Rename the server to `DC01`

## Step 2 - Deploy Active Directory

Install the Active Directory Domain Services role and promote the server to a Domain Controller.

### Domain Name

```text
corp.herbertlab.local
```

## Step 3 - Create Organizational Units

Create the following OUs:

```text
IT
HR
Finance
Service Accounts
```

## Step 4 - Create Users and Groups

### Sample Users

```text
John Smith
Jane Doe
IT Admin
```

### Sample Groups

```text
IT-Team
HR-Team
Finance-Team
```

## Step 5 - Install Microsoft Entra Connect

Configure:

- Password Hash Synchronization (PHS)
- Automatic Synchronization

Verify that users and groups synchronize successfully to Microsoft Entra ID.

## Step 6 - Configure Multi-Factor Authentication

Configure MFA for administrative accounts.

### Accounts Protected

```text
Global Administrator
Cloud Administrator
IT Administrators
```

## Step 7 - Configure Self-Service Password Reset

Enable SSPR for synchronized users.

Authentication methods:

- Microsoft Authenticator
- Mobile Phone

## Step 8 - Configure Conditional Access

Create a policy:

```text
Require MFA for Administrative Roles
```

Create a second policy:

```text
Block Legacy Authentication
```

## Step 9 - Configure Role-Based Access Control

Assign appropriate permissions using Entra ID groups.

Example:

```text
Helpdesk Team -> User Administrator
```

## Validation

Verify the following:

- User synchronizes successfully from Active Directory to Entra ID
- Group synchronization works correctly
- MFA prompt appears during sign-in
- SSPR functions successfully
- Conditional Access policies are enforced
- Microsoft 365 access works using synchronized identities

## Project Outcome

A fully functional hybrid identity environment integrating on-premises Active Directory with Microsoft Entra ID using modern identity and access management controls.
