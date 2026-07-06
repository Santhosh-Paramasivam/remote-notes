---
id: andrew-brown-fcc-az900
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
  - #az-900
---

# Azure Container Instances

- Allows you to launch containers in a fully managed PaaS environment

- Containers are more efficient that VMs:
    - Provisioned *within seconds*, whereas VMs take several minutes

    - Containers are *billed per second*, whereas VMs are billed per hour (greater savings)

    - Containers have *granular and custom sizing of vCPUs, Memory and GPUs* where VM sizes are predetermined

- *Persist storage with Azure Files*

- Launch containers from **Azure Container Registry**, **Docker Hub**, or some private container registry

- Can be accessed via a *Fully Qualified Domain Name (FQDN)* eg. customlabel.azureregion.azurecontainer.io 

## Container Groups

- Collection of containers that get scheduled on the same host machine 

- These containers share:
  - Lifecycle
  - Resources
  - Local Network
  - Storage Volumes

- Analogous to a *Kubernetes Pod*

- Multi-container groups only support Linux

- Two ways to deploy it:
  - **Resource Manager Template (ARM Template)**: When you need to deploy additional Azure service resources
  - **YAML file**: When your deployment includes only container instances

## Container Restart Policies

- Defines what a container should do *when their process in completed*

- Always (default): Suitable for long-running tasks 
- On failure: Only when failure 
- Never: Run one time only. Suited for one-off

## Container Environment Variables

- Just environment variables

> [!IMPORTANT]
> This can only be done through the CLI
- Through CLI, use `--secure-environment-variables` to provide an env keys to be encrypted

## Container Persistent Storage

- Azure Containers are *stateless* by default

- To persist state, mount an external volume such as:
  - Azure Files
  - Secret Volume 
  - Empty directory
  - Cloud git repo

> [!IMPORTANT]
> All file mounting can only be done through the Azure CLI or Powershell

## Follow-along

- Type in the **Public IP** of the service after giving it time to start
