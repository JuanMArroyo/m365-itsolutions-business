# 🧩 Microsoft Entra ID — IT Solutions Business

## 📘 Overview
This project documents the **Microsoft Entra ID (formerly Azure Active Directory)** configuration for the **IT Solutions Business Tenant**.  
It demonstrates a full enterprise identity architecture including **users**, **groups**, **RBAC structure**, and **privileged access management**.

The goal:  
> Build a realistic, secure, and scalable identity environment that mirrors how modern organizations manage access in Microsoft 365 and Entra ID.

---

## 🧠 Key Objectives
- Implement **Role-Based Access Control (RBAC)** across departments  
- Create **departmental security groups** and **Microsoft 365 groups**  
- Assign **job roles** and **permissions** based on least privilege  
- Configure **Privileged Identity Management (PIM)** for temporary admin access  
- Document the full **identity architecture** for portfolio and audit purposes  

---

## 🧩 Architecture Summary
The tenant is structured around **departments**, **roles**, and **groups**, each mapped to specific permissions and resources.

### Departments
- Executive  
- IT  
- HR  
- Finance  
- Sales  
- Marketing  
- Operations  
- Support

  ![Groups & Roles](screenshots/entra-id/groups-roles.png)
  

### Core Identity Components
| Component | Description |
|------------|-------------|
| **Users** | Created with job titles, departments, and role groups |
| **Groups** | Security and Microsoft 365 groups for access control |
| **Roles** | Job-based access assignments |
| **Permissions** | Attached to groups, not individuals |
| **Admin Roles** | Directory Reader, Privileged Role Admin, Helpdesk Admin |
| **PIM** | Time-limited admin access with MFA and approval workflow |

![Users & Positions](screenshots/entra-id/users-positions.png)

---

## 🔐 RBAC Matrix
The RBAC model defines access by **role**, **group**, and **resource**.

```mermaid
graph LR

    %% Executive
    CEO["CEO - SG_CEO"] --> EX["Executive Team"]
    COO["COO - SG_COO"] --> EX

    %% IT Department
    ITM["IT Manager - SG_IT_Manager"] --> IT_Team["IT Team"]
    SA["Systems Admin - SG_Systems_Admin"] --> IT_Team
    ITT["IT Support Tech - SG_IT_Support_Tech"] --> IT_Team

    %% HR Department
    HRM["HR Manager - SG_HR_Manager"] --> HR_Team["HR Team"]
    HRS["HR Specialist - SG_HR_Specialist"] --> HR_Team

    %% Finance Department
    FM["Finance Manager - SG_Finance_Manager"] --> FIN_Team["Finance Team"]
    ACC["Accountant - SG_Accountant"] --> FIN_Team

    %% Sales Department
    SM["Sales Manager - SG_Sales_Manager"] --> SALES_Team["Sales Team"]
    SR["Sales Rep - SG_Sales_Rep"] --> SALES_Team

    %% Marketing Department
    MM["Marketing Manager - SG_Marketing_Manager"] --> MKT_Team["Marketing Team"]
    MS["Marketing Specialist - SG_Marketing_Specialist"] --> MKT_Team

    %% Operations Department
    OM["Operations Manager - SG_Operations_Manager"] --> OPS_Team["Operations Team"]
    OC["Operations Coordinator - SG_Operations_Coordinator"] --> OPS_Team

    %% Support Department
    SPM["Support Manager - SG_Support_Manager"] --> SUP_Team["Support Team"]
    SPA["Support Agent - SG_Support_Agent"] --> SUP_Team

    %% SharePoint Sites
    EX --> SP_All_Read["SP: All Sites (Read)"]
    IT_Team --> SP_IT["SP: IT Site"]
    HR_Team --> SP_HR["SP: HR Site"]
    FIN_Team --> SP_FIN["SP: Finance Site"]
    SALES_Team --> SP_SALES["SP: Sales Site"]
    MKT_Team --> SP_MKT["SP: Marketing Site"]
    OPS_Team --> SP_OPS["SP: Operations Site"]
    SUP_Team --> SP_SUP["SP: Support Site"]
