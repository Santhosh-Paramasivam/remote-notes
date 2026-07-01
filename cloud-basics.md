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
- Availability

> [!IMPORTANT]
> Inherently and easily global and almost always more secure and reliable

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

- There is a ~75% reduction in cost when moving from on-prem to cloud 

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

## Architect Roles

### Solutions Architect

A role in a technical organization that architects a technical solution using multiple systems via researching, documentation, and experimentation

### Cloud Architect

A solutions architect that is focused solely on architecting technical solutions using cloud services

- Availability - Your ability to ensure a service remains available
- Scalability
- Elasticity
- Fault Tolerance
- Disaster recovery - Your ability to recover from a failure

Such an architect has to consider:
  - Security: How secure is this solution
  - Cost: How much is this going to cost

## Key Performance Indications

### High Availability

- The ability of your service to *remain available* by ensuring that *there is no single point of failure* and/or *ensure a certain level of performance*

- Running your workload across multiple **Availability Zones** makes sure that even if one datacenter goes down, the others still keep running

- Needs a **Load Balancer** to evenly distribute traffic

### High Scalability

- The ability to *increase your capacity* based on the increasing demand of traffic, memory and computing power

- Types of scaling:
  - Vertical scaling: Adding more resources to existing instances
  - Horizontal scaling: Increasing the number of instances

### High Elasticity

- The ability to *automatically* increase or decrease your capacity based on the current demand

- Horizontal scaling:
  - *Scaling Out*: Add more servers of the same size
  - *Scaling In*: Removing more servers of the same size

> [!NOTE]
> Vertical scaling is generally hard for traditional architecture so this is typically used with horizontal scaling only

- Utilizes specific tools specified in [azure-services](azure-services.md)
  - Azure VM Scale Sets
  - SQL Server 2016 to Microsoft Azure