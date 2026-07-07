---
id: cloud-global-infrastructure.md
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

- [Azure Compute Services](#azure-compute-services)
  - [Common Compute Services](#common-compute-services)
    - [Azure Virtual machines](#azure-virtual-machines)
    - [Azure Container Instances](#azure-container-instances)
    - [Azure Kubernetes Service (AKS)](#azure-kubernetes-service-aks)
    - [Azure Service Fabric](#azure-service-fabric)
    - [Azure Functions](#azure-functions)
    - [Azure Batch](#azure-batch)
  - [Azure VMs](#azure-vms)
    - [Virtual Machine Scale Sets](#virtual-machine-scale-sets)
      - [App Insights](#app-insights)
      - [Scale-In Policy](#scale-in-policy)
        - [Default](#default)
        - [Newest VM](#newest-vm)
        - [Oldest VM](#oldest-vm)
      - [Update Policy](#update-policy)
      - [Health Monitoring](#health-monitoring)
      - [Azure Diagnostic Extension](#azure-diagnostic-extension)
    - [Azure Virtual Desktop](#azure-virtual-desktop)
      - [Load Balancer](#load-balancer)
    - [Compute Fleet](#compute-fleet)

# Azure Compute Services

## Common Compute Services

### Azure Virtual machines

- [microsoft-learn](https://learn.microsoft.com/en-us/azure/virtual-machines/overview)

- A virtual machine requires other resources that are billed separately such as:
  - vNET, vNIC, IPs, OS Disk and other disks


### Azure Container Instances

- **Docker as a Service**

- Run containerized apps on Azure without provisioning servers or VMs

### Azure Kubernetes Service (AKS)

- **Kubernetes as a Service**

- Easy to deploy, manage and scale containerized applications

- Uses open-source K8

### Azure Service Fabric

- Microsoft's homegrown solution (from before Kubernetes became the norm) to microservice and container orchestration, an alternative to Kubernetes

- Special support for *stateful applications*, guest services/applications

- It doesn't need containers for orchestration

- It can be deployed on other clouds as well. Its less of a specific azure service and more of an open source way of writing microservices

- Service Fabric provides its own programming models (Reliable Services and Reliable Actors) and is more opinionated about application architecture.

### Azure Functions

- Event-driven, stateless compute (functions) run code without provisioning or managing servers
- You only pay for compute time consumed

### Azure Batch

- For high-performance computing, and batch processing for large volumes of files

- Automatically setups up VMs and schedules independent (or dependent) jobs to complete the entire workload

- Use Spot VMs to save money

- Scientific workloads, big data pipelines, multi-node AI training, 3D

## Azure VMs

- Which components and how many are utilized depends on the VM image
- Billed at an hourly rate
- A single VM has an availability of 99.9%
- Two instances deployed in an Availability Set will give you 99.95% availability
- You can attach Managed Disk to your Azure VMs

- When creating a VM, a few other resources are created:
  - **Network Security Group**
  - **vNIC**
  - **vNet**
  - **IP Addresses**

- A wide variety of OS image optimized for the Azure Runtime

- You can also bring your own Linux!

### Virtual Machine Scale Sets

- A set of load balanced virtual machines, the number of virtual machine instances can *automatically increase* or decrease in response to demand

- Create rules for scaling out or in using host metrics (percentage CPU, Network In...)

- Health checks and set a repair policy to replace unhealthy instances

#### App Insights

- Installs a small instrumentation package in your application that monitors the app and sends telemetry to Azure
- When you want App Metrics

#### Scale-In Policy 

- Determines which VM is to be removed to decrease the capacity of the Scale Set

##### Default

- Delete the VM with the highest instance ID 

- Balanced acrosss AZs and FDs

##### Newest VM

- Delete the newest created VM

- Balanced across Availability Zones (AZs)

##### Oldest VM

- Delete the oldest created VM

- Balanced across Availability Zones (AZs)

#### Update Policy

- Automatic 
- Manual 
- Rolling (?)

#### Health Monitoring

- Determines if VMs in the Scale Set is healthy or not 

- 2 modes of health monitoring:
  - Application health extension: Pings an HTTP endpoint and expect a 200 status
  - Load Balancer Probe: Needs a load balancer which is recommended for VMSS, based on TCP, UDP, or HTTP requests

- There is also an automatic repair policy for deleting "unhealgthy" and replacing them with healthy instances

#### Azure Diagnostic Extension

- An agent that runs inside a VM instance

- It monitors and saves more performance metrics to Azure storage

### Azure Virtual Desktop 

- Desktop and app virtualization service

- Enable *secure and productive remote work* on any device

- *Reduce the costs of licensing and infrastructure*, only pay for what you use in terms of Microsoft 365 and Windows usage

- *Protect against outages* to stay productive, by leveraging built-in Azure Site Recovery and Azure Backup technologies

- *Simplify IT Management*, no need to manage power networking and desktop infrastructure 

- *Keep application and user data secure*, easily apply the right access controls to users and devices

#### Load Balancer

- **Application Gateway**: HTTP/HTTPS web traffic load balancer with URL-based routing, SSL termination, session persistence, and web application firewall

- **Azure Load Balancer**: supports all TCP/UDP network traffic, port-forwarding, and outbound flows

- **Probe checks**: Robust health checks

### Compute Fleet

- For high-performance and distributed computing environments

