---
id: cloud-global-infrastructure.md
aliases: []
tags:
  - #cloud
  - #azure
  - #cloud-components
---

# Cloud Global Infrastructure

## Regions and Geographies

### Availability Zone

- A *close cluster of data centers* that share power, networking and other infrastructure, that is atleast several kilometers away from another Availability Zone

- This allows *automatic failover* mechanisms: If one availability zone encounters some error that causes it to go down, the workload is run on a different AZ

### Region

- A grouping of *all data centers within a region*, which has low latency network connections

- Not all regions have AZ, ones that don't support the same failover mechanisms

- Azure has *58 Regions* available across *140 countries*, the largest of any CSP

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