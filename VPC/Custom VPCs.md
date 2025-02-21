***
[Regional](../Fundamentals/Resilience.md#Region) Service - operates in all AZs in the region.
***

Example:
![Pasted image 20250217192933.png](_atts/Pasted%20image%2020250217192933.png)

- Isolated networks
- Nothing IN or OUT without explicit configuration

Custom [VPC](VPC.md)s allow:
- Flexible config - simple or multi-tier
- Hybrid networking - other cloud & on-premises
- Config option - Default or Dedicated Tenancy
	- Default - can choose whether each resource runs on different hardware
	- Dedicated - all services run on separate dedicated hardware. No option after setup.
- IPv4 Private CIDR Blocks & Public IPs
- 1 Primary Private IPv4 CIDR Block mandatory
	- Min /28 (16 IP)
	- Max /16 (65,536 IP)
	- Optional secondary IPv4 blocks
- Optional single assigned IPv6 /56 CIDR block

DNS in a VPC
- Provided by [R53](../R53/R53.md)
- DNS IP address is VPC Base + 2
	- Ex. 10.0.0.0 -> 10.0.0.2
- `enableDnsHostnames` - whether instances with public IPs in a VPC are given DNS names
- `enableDnsSupport` - enables DNS resolution in VPC

## DHCP Option Set
Configuration applied to a VPC. There's one per VPC. It controls how IPs are assigned automatically. Flows down to the [Subnets](Subnets.md).