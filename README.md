# Awesome-User-Lifecycle-Management-Directory-Sync

# Awesome User Lifecycle Management & Directory Sync

> A curated list of top User Lifecycle Management and Directory Sync platforms — both SaaS/Hosted commercial solutions and open-source alternatives for automating joiner-mover-leaver (JML) workflows, identity synchronization, and access provisioning across directories and applications.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Okta Lifecycle Management](#okta-lifecycle-management)
  - [Microsoft Entra Lifecycle Workflows](#microsoft-entra-lifecycle-workflows)
  - [Google Workspace Directory](#google-workspace-directory)
  - [JumpCloud](#jumpcloud)
  - [OneLogin](#onelogin)
  - [Ping Identity (PingIDM)](#ping-identity-pingidm)
  - [CyberArk Identity](#cyberark-identity)
  - [Auth0](#auth0)
  - [AWS IAM Identity Center](#aws-iam-identity-center)
  - [SailPoint Identity Security Cloud](#sailpoint-identity-security-cloud)
  - [Druva inSync User Management](#druva-insync-user-management)
- [Open-Source Software](#-open-source-software)
  - [WSO2 Identity Server](#wso2-identity-server)
  - [BoxyHQ Jackson](#boxyhq-jackson)
  - [Keycloak](#keycloak)
  - [Evolveum midPoint](#evolveum-midpoint)
  - [Apache Syncope](#apache-syncope)
  - [Hanzo IAM](#hanzo-iam)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted User Lifecycle Management and Directory Sync platforms. These are not open-source but are included as reference points for feature comparison.

### Okta Lifecycle Management
**Type:** Enterprise identity lifecycle automation  
Okta Lifecycle Management automates access decisions across joiner-mover-leaver (JML) events using dynamic RBAC and ABAC. It connects to multiple identity sources — HR systems, Active Directory, and LDAP — through Okta Universal Directory, which consolidates identity data across subsidiaries and post-merger environments [citation:5]. Lifecycle Management is tightly integrated with Okta Identity Governance, applying policies and provisioning directly within the identity flow rather than through a separate IGA layer [citation:5].  
**Best for:** Organizations with complex, multi-source identity estates needing unified lifecycle automation and governance.

### Microsoft Entra Lifecycle Workflows
**Type:** Identity governance workflows within Entra ID  
Microsoft Entra Lifecycle Workflows automate JML processes with predefined templates for onboarding and offboarding, custom task scheduling, and execution condition scoping [citation:6]. Workflows can send emails, assign licenses, disable accounts, and integrate with Azure Logic Apps for advanced scenarios. Requires Entra ID Governance or Entra Suite licensing [citation:6]. Deeply integrated with HR-driven provisioning and the broader Microsoft identity ecosystem.  
**Best for:** Microsoft-centric organizations wanting JML automation native to Entra ID and Microsoft 365.

### Google Workspace Directory
**Type:** Directory user management via Admin API  
Google Workspace Directory provides programmatic user lifecycle management through the Admin SDK Directory API, including user creation, updates, renaming, suspension, and admin role assignment [citation:7]. Renaming a user changes the primary email and can take up to 10 minutes to propagate; the old username is retained as an alias for mail continuity [citation:7]. Relationship fields support manager-employee and other org structures. Suited for Google-first organizations.  
**Best for:** Google Workspace organizations needing API-driven directory management.

### JumpCloud
**Type:** Cloud directory with cross-OS device management  
JumpCloud combines cloud directory, SSO, MFA, LDAP/RADIUS, and device management in a single console. The Enterprise Portal (preview) allows admins to manage users across multiple sub-organizations, filter by state, and perform actions like suspend or force password change [citation:8]. Users can be created manually, imported, or synced from external sources.  
**Best for:** SMBs and mid-market organizations replacing on-premises Active Directory with a cloud-native directory.

### OneLogin
**Type:** IAM with directory sync and manual user management  
OneLogin syncs users from third-party directories (AD, LDAP, Workday, Google) but also supports manually adding users directly to its directory, with OneLogin serving as the primary user directory . Each user gets a unique OneLoginID, and bulk CSV import is available. Recommended practice: create at least one admin account manually to prevent lockout if the external directory fails .  
**Best for:** Organizations wanting flexible directory sourcing with a straightforward admin experience.

### Ping Identity (PingIDM)
**Type:** Identity management with BPMN workflow engine  
PingIDM 7.5 brings together multiple identity sources for policy- and workflow-based management, with modules for synchronization, provisioning, self-service, and identity lifecycle [citation:10]. The Workflow module uses BPMN 2.0 and the Flowable process engine for visually organized provisioning, approvals, escalations, and sunrise/sunset processes [citation:10]. OpenICF connectors extend to external systems.  
**Best for:** Enterprises needing complex, standards-based workflow orchestration for identity lifecycle events.

### CyberArk Identity
**Type:** Identity administration with external directory integration  
CyberArk Identity supports interactive users imported from on-prem authentication (AD, LDAP, RADIUS) or cloud sources (Entra ID, Google Workspace), plus federation via external IdPs [citation:11]. Service users for API/automation have least-privilege access and no MFA policies. Roles determine which services and permissions users can access after provisioning.  
**Best for:** Organizations needing privileged and general user lifecycle management with strong security controls.

### Auth0
**Type:** Developer-focused user management  
Auth0 provides user profiles stored in a hosted cloud database, sourced from configured IdPs. The Dashboard and Management API support creating users, modifying profiles, importing/exporting, and linking accounts [citation:12]. Organizations support B2B multi-tenancy with branded login flows, and RBAC assigns permissions via roles rather than individual user grants [citation:12].  
**Best for:** Developer teams building applications needing flexible user management and B2B organization support.

### AWS IAM Identity Center
**Type:** AWS workforce identity and access  
IAM Identity Center connects to external IdPs, Active Directory, or its own directory as identity sources [citation:13]. Users and groups are assigned access to AWS accounts via permission sets and to applications (AWS-managed or customer-managed). The AWS access portal provides a unified sign-in destination. Multi-Region setups require external IdP or Identity Center directory (not AD).  
**Best for:** Organizations needing centralized workforce access to AWS accounts and applications.

### SailPoint Identity Security Cloud
**Type:** Enterprise identity security and governance  
SailPoint's cloud platform covers machine identity discovery, data access security, AI-powered application onboarding, and SAP IAG integration [citation:14]. Machine Account Migration moves non-employee machine accounts under proper governance. Automated Data Ownership Election identifies and assigns data owners based on usage patterns.  
**Best for:** Enterprises needing comprehensive identity security spanning human and machine identities with strong governance.

### Druva inSync User Management
**Type:** Backup service user directory integration  
Druva inSync integrates with AD/LDAP to import users rather than creating them individually, with configurable mappings, sync frequency, and priority [citation:4]. Supports AD, non-AD, AD/LDAP, Entra ID, and SCIM as deployment types. This is a backup-platform-specific user management layer rather than a general-purpose IdP.  
**Best for:** Druva inSync customers needing directory-integrated user provisioning for backup services.

---

## 🟩 Open-Source Software

Self-hosted, community-driven User Lifecycle Management and Directory Sync tools. All listed projects offer source code you can deploy on your own infrastructure.

### WSO2 Identity Server
**Stack:** Java | **License:** Apache-2.0  
A Digital Public Good-recognized open-source IAM solution supporting OAuth2, OIDC, SAML, SCIM 2.0, and FIDO2 [citation:1]. Features include adaptive MFA, RBAC, SSO, identity federation, social login, and user management [citation:1]. Used in 93 countries across finance, public administration, healthcare, and education [citation:1]. SCIM 2.0 enables automated user provisioning and deprovisioning from external directories.  
**Best for:** Organizations wanting a comprehensive, standards-based IAM platform with SCIM provisioning and a proven track record in regulated sectors.

### BoxyHQ Jackson
**Stack:** Node.js / Next.js / PostgreSQL | **License:** Open Source (per project)  
SAML Jackson provides **Directory Sync** for automating user provisioning and deprovisioning, creating a single source of truth for user identity data . It can be deployed as a separate service with an admin portal for managing SSO and Directory Sync connections, or embedded as an NPM library . Docker Compose deployment is supported.  
**Best for:** SaaS applications needing to add enterprise directory sync (SCIM) and SSO capabilities without building the infrastructure from scratch.

### Keycloak
**Stack:** Java | **License:** Apache-2.0  
The most widely deployed open-source IAM platform, providing SSO, identity brokering, user federation (LDAP/AD), and SCIM provisioning. Widely used as the identity backbone in open-source stacks. Supports OIDC, SAML, and OAuth 2.0. While not a dedicated lifecycle automation tool, its user federation and SCIM capabilities enable directory synchronization and provisioning workflows.  
**Best for:** Organizations wanting a proven, battle-tested IAM foundation with directory federation and SCIM support.

### Evolveum midPoint
**Stack:** Java | **License:** Open Source (subscription model)  
A comprehensive open-source Identity Governance and Administration (IGA) platform with automated provisioning/deprovisioning, policy-based approvals, segregation of duties controls, access certification campaigns, and role mining. Subscription-based with **no license fees** — pay only for support. The governance depth (approvals, certifications, SoD) exceeds what most open-source IAM tools provide.  
**Best for:** Organizations needing full IGA with lifecycle automation and governance controls without per-identity licensing costs.

### Apache Syncope
**Stack:** Java | **License:** Apache-2.0  
An open-source IAM and IGA platform for managing digital identities, provisioning, authentication, and access control. Supports user/group/role management, automated provisioning workflows, RBAC, delegated administration, LDAP/AD/database connectors, SAML 2.0, OIDC, and SCIM. Includes audit logging and compliance reporting.  
**Best for:** Organizations seeking a standards-based, Apache-governed IGA platform with strong connector support.

### Hanzo IAM
**Stack:** Go | **License:** Apache-2.0  
An AI-first IAM and MCP gateway/auth server with web UI. Supports OAuth 2.1, OIDC, SAML, CAS, LDAP, **SCIM provisioning** for automated user lifecycle management, WebAuthn, TOTP, MFA, and 40+ social login providers [citation:15]. Features RBAC, multi-tenancy, API-first design, and Docker deployment.  
**Best for:** Teams wanting a modern, Go-based IAM with SCIM provisioning and AI/MCP integration.

---

## 📊 Comparison at a Glance

| Software | License | Type | SCIM/Directory Sync | JML Automation | Self-Hosted | Best For |
|----------|---------|------|---------------------|----------------|-------------|----------|
| **Okta** | Proprietary | Enterprise IAM | ✅ | ✅ | ❌ | Multi-source lifecycle automation |
| **Entra Lifecycle** | Proprietary | IGA workflows | ✅ | ✅ Templates | ❌ | Microsoft-centric JML |
| **Google Workspace** | Proprietary | Directory API | Limited | API-driven | ❌ | Google-first directory management |
| **JumpCloud** | Proprietary | Cloud directory | ✅ | ✅ | ❌ | SMB cloud directory |
| **OneLogin** | Proprietary | IAM | ✅ | ✅ | ❌ | Flexible directory sourcing |
| **PingIDM** | Proprietary | Identity mgmt | ✅ | ✅ BPMN workflows | ❌ | Complex workflow orchestration |
| **CyberArk** | Proprietary | Identity admin | ✅ | ✅ | ❌ | Privileged + general lifecycle |
| **Auth0** | Proprietary | Developer IAM | Limited | Via API | ❌ | B2B app user management |
| **AWS IAM Identity Center** | Proprietary | AWS access | ✅ | ✅ | ❌ | AWS workforce access |
| **SailPoint** | Proprietary | Identity security | ✅ | ✅ | ❌ | Human + machine governance |
| **WSO2 IS** | Apache-2.0 | IAM | ✅ SCIM 2.0 | Via SCIM | ✅ | Standards-based IAM |
| **Jackson** | Open Source | Directory sync | ✅ SCIM | ✅ | ✅ | SaaS directory sync add-on |
| **Keycloak** | Apache-2.0 | IAM foundation | ✅ SCIM | Via federation | ✅ | Proven IAM foundation |
| **midPoint** | Open Source | IGA | ✅ | ✅ Policy-driven | ✅ | Full governance without license fees |
| **Apache Syncope** | Apache-2.0 | IAM + IGA | ✅ SCIM | ✅ Workflows | ✅ | Standards-based IGA |
| **Hanzo IAM** | Apache-2.0 | AI-first IAM | ✅ SCIM | ✅ | ✅ | Modern Go IAM + MCP |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source User Lifecycle Management or Directory Sync tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem spans **full IAM/IGA suites** (WSO2, midPoint, Syncope) and **focused directory sync components** (Jackson), which solve different layers of the lifecycle problem.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
