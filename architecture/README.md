```mermaid
graph LR
    %% ============================
    %% STYLE DEFINITIONS
    %% ============================
    classDef identity fill:#0078D4,stroke:#004578,color:#fff;
    classDef mail fill:#107C10,stroke:#0B6A0B,color:#fff;
    classDef collab fill:#6B4C9A,stroke:#4B2E7A,color:#fff;
    classDef device fill:#E81123,stroke:#C50F1F,color:#fff;
    classDef security fill:#FFB900,stroke:#D48C00,color:#000;
    classDef automation fill:#00B7C3,stroke:#007C91,color:#fff;
    classDef domain fill:#8E8CD8,stroke:#5C5ACF,color:#fff;

    %% ============================
    %% CORE TENANT
    %% ============================
    A[Microsoft 365 Tenant] --> B[Entra ID]
    A --> C[Exchange Online]
    A --> D[SharePoint & Teams]
    A --> E[Intune Setup]
    A --> F[Security & Compliance]
    A --> G[Automation]
    A --> H[Domain Setup]

    %% DOMAIN SETUP
    subgraph Domain[domain-setup]
        H1[Domain Registrar]
        H2[DNS Records (MX / TXT / CNAME)]
        H3[M365 Domain Verification]
    end
    H --> H1
    H --> H2
    H --> H3
    H3 --> B
    class H,H1,H2,H3 domain;

    %% IDENTITY
    subgraph Identity[architecture]
        B1[Users]
        B2[Groups / Roles]
        B3[MFA / Conditional Access]
    end
    B --> B1
    B --> B2
    B --> B3
    class B,B1,B2,B3 identity;

    %% EXCHANGE ONLINE
    subgraph EXO[exchange-online]
        C1[Mailboxes]
        C2[Mail Flow]
        C3[Transport Rules]
    end
    C --> C1
    C --> C2
    C --> C3
    class C,C1,C2,C3 mail;

    %% SHAREPOINT & TEAMS
    subgraph SPO[sharepoint-teams]
        D1[SharePoint Sites]
        D2[Document Libraries]
        D3[Teams Channels]
        D4[Meetings / Chat]
    end
    D --> D1
    D --> D2
    D --> D3
    D --> D4
    class D,D1,D2,D3,D4 collab;

    %% INTUNE SETUP
    subgraph INTUNE[intune-setup]
        E1[Device Enrollment]
        E2[Compliance Policies]
        E3[App Protection]
    end
    E --> E1
    E --> E2
    E --> E3
    class E,E1,E2,E3 device;

    %% SECURITY & COMPLIANCE
    subgraph SEC[security-compliance]
        F1[Microsoft Defender]
        F2[Purview (DLP / Retention)]
        F3[Audit / eDiscovery]
        F4[Zero Trust Policies]
    end
    F --> F1
    F --> F2
    F --> F3
    F --> F4
    class F,F1,F2,F3,F4 security;

    %% AUTOMATION
    subgraph AUTO[automation]
        G1[PowerShell Scripts]
        G2[Python Automation]
        G3[CLI Tools (az / m365)]
    end
    G --> G1
    G --> G2
    G --> G3
    class G,G1,G2,G3 automation;

    %% USER ACCESS FLOW
    U[User / Admin] --> B
    B --> C
    B --> D
    B --> E
    B --> F
    B --> G
    B --> H
```
