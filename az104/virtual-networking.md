---
id: virtual-networking.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
---

# Virtual Networking

- [azure-virtual-networks](https://learn.microsoft.com/en-us/training/modules/configure-virtual-networks/2-plan-virtual-networks)

- Allows communication between devices on the cloud and on-prem

### VPN

- An *overlay network* that uses *virtualization and encryption* to extend a private network over a public internet

### Use Cases

- A dedicated cloud-only private network

- Securely extend datacenters capacity with a site-to-site VPN

- Enable cloud scenarios

### Subnetting

- First 4 and last IP address are reserved by Azure

### Private and Public IPs

- Private IPs: 
  - ExpressRoute
  - Virtual networks
  - VPN Gateway
  - On-premise networks

- Public IPs:
  - Internet, public-facing Azure services

- Use static IP address when:
  - DNS name resolution, where a change in the IP address requires updating host records.
  - IP address-based security models that require apps or services to have a static IP address.
  - TLS/SSL certificates linked to an IP address.
  - Firewall rules that allow or deny traffic by using IP address ranges.
  - Role-based virtual machines such as Domain Controllers and DNS servers.