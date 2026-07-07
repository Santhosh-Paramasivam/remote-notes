---
id: cloud-global-infrastructure.md
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

- [Cloud Global Infrastructure](#cloud-global-infrastructure)
  - [Regions and Geographies](#regions-and-geographies)
    - [Availability Zone](#availability-zone)
    - [Region](#region)
    - [Geography](#geography)
    - [Paired Regions](#paired-regions)
    - [Regions' Service Capabilities](#regions-service-capabilities)
    - [Service Availability](#service-availability)
    - [Special Region](#special-region)
  - [Availability zones](#availability-zones)
    - [AZ Supported Regions](#az-supported-regions)
    - [Fault and Update domains](#fault-and-update-domains)

# Cloud Global Infrastructure

## Regions and Geographies

### Availability Zone

- A *close cluster of data centers* that share power, networking and other infrastructure, that is at least several kilometers away from another Availability Zone
- This allows *automatic failover* mechanisms: If one availability zone encounters some error that causes it to go down, the workload is run on a different AZ

### Region

- A grouping of *all data centers within a region*, which has low latency network connections
- Not all regions have AZ, ones that don't support the same failover mechanisms
- Azure has *58 regions* available across *140 countries*, the largest global footprint of any CSP

### Geography

- A discreet market of two or more regions that *preserves data residency and compliance boundaries*
- Includes:

  - United States
  - Azure Government (US)
  - Canada
  - Mexico
  - Brazil

### Paired Regions

- [microsoft-learn](https://learn.microsoft.com/en-us/azure/reliability/regions-paired?tabs=all)
- When a region is logically paired with another region "300 miles away"
- Only one region is updated at a time *to ensure no outages*
- A lot of regions are not paired, and instead use availability zones as their primary means of redundancy
- Some azure services internally utilize paired regions to provide redundancy, such as the GRS (Azure geo-redundant storage)

### Regions' Service Capabilities

- *Not all Azure cloud services* are available in every region
- Two types of regions by service capabilities:

  1. **Recommended region**: A region that provides the *broadest range of capabilities* and is designed to support availability zones now or in the future
  2. **Alternate (other) region**: A region *not designed to support AZs*, labelled as *other in Azure Portal*

### Service Availability

- **General availability (GA)**: the service is considered ready to used publicly by everyone
- Azure Cloud services are grouped into 3 categories, this determines when the cloud service become available:
  1. **Foundational**: When GA, immediately or in 12 months in Recommended and Alternate Regions
  2. **Mainstream**: When GA, immediately or in 12 months in Recommended Regions may become available in Alternate Regions based on customer demand
  3. **Specialized**: Available in Recommended or Alternate Region based on customer demand

### Special Region

- Specialized regions to meet *compliance or legal reasons*

- Including:
  - US DoD Central
  - US Gov Virginia
  - US Gov Iowa
  - *Three Azure Government secret locations undisclosed*

## Availability zones

- Common practice to run workloads in at least 3 AZs to *ensure services remain available* in case one or two datacenters fail.

- Datacenters in a region are physically isolated (so different buildings), but still close enough to allow hyper low-latency connections (< 2 milliseconds)

### AZ Supported Regions

- Recommended regions are supposed to have at least 3 AZs, but not always possible

### Fault and Update domains

- An availability zone is a combination of a **Fault Domain** and an **Update Domain**

- Fault domain: Its a group of virtual machines that share a common power source and network switch. A logical grouping of hardware that's non-redundant. 

- Update domain: A group of virtual machines that are updated at once
  
- For availability, *workload must be distributed across fault and update domains*, could also mean *across AZs*. This is accomplished through **Availability Sets**

- You get to choose the number of fault and update domains for resources