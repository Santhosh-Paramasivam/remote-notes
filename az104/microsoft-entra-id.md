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