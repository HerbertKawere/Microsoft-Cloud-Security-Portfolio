Project 01 - Identity & Access Security
Overview
This project demonstrates identity and access security using Active Directory, Microsoft Entra ID, MFA, Conditional Access, Privileged Identity Management (PIM), Access Reviews, and Entitlement Management.

The objective is to implement core Zero Trust identity controls that strengthen authentication, authorization, governance, and privileged access management.

Project Type
Personal Lab Environment

Scenario
A fictional organization requires secure access to Microsoft 365 resources while reducing identity-related risks through modern identity and governance controls.

Objectives
Implement hybrid identity
Configure MFA
Implement Conditional Access
Configure PIM
Perform Access Reviews
Implement Entitlement Management
Validate security controls
Architecture
Identity Architecture

Security Controls Demonstrated
1. Hybrid Identity
Active Directory identities are synchronized to Microsoft Entra ID using Microsoft Entra Connect, providing a unified identity platform across on-premises and cloud resources.

Screenshot
Hybrid Identity

2. Multi-Factor Authentication (MFA)
MFA was configured to strengthen authentication security and reduce the risk of unauthorized access from compromised credentials.

Screenshot
MFA

3. Conditional Access
Conditional Access policies were configured to enforce MFA, control access, and support Zero Trust principles.

Screenshot
Conditional Access

4. Privileged Identity Management (PIM)
PIM was used to implement Just-In-Time administrative access, reducing standing privileges and supporting least privilege.

Screenshot
PIM

5. Access Reviews
Access Reviews were configured to periodically validate user access and reduce excessive permissions.

Screenshot
Access Reviews

6. Entitlement Management
Access Packages were created to simplify access requests and improve identity governance.

Screenshot
Entitlement Management

7. Validation
Identity controls were verified through sign-in testing and audit logs.

Screenshot
Sign-In Logs

Test Results
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
