# Microsoft 365 Business Environment

> Solution package: [business and technical documentation](docs/solution-package.md)

Portfolio project documenting the design and administration of a small-business Microsoft 365 tenant. The environment covers identity, messaging, endpoint management, collaboration, security, compliance, and automation through repeatable, engineer-style documentation.

## Why I built it

This project demonstrates four Cloud Engineer capabilities:

1. **Cloud identity and access** — Entra ID users, groups, roles, domain verification, and identity workflows.
2. **Enterprise collaboration services** — Exchange Online, SharePoint, OneDrive, and Teams working together for a business.
3. **Endpoint, security, and compliance operations** — Intune enrollment and policies plus Purview, retention, DLP, audit, and eDiscovery concepts.
4. **Automation and operational documentation** — PowerShell, Microsoft Graph, CLI workflows, screenshots, and troubleshooting notes.

## Architecture

The tenant is organized around Entra ID as the identity layer, with Microsoft 365 workloads connected through shared users, groups, roles, policies, and automation.

The source diagram is maintained in [architecture/m365-tenant-structure.md](architecture/m365-tenant-structure.md).

## Repository layout

```text
domain-setup/         Domain verification, DNS, SPF, DKIM, DMARC, mail-flow testing
entra-ID/             Users, groups, roles, departments, and RBAC concepts
exchange-online/      Mailboxes, shared mailboxes, groups, transport, and message trace
intune-setup/         Enrollment, compliance policies, apps, profiles, and testing
security-compliance/  Purview labels, retention, DLP, audit, and eDiscovery
sharepoint-teams/     Sites, libraries, Teams, governance, and collaboration structure
automation/           PowerShell, Graph API, bulk operations, and administration workflows
architecture/         Tenant relationship diagram
screenshots/          Visual evidence organized by capability
```

## What I implemented

### 1. Built the identity foundation

I documented domain verification, DNS records, users, groups, departments, roles, and RBAC decisions. This demonstrates how identity becomes the control plane for the rest of the tenant.

Evidence: [Entra ID documentation](entra-ID/README.md) and [domain setup](domain-setup/README.md).

### 2. Configured business collaboration services

I modeled mailboxes, shared mailboxes, distribution groups, mail-flow rules, SharePoint sites, document libraries, Teams structures, and governance boundaries.

Evidence: [Exchange Online](exchange-online/README.md) and [SharePoint–Teams](sharepoint-teams/README.md).

### 3. Added endpoint and security controls

I documented Intune enrollment, compliance policies, configuration profiles, app deployment, sensitivity labels, retention, DLP, audit, and eDiscovery workflows.

Evidence: [Intune](intune-setup/README.md) and [Security & Compliance](security-compliance/README.md).

### 4. Practiced administration through automation

I organized PowerShell, Graph API, and CLI workflows for bulk identity operations, Exchange administration, Intune tasks, and policy-oriented operations. The goal was to make cloud administration repeatable instead of relying only on portal clicks.

Evidence: [Automation](automation/README.md).

## Visual evidence

The repository includes screenshots showing configuration and validation evidence, including domain and DNS verification, Entra ID users and roles, Exchange mail flow, Intune policies, Purview controls, SharePoint and Teams administration, and automation workflows. Screenshots are grouped by capability in the [`screenshots/`](screenshots/) directory.

## Skills demonstrated

- Microsoft 365 administration
- Microsoft Entra ID and RBAC fundamentals
- Exchange Online and mail-flow administration
- Intune endpoint management
- SharePoint and Teams governance
- Purview security and compliance concepts
- PowerShell and Microsoft Graph automation
- Architecture documentation and troubleshooting

## Lessons learned

- Identity is the foundation that connects Microsoft 365 services.
- Cloud administration requires both configuration skills and governance thinking.
- Automation reduces repetitive work and makes administrative tasks easier to validate.
- Screenshots, diagrams, and decision-focused documentation make a homelab project easier to evaluate.

## Security and scope

This is a learning homelab and portfolio project. Screenshots should be redacted before publication, and no passwords, access tokens, tenant secrets, or personal data should be committed. Advanced features described as conceptual are labeled in their individual documentation rather than presented as production claims.
