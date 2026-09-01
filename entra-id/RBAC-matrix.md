```mermaid
graph LR
    %% Executive
    CEO[CEO<br/>SG_CEO<br/>Directory Reader] --> EX[Executive Team]
    COO[COO<br/>SG_COO<br/>Directory Reader] --> EX

    %% IT Department
    ITM[IT Manager<br/>SG_IT_Manager] --> IT_Team[IT Team]
    SA[Systems Administrator<br/>SG_Systems_Admin] --> IT_Team
    ITT[IT Support Technician<br/>SG_IT_Support_Tech] --> IT_Team

    %% HR Department
    HRM[HR Manager<br/>SG_HR_Manager] --> HR_Team[HR Team]
    HRS[HR Specialist<br/>SG_HR_Specialist] --> HR_Team

    %% Finance Department
    FM[Finance Manager<br/>SG_Finance_Manager] --> FIN_Team[Finance Team]
    ACC[Accountant<br/>SG_Accountant] --> FIN_Team

    %% Sales Department
    SM[Sales Manager<br/>SG_Sales_Manager] --> SALES_Team[Sales Team]
    SR[Sales Rep<br/>SG_Sales_Rep] --> SALES_Team

    %% Marketing Department
    MM[Marketing Manager<br/>SG_Marketing_Manager] --> MKT_Team[Marketing Team]
    MS[Marketing Specialist<br/>SG_Marketing_Specialist] --> MKT_Team

    %% Operations Department
    OM[Operations Manager<br/>SG_Operations_Manager] --> OPS_Team[Operations Team]
    OC[Operations Coordinator<br/>SG_Operations_Coordinator] --> OPS_Team

    %% Support Department
    SPM[Support Manager<br/>SG_Support_Manager] --> SUP_Team[Support Team]
    SPA[Support Agent<br/>SG_Support_Agent] --> SUP_Team

    %% SharePoint Sites (Permissions)
    EX --> SP_All_Read[All Sites (Read)]
    IT_Team --> SP_IT[IT Site]
    HR_Team --> SP_HR[HR Site]
    FIN_Team --> SP_FIN[Finance Site]
    SALES_Team --> SP_SALES[Sales Site]
    MKT_Team --> SP_MKT[Marketing Site]
    OPS_Team --> SP_OPS[Operations Site]
    SUP_Team --> SP_SUP[Support Site]

    %% Apps / Services
    ITM --> AdminCenter[Admin Center]
    ITM --> Intune[Intune]
    ITM --> Entra[Entra ID]

    SA --> SP_Admin[SharePoint Admin Center]
    SA --> Teams_Admin[Teams Admin Center]

    ITT --> Helpdesk[Helpdesk Portal]
    ITT --> Intune_Read[Intune (Read)]

    HR_Team --> HR_Apps[HR Apps]
    FIN_Team --> FIN_Apps[Finance Apps]
    SALES_Team --> CRM[CRM / Sales Apps]
    MKT_Team --> MKT_Apps[Marketing Apps]
    OPS_Team --> OPS_Apps[Operations Apps]
    SUP_Team --> Support_Apps[Support Apps]
```
