---
id: azure-entra-id.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
---

# Microsoft Entra Id

## Microsoft Entra Product Family



## Introduction

> [!NOTE]
> By default, when you create a new Azure subscription by using a Microsoft account, the subscription automatically includes a new Microsoft Entra tenant named Default Directory.

- Active Directory is also called "Active Directory Domain Services (AD DS)"

### Tenant

- A **Tenant** is one isolated instance of Microsoft Entra ID specific to one company or organization

- It is a cluster of identities, groups and applications that can be managed collectively. Its sort of a container for Entra ID Objects

- An organization can have more than one tenant

- Each subscription is linked to exactly one tenant at any given time

- This allows one to grant permission for certain users from Microsoft Entra ID to access resources from the Azure Subscription

- One tenant -> Multiple subscriptions (Same identities can be used to manage access to resources)

- One subscription -> Only one tenant at any given time

### Tiers

- Free
- Basic
- Premium
  - Premium 1 (P1)
  - Premium 2 (P2)
- Entra Suite

### AD DS vs. Entra ID

- AD DS is a directory service whereas Entra ID is an identity service 

- AD DS has OUs and GPOs for managing multiple AD objects, whereas Entra ID has a flat service

- AD DS can be queried via LDAP whereas Entra ID is accessed via HTTP/HTTPs

### Entra ID - P1 vs. P2 

#### P1

- Full MFA: Across hybrid environments
- Microsoft Identity Management: Hybrid identities
- Password reset with write-back (automatically and immediately synced with on-premises)
- Enterprise SLA of 99.9% (Applies to Basic, P1, P2)
- Conditional access

#### P2

- Microsoft Entra ID Protection
- Microsoft Entra Privileged Identity Management

### Microsoft Entra Domain Services

- A managed cloud instance of AD DS
- Has GPOs and OUs
- Supports LDAP, Keberos protocols

- Reduces the effort it takes to manage AD DS
  - No need to ensure replication of domain controllers
  - No need to monitor, manage and troubleshoot domain controllers

- Alternatives to
  - A site-to-site VPN between on-prem and Azure IaaS
  - Replica domain controllers from your local AD DS as virtual machines (VMs) in Azure

## Practical

> [!NOTE]
> There are dedicated User settings in Microsoft Entra ID for controlling the permissions of *default* users

### Initial configuration of Microsoft Entra ID

- [init-config-entra-id](https://learn.microsoft.com/en-us/training/modules/implement-initial-configuration-of-azure-active-directory/)

> [!NOTE]
> P1, P2, Office 365 come with *Company branding*

### Adminstrative Unit 

- A collection of Microsoft Entra ID objects that can be assigned admins 

- Allows the segmentation of an Entra tenant into multiple groups, by departments for examples, allowing granular scope for the administrator privileges

- The Entra version of Organizational Units (OUs)

- Roles available for AUs:
  - Authentication administrator
  - Helpdesk administrator
  - License administrator
  - Password administrator
  - User administrator

### Guest users vs. Member users

- Member users are internal users who are members of the Entra Tenant, and are part of the company itself

- Guest users belong to other organizations, have an email or identity that is not part of the Entra Tenant, but are still users under Entra Tenant

- By default, guest users have fewer permissions than member users

- But guest users can be assigned any permission that member users can, including Global Administrator