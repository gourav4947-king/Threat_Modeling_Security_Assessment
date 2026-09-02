# Threat Flow Diagram

## Threat Modeling Flow

The following diagram illustrates how an external attacker may interact with the application's attack surface and which security controls are expected to prevent or reduce the associated risks.

```mermaid
flowchart TD

    A[External Attacker] --> B[Internet]

    B --> C[Web Interface]

    C --> D[Authentication]

    D --> E[Session Management]

    E --> F[Authorization]

    F --> G[Application Logic]

    G --> H[Input Validation]

    G --> I[Database]

    G --> J[Logging and Monitoring]

    A --> K[Malicious Input]

    K --> C

    K --> H

    H -->|Validated Input| G

    H -->|Rejected Input| L[Security Event]

    L --> J

    D -->|Failed Login| J

    F -->|Unauthorized Access Attempt| J

    G -->|Data Request| I

    I -->|Data Response| G

    G --> M[Application Response]

    M --> C

    C --> B

    B --> A

    subgraph Attack_Surface[Attack Surface]
        C
        D
        E
        F
        G
        H
        I
    end

    subgraph Security_Controls[Security Controls]
        H
        J
    end

    subgraph Threats[Threat Categories]
        T1[Spoofing]
        T2[Tampering]
        T3[Repudiation]
        T4[Information Disclosure]
        T5[Denial of Service]
        T6[Elevation of Privilege]
    end

    T1 --> D
    T2 --> H
    T3 --> J
    T4 --> I
    T5 --> C
    T6 --> F
