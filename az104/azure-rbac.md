---
id: azure-rbac.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
---

# Azure RBAC

- [azure-rbac](https://learn.microsoft.com/en-us/training/modules/secure-azure-resources-with-rbac/1-introduction)

## Types of roles

### Microsoft Entra roles

- Global admin
- Application admin
- Application developer
- Billing admin

### Azure roles

- Owner
- Contributor
- Reader
- User Access Admin

### Classic subscription admin roles

- Service admins
- Co-admins

## Working of Azure RBAC

![azuread-and-azure-roles](../images/2-azuread-and-azure-roles.png)

![rbac-overview](../images/2-rbac-overview.png)

### Role Assigments

- Has three elements:
  - Security principal
  - Role definition
  - Scope

- **Security Principle (Who):** The user, user group or **service principal** (an application) who is to be granted permission

- **Role definition (What):** A role or role definition is a collection of permissions.

- **Scope (Where):** This is where the role permissions applies. It can be a management group, subscription, resource group or resource

> A role assignment is the process of binding a role to a security principal at a particular scope for the purpose of granting access. To grant access, you'll create a role assignment. To revoke access, you'll remove a role assignment.
