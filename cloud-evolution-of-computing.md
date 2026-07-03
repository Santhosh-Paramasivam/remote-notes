---
id: cloud-evolution-of-computing.md
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

# Evolution of Computing

## Dedicated

- A physical server wholly utilized by a single customer

- You have to guess your capacity, you'll *overpay for an underutilized server*

- Upgrading beyond your capacity will be slow and expensive

- You are limited by your OS

> [!IMPORTANT]
- No isolation between executing applications; multiple apps can result in conflicts in resource sharing

> [!IMPORTANT]
- You have a guarantee of **security, privacy and full utility of underlying resources*

> [!NOTE]
> Only if managed well, does a dedicated machine have any guarantee of security, and the same goes for cloud although cloud has better default inexpensive security

## Virtual Machines

- You can run multiple virtual machines on one machine
- Hypervisor -> Allows virtualization
- A physical server shared by multiple customers
- You pay for a fraction of the server

- You will still overpay for an underutilized Virtual Machine
- You are still limited by your guest operating system
- Good isolation between tenants, still terrible isolation between workloads of a single tenant

## Containers

- Containers allow physical or virtual resources to be *divided for use by multiple apps*
- Efficient resource utilization, lower cost
- Each app executes in its own environment
- Each app emulates a different OS that's suitable for the app, whilst still sharing the underlying OS, which makes them efficient
- Very good isolation between apps

## Functions (FaaS)

- Yet another subdivision to improve cost effectiveness
- *Serverless compute*: All of server management is abstracted away from the use
- User simply uploads code and data
- Very very cost effective
- **Cold Starts** are a side-effect of this setup, as the program needs to be loaded in before it runs