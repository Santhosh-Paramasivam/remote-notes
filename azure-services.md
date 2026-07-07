---
id: azure-services
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
---

- [Azure Services](#azure-services)
  - [Azure Monitor](#azure-monitor)
  - [Azure Entra](#azure-entra)
    - [Azure Entra ID](#azure-entra-id)
      - [Azure Entra External ID](#azure-entra-external-id)
  - [Azure Front Door](#azure-front-door)
  - [Azure Databases](#azure-databases)
    - [CosmosDB](#cosmosdb)
    - [Azure SQL Database](#azure-sql-database)
    - [SQL Server Managed Database](#sql-server-managed-database)
  - [Azure API Management](#azure-api-management)
    - [Azure API Gateway](#azure-api-gateway)
  - [Application Gateway Ingress Controller (AGIC)](#application-gateway-ingress-controller-agic)
  - [Elastic Services](#elastic-services)
    - [Azure VM Scale Sets](#azure-vm-scale-sets)
    - [SQL Server Stretch Database](#sql-server-stretch-database)
  - [Fault Tolerant Services](#fault-tolerant-services)
    - [Azure Traffic Manager](#azure-traffic-manager)

# Azure Services

## Azure Monitor

- Logs:
  - What happened
  - Metrics: How often / fast
  - Alerts: What needs attention?
- Brings in information from Grafana, Prometheus
- Health, performance and reliability
- Metrics, logs, traces, and events, including audit logs from Entra ID
- Contains Azure Application Insights, which provides performance monitoring

## Azure Entra

- Manages identity, security, encryption and other security concerns

### Azure Entra ID

#### Azure Entra External ID

- For allowing non-microsoft accounts and external parties to utilize an application
- For client-facing applications

- Provides you with components to easily get the users' `idTokenClaims`, that is a JWT token with claims

## Azure Front Door

- Fancy CDN
- Security against DDoS protection, although it is advisable to utilize Azure DDoS Protection and Web Application Firewall
- Connects to Azure Monitor
- Integrated WAF

## Azure Databases

- How consistent?

### CosmosDB

- Offers a flexible schema, NoSQL
- Geo-replicated distributed caching
- indexing and search

### Azure SQL Database

- Fully managed SQL Database
- SQL Server

### SQL Server Managed Database

- Typically used when migrating 

## Azure API Management

- Dashboard for viewing and managing APIs
- Securely expose services hosted on and outside Azure as APIs
- Enable API discovery

### Azure API Gateway 

- Verifies credentials
- Routes to the appropriate APIs

## Application Gateway Ingress Controller (AGIC)

- Built in L7 Load Balancer
- Identifies and exposes AKS deployed services
- WAF

## Elastic Services

### Azure VM Scale Sets

- Automatically increase or decrease in response to demand or a defined schedule

### SQL Server Stretch Database

- Dynamically stretch warm and cold transactional data from Microsoft SQL Server 2016 to Microsoft Azure

## Fault Tolerant Services

### Azure Traffic Manager

- DNS-based traffic balancer

- To fail-over from a failing primary system to a stand-by secondary system