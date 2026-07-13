---
id: azure-storage-services
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
---

- [Azure Monitoring](#azure-monitoring)
  - [Sources](#sources)
  - [Azure Monitor](#azure-monitor)
  - [3 Pillars of Observability](#3-pillars-of-observability)
    - [Metrics](#metrics)
    - [Logs](#logs)
    - [Traces](#traces)
  - [Anatomy of Azure Monitor](#anatomy-of-azure-monitor)
    - [Sources](#sources-1)
    - [Data Stores](#data-stores)
    - [Azure Monitor Functions](#azure-monitor-functions)
      - [Insights](#insights)
        - [Application Insights](#application-insights)
      - [Visualize](#visualize)
      - [Analyze](#analyze)
        - [Log Analytics](#log-analytics)
      - [Respond](#respond)
        - [Autoscale](#autoscale)
        - [Azure Alerts](#azure-alerts)
      - [Integrate](#integrate)

# Azure Monitoring 

## Sources

- [az-900 freecodecamp 8 hour course](https://www.youtube.com/watch?v=5abffC-K40c)
- [azure-monitor-docs](https://docs.azure.cn/en-us/azure-monitor/)

## Azure Monitor 

- A unified observability service for *collecting, analyzing and acting on telemetry*

- From cloud *and* on-premises environment 

- Functionality:
  - Visual dashboards
  - Smart alerts
  - Automated actions
  - Log monitoring 

- Many azure services are configured to automatically send telemetry data to Azure monitor  

## 3 Pillars of Observability

- The ability to *measure and understand how internal systems work* to understand *performance, tolerance, security and faults*

- To do this, **Metrics**, **Logs** and **Traces** need to be used

### Metrics

- A quantitative measure for the performance of cloud services over time 
- Example: If we measured CPU usage and aggregated it over a period of time, that's Average CPU usage metric

### Logs 

- A text file where each line contains event data about what happenend at a certain time
- Includes:
  - Audit logs

### Traces 

- A history of a request or function call that travels through multiple Apps / Services so we can pinpoint performance or failure 

## Anatomy of Azure Monitor 

### Sources 

- Application
- Operating system
- Azure Resources
- Azure Subscription
- Azure Tenant
- Custom sources

### Data Stores 

- Logs
- Metrics 

### Azure Monitor Functions 

#### Insights

- [list-of-all-azure-insights](https://learn.microsoft.com/en-us/azure/azure-monitor/visualize/insights-overview)

- Container 
- VMs 
- Monitoring Solutions

##### Application Insights

- Based on OpenTelemetry, providing a vendor-neutral approach

- **Application Performance Management (APM) service**

- Automatically detect performance anomalies

- Powerful analytics tools to help diagnose issues 

- Works for many languages, frameworks but only some are official (.NET, Node.js, Java, Python) hosted on cloud or on-prem

- Integrates with DevOps process 

- Can monitor and analyze telemetry from mobile apps by integrating with Visual Studio App Center 

- To use Application Insights, you need to "instrument" your app with App Insights Package, that is install that package

- There are many ways to view telemetry data:
  - Alerts
  - PowerBI
  - Visual Studio 
  - REST APIs
  - Continuous Export

- When setting up Application Insights Monitoring, Application Insights *resource* is created

- This resource could be opened to see telemetry from this app

- The resource is identified by instrumentation key (ikey)

- What all does it monitor:
  - Request rates, response times and failure rates 
  - Exceptions 
  - Page views and load performance 
  - Dependency rates, response time and failure rates 
  - AJAX calls 
  - User and session counts 
  - Performance counters 
  - Host diagnostics 
  - Diagnostic trace logs 
  - Custom events and metrics

- Where do I see my telemetry?
  - Smart detection and manual alerts 
  - Application map 
  - Profiler 
  - Usage Analysis 
  - Diagnostic search for instance data 
  - Metrics explorer for aggregated data 
  - Dashboards 
  - Live Metrics Stream
  - Analytics
  - Visual Studio
  - Snapshot Debugger 
  - Power BI

#### Visualize 

- Dashboards 
- Views 
- Power BI 
- Workbooks

#### Analyze

- Metric Analytics 

##### Log Analytics

- Edit and run log queries
- Log and metrics
- Own query langauge called KQL

- Log Analytics Workspaces:
  - An isolated container environment with specific Logs Analytics Data
  - Is a unique environment for Azure Monitor Log data

#### Respond 

##### Autoscale

- [azure-monitor-autoscale-docs](https://docs.azure.cn/en-us/azure-monitor/autoscale/autoscale-overview)

- Automatically scale when metrics reach a certain threshold

- You can scale your application based on metrics like CPU usage, queue length, and available memory.

- Rules can be metrics based or time-based

- Scales out if *any* of the rules are met, scales in only if *all* rules are met
  
- Can additionally send notifications and trigger webhooks / azure functions

##### Azure Alerts 

- Notify when issues are found with infrastructure or application 

- Allows identifying and addressing issues before the users of the system notice them

- Kinds:
  - Metric Alerts
  - Log Alerts 
  - Activity Log Alerts 

- Give notification or automatically take action

#### Integrate

- Logic apps 
- Export APIs
