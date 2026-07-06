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

- You *cannot by DNS names in Azure DNS*, Azure DNS simply manages the domain

### Virtual Network Gateways

#### Virtual Private Networks 

- "A VPN extends a private network across a public network and enables users to send and receive data across shared or public networks as if their computing devices were directly connected to the network"

#### What is a Virtual Network Gateway 

- The software VPN device for an Azure virtual network

- When you deploy a Virtual Network Gateway, it will deploy two or more specialized VMs in a specific subnet you need to create called a "gateway subnet"
- These deployed VMs contain routing tables and run specific gateway services

- *Gateway Type*:
  - VPN
  - **ExpressRoute**
  
### Azure ExpressRoute 

- Creates a *private connection* from on-premises and Azure datacenters

- ExpressRoute connections don't go over the public internet:
  - More reliability
  - Faster speeds 
  - Consistent latencies
  - Higher security

- Connectivity can be from (on-premises):
  - Any-to-any (IP VPN network)
  - point-to-point Ethernet network 
  - virtual cross-connection 
  - through a connectivity provider at a colocation facility

- Could be used for:
  - **Microsoft (Public) Peering**: Office 365
  - **Azure Private Peering**

- **ExpressRoute Direct**: Greater bandwidth connections, from 50 Mbps to 10 Gbps

### Private Links 

- Azure Private Links allows you to *establish private and secure connections* between Azure resources so traffic remains within the Azure Network

- Most Azure services are automatically configured to be able to use Private Link

- **Azure Private Endpoint** is an endpoint within a vNet that allows traffic to a Private Link

- **Private Link Services** allows you to use Private Link for a connection to a vNet or a vNet Subnet. You need an **Azure Standard Internal Load Balancer**, and associate it with the Link Service
