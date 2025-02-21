Deciding the [VPC](VPC.md) IP range ([CIDR](VPC.md#VPC%20CIDR)) is one of the first things to do. It is hard to change later.

[https://aws.amazon.com/answers/networking/aws-single-vpc-design/](https://aws.amazon.com/answers/networking/aws-single-vpc-design/)

Considerations:
- What size should the [VPC](VPC.md) be, IP range
	- Influences how many services
- Other networks that will need to be used
	- Mindful of other VPC ranges, on-premises, etc
	- Avoid IP ranges already in use
- Predict what services will be like in the future
- VPC Structure - tiers (dev & prod) & resiliency of services
- VPC minimum /28 (16 IP), maximum /16 (65536 IPs)
- Avoid common ranges
- Reserve 2+ networks per region being used per account

![Pasted image 20250217174811.png](_atts/Pasted%20image%2020250217174811.png)
Sizing:
- How many subnets will you need?
- How many total IPS? How many per subnet?

Services use subnets, VPC services run from within subnets not directly from the VPC.

A subnet is located in 1 availability zone, so the number of subnets depends on how many Availability Zones & regions are going to be used.

Example using /16
![Pasted image 20250217175744.png](_atts/Pasted%20image%2020250217175744.png)