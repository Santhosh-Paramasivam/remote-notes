---
id: andrew-brown-fcc-az900
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
  - #az-900
---

# Azure Virtual Network (vNet)

- A logically isolated section of the Azure Network where you launch your Azure resources 

- [microsoft-learn](https://learn.microsoft.com/en-us/azure/virtual-network/concepts-and-best-practices)

## Services within AVN:

- **Azure DNS** - manage your own DNS domain 
- Virtual Network (vNET) - logically isolated section of Azure Network 
  - Address spaces 
  - Route tables
  - Subnets
  
- **Network Security Groups**: A virtual firewall at the subnet or NIC level 

- **ExpressRoute**: A very fast 50 Mbps-10Gbps connection between on-premise to vNet 

- **Virtual WAN**: A centralized network to route different netword connections

- **Virtual Network Gateway**: A site-to-site VPN connection between a vNet and local networks 

- **Network Interfaces**: virtual network device to allow your VMs to communicate using IP protocols

## vNet Peering

- When you connect multiple vNets to form one vNet 

- Can be:
  - **Regional**: same region
  - **Global**: different region

## Network Interfaces

- All compute needs a vNIC to form or access any network

- Can be called:
  - Network adapter
  - Network Interface Card 
  - LAN adapter 
  - physical network interace 

- NICs communicate using Internet Protocol (IP)

- NICs operate on Layer 1 (Physical Layer) and Layer 2 (Data Link Layer)

- An Azure VM can have multiple NICs

## Subnets

### What is a Subnet

- A `logical division of an address space`.

- Subnets help you define different kinds of workloads and allows you to apply virtual isolation within your network.

- When you launch an Azure resource you choose the subnet you want to launch within and an IP from that subnet is assigned to the resource 

### Associating a Route table 

- A subnet needs a Route table so it can access other resources on the network 

### Public vs Private Subnet 

- No distinct concepts like that in Azure, instead it is manually configured through route table to the **Internet Gateway**

### Network Security Gateway

- Acts as a firewall, allowing or blocking traffic based on preset security rules, using IP address, port, and protocol 

### Gateway Subnet 

> [!NOTE]
> To be looked up

### Azure DNS

- A **hosting service for DNS domains** that provides name resolution through Microsoft Azure Infrastructure

- **Public DNS Internet-facing**:
  - Pointing your domain to your website
  - Settings records to show you own the domain 
  - Records to connect your domain to your email server

- **Private DNS Internal-facing**:
  - Allows you to use your own custom domains instead of the Azure provided domains 
    - Many azure services use FQDN to identify services on the network
      - e.g. Azure Storage Accounts FQDN