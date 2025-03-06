## Elastic Network Interfaces (ENI)

- [EC2](EC2.md) instances have at least 1 ENI
	- Primary ENI
	- Can attach one or more secondary ENIs which can be in separate [Subnets](../VPC/Subnets.md)
	- All has to be in the same [AZ](../Fundamentals/Resilience.md#AZ)
- Things that are actually attached to the ENI and not the instance
	- Mac Address
	- Primary IPv4 Private IP
	- 0 or more secondary IPs
	- 0 or 1 Public IP
		- The public IP is dynamic, changes when instances are stopped/started
		- Restart won't change IP
	- 1 elastic IP per private IP
		- If the primary ENI is assigned an elastic IP, it replaces the public IP
		- If the elastic IP is removed, the instances gets a new public IP #AWSCommonTest
	- 0 or more IPv6 addresses
	- [Security Groups](../VPC/Security%20Groups.md)
	- Source/Destination Check
- Secondary ENIs have the same capabilities
	- But can be detached and re-attached to other instances

## DNS

- Assume the instance is given a Primary **private** IP of `10.16.0.10`
	- The instance is given a DNS address of `ip-10-16-0-10.ec2.internal`
	- Only resolvable inside the [VPC](../VPC/VPC.md)
	- Can be used for internal communications
- Given the **public** IP of `3.89.7.136`
	- The DNS is `ec2-3-89-7-136.compute-1.amazonaws.com`
	- From within the VPC, this DNS will resolve to the primary private IP #AWSCommonTest
		- Communication never leaves VPC
	- Elsewhere, it resolves to the public IP

## Tips #AWSCommonTest 
- Use a secondary ENI for licensing
	- If a license is attached to a MAC address, this means you can move the licensing to different instances by attaching the ENI.
- Multiple ENIs can be used for multi-homed instances (subnets)
	- Can provide separation in allowed IPs in different subnets
	- Ex, Management & Data
	- Security Groups are attached to ENIs so:
		- If you need different rules for different IPs, use secondary ENIs
- The OS never sees the public IP
	- Never configure an network interface inside the OS with the public IP