Network Access Control Lists

An optional layer of security for your [VPC](VPC.md) that acts as a firewall for controlling traffic in and out of one or more [subnets](Subnets.md). 

You might set up network ACLs with rules similar to your security groups in order to add an additional layer of security to your VPC.

- NACLs are [stateless firewalls](Stateful%20vs%20Stateless%20Firewalls.md#Stateless%20Firewalls).
- Only impacts data crossing subnets
- Only deal with IPs/CIDR, ports and protocols, they do not reference resources
	- Cannot be assigned to resources, only subnets
- Generally, used together with [Security Groups](Security%20Groups.md) to add explicit DENYs
- Each subnet can have one NACL
- A NACL can be associated with many subnets

Filters traffic crossing the subnet inbound and outbound. Connections within a subnet are not impacted.

NACLs have a set of Inbound and Outbound rules to configure. They allow both explicit ALLOWs and DENYs. Rules are processed in order, lowest rule number to first, once a match occurs processing stops. * is an implicit deny if nothing else matches.

![Pasted image 20250222212214.png](_atts/Pasted%20image%2020250222212214.png)

![Pasted image 20250222213030.png](_atts/Pasted%20image%2020250222213030.png)

## Default NACL
A VPC is created with a default NACL which allows all traffic.

## Custom NACL
Can be created for a specific [VPC](VPC.md) and are initially not associated with any [Subnets](Subnets.md). The default configuration of a custom NACL is to deny all traffic.