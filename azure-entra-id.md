---
id: 7-7-2026.md
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
---

# Azure Entra ID

## Name Change!

Azure AD Free -> Microsoft Entra ID Free 
Azure AD Premium PO -> Microsoft Entra ID P1
Azure AD Premium P2 -> Microsoft Entra ID P2 
Azure AD External Identities -> Microsoft Entra External ID

## Azure Active Directory (AD)

- Cloud-based identity and access management services 

- Manage users, Sign-Ins and access to AD-related resources 

- **Microsoft Entra ID Free:** MFA, SSO, Basic Security and Usage Reports and User Management 

- **Office 365 Apps:** Company Branding, SLA, Two-Sync between On-premise and cloud

- **Premium 1:** Hybrid architecture, Advanced Group Access, Conditional Access 

- **Premium 2:** Identity protection, Identity governance

### Use Cases 

- Azure AD can authorize and authenticate:
  - To your on-premise AD: Azure AD Connect
  - To your web-application: Azure AD App Registrations
  - Allow users to login with their IpD eg. Facebook or Google: External Identities
  - To Office 365 or Azure Microsoft

### Active Directory vs. Azure Active Directory (Entra ID)

- Introduced for the *Windows 2000*

- To give organizations the ability to manage multiple on-premises infrastructure components and systems using a single identity per user

- Azure AD provides Identity as a Service (IDaaS) 

- Active Directory -> On-premise version 

- Azure AD -> The cloud version

### Active Directory Terminology

#### Domain 

- A domain is an area of a network organized by a single authentication database 

- An **Active Directory domain** is a logical grouping of AD objects on a network

#### Domain Controller (DC)

- A domain controller is a server that authenticates user identities and authorizes their access to resources

- Common to have multiple DCs

#### Domain Computer 

- A computer that is registered with a central authentication database. A domain computer would be an AD Object 

#### AD Object

- An AD Object is the basic element of Active Directory such as:
  - Users
  - Groups
  - Printers
  - Computers
  - Shared folders

#### Group Policy Object (GPO)

- A virtual collection of policy settings. 

- Controls what AD Objects have access to

#### Organization Units (OU)

- A subdivision within an Active Directory into which you can place users, groups, computers, and other organizational units 

#### 