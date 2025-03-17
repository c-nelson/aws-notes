- A [R53](R53.md) Hosted Zone is a DNS DB for a domain
- [Globally resilient](../Fundamentals/Resilience.md#Global)
- Created automatically with domain registration via R53
- Host [DNS Records](DNS%20Record%20Types.md) (eg A, AAAA, MX, NS, TXT)
## Public
A public hosted zone is a container that holds information about how you want to route traffic on the internet for a specific domain which is accessible from the public internet.

- DNS Database (zone file) hosted by [R53](R53.md) (Public Name Servers)
- Accessible from public internet & [VPC](../VPC/VPC.md)
- When Public Hosted Zone created:
	- Hosted on 4 R53 Name Servers (NS) specific for the zone
	- Use NS Records to point at these NS (connect to global DNS)
- Resource Records (RR) created within the Hosted Zone
- Externally registered domains can point at a R53 Public Zone
![Pasted image 20250316210640.png](_atts/Pasted%20image%2020250316210640.png)

## Private
A _private hosted zone_ is a container that holds information about how you want [R53](R53.md) to respond to DNS queries for a domain and its subdomains within one or more [VPC](../VPC/VPC.md)s.

- Mostly the same as Public Hosted zone but private
- Associated with [VPC](../VPC/VPC.md)s
	- Only accessible in those VPCs
- Using different accounts is supported via [CLI](../CLI.md)/API
- Split-view (overlapping public & private) for public and internal use with the same zone name
![Pasted image 20250316211350.png](_atts/Pasted%20image%2020250316211350.png)

#### Split View Hosted Zones
Use the same domain name for public and internal access but with a different set of records available to each.
![Pasted image 20250316211544.png](_atts/Pasted%20image%2020250316211544.png)
