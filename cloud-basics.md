---
id: cloud-basics
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

# Cloud Basics

## Reason

- Instead of making capital investments, renting real estate, buying hardware, hiring people and *taking all the risk yourself*, you can outsource the risk to the cloud provider

## Evolution

- Dedicated Server:
    - A dedicated physical machine for running some application. Very expensive, high maintenance and *was and remains high security*

- Virtual Private Server:
    - A dedicated (still single tenant) single physical machine for running multiple applications, through virtualized computer resources. "...virtualized into sub-machines"
    - *Resource pooling*: Resources are shared as per need of applications leading to more efficient usage

- Shared Hosting:
    - One machine shared by hundreds of businesses. Multi-tenant. *Relies on most tenants under utilizing resources*
    - Incredibly cheap, limited functionality, poor isolation (instead of containers)

- Cloud Hosting:
    - Multiple physical machines that act as one system, through virtualization
    - The system is abstracted into multiple *cloud services*
    - Flexible, Scalable, Secure, Cost-Effective, High Configurability
  
## Common Cloud Services

### IaaS

- Compute
- Storage
- Networking
- Databases

## Benefits of Cloud Services

- Cost-effective
- Global: Launch workloads anywhere in the world, just choose a region
- Secure: Cloud provider takes care of *physical security*
- Reliable: data backup, disaster recovery, data replication, and fault tolerance
- Scalable
- Elastic: Automatic scaling

## Azure's Deployment Models

- Public cloud:
  - Everything built on cloud provider
  - Also known as: Cloud-Native
  
- Private cloud:
  - Everything built on company's datacenters
  - Also known as On-Premise
  - The cloud could be OpenStack

- Hybrid cloud:
  - Both
  - Through ExpressRoute

- Cross cloud:
  - Using multiple cloud service providers
  - Example: Using Azure Arc to "extend the control plane from Amazon AKS to GCP Kubernetes Engine"
  
## Total Cost of Ownership (TCO)

- There is a ~75% reduction in cost when moving to cloud from on-prem

## CAPEX vs. OPEX

- Capital Expenditure:
  - Spending money upfront on physical infrastructure, *deducting that expense from your tax bill over time*
  - Computers, storage, network, backup and archive, disaster recovery costs
  - You have to guess the actual cost of the investment, and there is no knowing if there will be a return on investment

- Operational Expenditure:
  - Leasing software and customizing features
  - Training employees in cloud services
  - Paying for cloud support
  - Billing based on cloud metrics e.g.
    - compute usage
    - storage usage
  - Try a product *without investing in equipment*
