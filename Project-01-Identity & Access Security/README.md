## Project 01 - Identity & Access Security

## Overview
This project demonstrates how Microsoft Entra ID can be used to implement Zero Trust identity controls in a hybrid environment.

The solution integrates hybrid identity, secure authentication, privileged access management, and identity governance to reduce identity-related risk and strengthen access control.

## Scenario
Secure Networks Ltd. requires secure access to Microsoft 365 resources while reducing the attack surface associated with user and administrative accounts.

## Implementation
- Hybrid Identity. Implemented synchronization between Active Directory and Microsoft Entra ID using Entra Connect.


  


- Multi-Factor Authentication (MFA)
MFA was configured to strengthen authentication security and reduce the risk of unauthorized access from compromised credentials.

- Conditional Access
Conditional Access policies were configured to enforce MFA, control access, and support Zero Trust principles.

- Privileged Identity Management (PIM)
PIM was used to implement Just-In-Time administrative access, reducing standing privileges and supporting least privilege.

- Access Reviews
Access Reviews were configured to periodically validate user access and reduce excessive permissions.

- Entitlement Management
Access Packages were created to simplify access requests and improve identity governance.

- Validation
Identity controls were verified through sign-in testing and audit logs.

## Test Results
Test	Expected Result	Outcome
MFA Challenge	User prompted for MFA	✅ Success
Conditional Access	Policy enforced	✅ Success
PIM Activation	Elevation required	✅ Success
Access Review	Review generated	✅ Success
Security Considerations
Zero Trust principles
Least Privilege access
Just-In-Time administration
Identity Governance
Strong authentication
Continuous access validation
Lessons Learned
Improved understanding of Conditional Access policy evaluation.
Improved understanding of hybrid identity architecture.
Learned how PIM reduces standing administrative privileges.
Gained practical experience with identity governance controls.
Better understanding of Zero Trust identity security.

## Technologies Used
- Active Directory
- Microsoft Entra ID
- Entra Connect
- Multi-Factor Authentication (MFA)
- Conditional Access
- Privileged Identity Management (PIM)
- Access Reviews
- Entitlement Management
