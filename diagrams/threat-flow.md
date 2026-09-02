\# Threat Flow Diagram



\## Threat Modeling Flow



The following diagram illustrates how an external attacker may interact with the application's attack surface and which security controls are expected to prevent or reduce the associated risks.



```mermaid

flowchart LR



&#x20;   A\[External Actor / Attacker]



&#x20;   A -->|Malicious Request| B\[Web Application]



&#x20;   B --> C{Authentication}



&#x20;   C -->|Invalid Credentials| D\[Authentication Failure]

&#x20;   C -->|Valid Credentials| E\[Authenticated Session]



&#x20;   E --> F{Authorization Check}



&#x20;   F -->|Denied| G\[Access Denied]

&#x20;   F -->|Allowed| H\[Application Logic]



&#x20;   H --> I\[Input Validation]

&#x20;   I -->|Invalid Input| J\[Validation Failure]

&#x20;   I -->|Valid Input| K\[Database Operations]



&#x20;   K --> L\[(Application Database)]



&#x20;   H --> M\[Security Logging]



&#x20;   A -.->|Spoofing| C

&#x20;   A -.->|Tampering| I

&#x20;   A -.->|Information Disclosure| K

&#x20;   A -.->|Elevation of Privilege| F

&#x20;   A -.->|Denial of Service| B

&#x20;   A -.->|Repudiation| M

Threat-to-Control Mapping

Threat	Attack Point	Primary Control

Spoofing	Authentication	Strong authentication and session protection

Tampering	User-controlled input	Server-side validation and integrity controls

Repudiation	Security events	Security logging and audit records

Information Disclosure	Application/data layer	Access control and data protection

Denial of Service	Web application	Rate limiting and resource controls

Elevation of Privilege	Authorization	Server-side authorization and least privilege

Key Security Decisions

Authentication



Authentication should occur before access to protected application resources.



Authorization



Authentication alone should not grant access to every resource. Authorization must verify whether the authenticated user has permission to perform the requested action.



Input Validation



All user-controlled input should be considered untrusted until validated on the server side.



Database Access



Database operations should be performed through controlled application logic using appropriate access controls and parameterized queries.



Security Logging



Security-relevant events should be logged to support detection, investigation, and accountability.



Trust Boundary Representation



The major trust boundaries represented by this flow are:



External Actor

&#x20;     |

&#x20;     | Untrusted Request

&#x20;     v

+---------------------------+

|      Web Application      |

|                           |

| Authentication            |

| Authorization             |

| Input Validation          |

| Application Logic         |

+---------------------------+

&#x20;     |

&#x20;     | Controlled Access

&#x20;     v

+---------------------------+

|    Data / Logging Layer   |

|                           |

| Database                  |

| Security Logs             |

+---------------------------+

Assessment Use



This threat-flow diagram supports the STRIDE analysis documented in:



../threat-model.md

../risk-register.md

../security-assessment.md

