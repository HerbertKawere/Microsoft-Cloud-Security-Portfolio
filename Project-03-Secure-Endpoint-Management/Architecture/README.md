# Project 03 - Secure Endpoint Management

## Overview

This project demonstrates the deployment and management of Windows 11 endpoints using Microsoft Intune and Windows Autopilot, while implementing modern endpoint security controls and device compliance standards.

The solution leverages Microsoft Entra ID, Microsoft Intune, Windows Autopilot, BitLocker, Compliance Policies, Configuration Profiles, Endpoint Privilege Management (EPM), Endpoint Detection and Response (EDR), and Attack Surface Reduction (ASR) rules to provide a secure and centrally managed endpoint environment.

---

## Objective

Design and implement a secure endpoint management solution that enables:

- Automated Windows device provisioning
- Centralized endpoint administration
- Device compliance monitoring
- Endpoint security policy enforcement
- BitLocker encryption management
- Endpoint Detection and Response (EDR)
- Least privilege administration
- Secure access to corporate resources

---

## Architecture

Architecture/Secure-Endpoint-Management-Architecture.png

### Solution Overview

The solution utilizes Microsoft Entra ID and Microsoft Intune to manage and secure Windows 11 devices throughout their lifecycle.

Windows Autopilot automates device deployment and enrollment, while Intune enforces compliance requirements, configuration profiles, and endpoint security controls. Security technologies including BitLocker, Endpoint Privilege Management (EPM), Endpoint Detection and Response (EDR), Attack Surface Reduction (ASR), and Microsoft Defender provide layered protection against threats and unauthorized access.

---

## Technologies Used

### Identity

- Microsoft Entra ID
- Dynamic Device Groups
- User & Group Management

### Device Management

- Microsoft Intune
- Windows Autopilot
- Compliance Policies
- Configuration Profiles

### Endpoint Security

- BitLocker Disk Encryption
- Microsoft Defender Antivirus
- Microsoft Defender for Endpoint
- Endpoint Detection and Response (EDR)
- Endpoint Privilege Management (EPM)
- Attack Surface Reduction (ASR)
- Microsoft Defender Firewall
- Security Baselines
- Threat & Vulnerability Management

### Operating System

- Windows 11 Enterprise

---

## Key Features Implemented

### Windows Autopilot

- User-driven deployment
- Microsoft Entra ID join
- Automated device provisioning
- Zero-touch deployment experience

### Compliance Policies

- BitLocker required
- Secure Boot validation
- TPM validation
- Firewall requirements
- Microsoft Defender health checks

### Configuration Profiles

- Password complexity requirements
- Screen lock policies
- Microsoft Defender settings
- Device security configurations

### Disk Encryption

- BitLocker deployment
- Recovery key escrow to Microsoft Entra ID
- Silent encryption enforcement

### Endpoint Security

- Firewall management
- Security Baselines
- Endpoint Privilege Management
- Endpoint Detection and Response
- Attack Surface Reduction rules
- Threat & Vulnerability Management

---

## Documentation

Detailed implementation documentation is available below:

- Documentation/Build-Guide.md
- Documentation/Troubleshooting.md
- Documentation/Lessons-Learned.md

---

## Screenshots

The Screenshots directory contains validation and configuration evidence for:

- Windows Autopilot Deployment Profile
- Device Enrollment
- Compliance Policies
- Configuration Profiles
- BitLocker Configuration
- Endpoint Security Policies
- Device Compliance Status
- Microsoft Defender Integration
- Recovery Key Verification

---

## Scripts

The Scripts directory contains PowerShell scripts used for:

- Device validation
- Enrollment verification
- Compliance verification
- BitLocker status validation
- Endpoint management tasks

---

## Skills Demonstrated

- Microsoft Intune Administration
- Windows Autopilot Deployment
- Microsoft Entra ID Integration
- Compliance Management
- Endpoint Security Management
- BitLocker Administration
- Endpoint Detection and Response (EDR)
- Endpoint Privilege Management (EPM)
- Microsoft Defender Administration
- Attack Surface Reduction (ASR)
- Security Baseline Deployment
- Device Lifecycle Management

---

## Project Outcome

Successfully implemented a secure endpoint management solution capable of provisioning, managing, monitoring, and securing Windows 11 endpoints through Microsoft Intune and Microsoft Entra ID.

The environment enforces enterprise security standards through centralized policy management, automated deployment, BitLocker encryption, compliance monitoring, and advanced endpoint protection controls.

---

## Certification Alignment

This project aligns with the following Microsoft certification objectives:

- **MD-102** – Microsoft Endpoint Administrator
- **SC-300** – Microsoft Identity and Access Administrator
- **SC-200** – Microsoft Security Operations Analyst (Endpoint Security Integration)

---
**Author:** Herbert Kawere  
**Repository:** Microsoft-Cloud-Security-Portfolio
