---
id: cloud-global-infrastructure.md
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

- [Azure App Service](#azure-app-service)
  - [Managed Infrastructure](#managed-infrastructure)
  - [Simplified Integrations](#simplified-integrations)
  - [Azure App Service Plans](#azure-app-service-plans)
  - [Runtime Environment](#runtime-environment)
  - [Deployment Slots](#deployment-slots)
  - [App Service Environment (ASE)](#app-service-environment-ase)
  - [Azure App Service Plan](#azure-app-service-plan)
    - [Shared Tiers](#shared-tiers)
    - [Dedicated Tiers](#dedicated-tiers)

# Azure App Service

- PaaS
- HTTP-based service 

## Managed Infrastructure

- Security patches for OS and languages
- Load Balancing
- Autoscaling
- Automated manager

## Simplified Integrations 

- Azure DevOps
- Github Integration 
- Docker Hub Integration 
- Package Management
- Simple setup for staging environments 
- Custom Domains 
- Attaching TLS/SSL Certificates

## Azure App Service Plans

- **Shared Tier** - Free, Shared (Linux not supported)
- **Dedicated Tier** - Basic, Standard, Premium, PremiumV2, PremiumV3
- **Isolated Tier** 

## Runtime Environment

- All the software that is running to ensure that your program is running, i.e., programming languages, any packages or frameworks

- The runtime environment can be selected, and is deployed as a container within which your application will run

> [!NOTE]
> Azure and other CSPs have the tendency to retire older versions of Runtimes
> It's always good to move to later versions

- You could use a **Custom Container** after putting it in Azure Container Registry

## Deployment Slots 

- Allow multiple environments of a web application associated to a different hostname

- Helps creating dev, qa, staging and prod environments

- You can also *swap* environments. This could be used to perform a **Blue/Green** deploy

## App Service Environment (ASE)

- A *dedicated, isolated environment* for running App Service apps *securely and at scale*

- High-requests per second (RPS) workloads

- ASE comes with its own pricing tier (Isolated Tier)

- ASEs can be used to configure security architecture

- Web application firewall and other upstream devices can be used to gate access to ASE apps

- ASEs can be deployed into specific AZs

- Two deployment types:
  - External ASE: ASE is exposed directly to the internet
  - ILB ASE: ASE is exposed to an Internal Load Balancer**

## Azure App Service Plan

### Shared Tiers

- Free tier:
  - 1 GB of disk space 
  - up to 10 apps on a single shared instance 
  - No SLA for availability 
  - Each app has a compute quota of 60 minutes a day 

- Shared tier: 
  - up to 100 apps on a single shared instance 
  - No SLA for availability 
  - Each app has a compute quota of 240 minutes per day
  - Doesn't support Linux

### Dedicated Tiers

- Basic 
- Standard 
- Premium

> [!IMPORTANT]
> Fill out these tiers' info