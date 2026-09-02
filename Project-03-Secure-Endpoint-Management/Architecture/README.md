flowchart TD

A[Microsoft Entra ID]
--> B[Microsoft Intune]

B --> C[Windows Autopilot]
B --> D[Compliance Policies]
B --> E[Configuration Profiles]

C --> F[Windows 11 Endpoint]
D --> F
E --> F

F --> G[BitLocker Recovery Keys]
F --> H[Microsoft Defender]
F --> I[Company Apps]

G --> J[Security & Compliance]
H --> J
I --> J
