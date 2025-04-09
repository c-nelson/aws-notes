## [VPC](VPC.md) Router
- Every VPC has a router
- Runs in every AZ that the VPC is in
- Every subnet has a router interface - network+1 address
- Routes traffic between subnets
- Controlled by route tables
	- Route tables are attach to 0+ subnets
	- each subnet has to have one
	- VPC has a Main route table - subnet default
		- Custom route tables can be associated with subnets
![Pasted image 20250222112342.png](_atts/Pasted%20image%2020250222112342.png)
## Internet Gateway (IGW)
How data can enter and exit a [VPC](VPC.md).

- [Regionally](../../Fundamentals/Resilience.md#Region) resilient gateway attached to a VPC
- A VPC can have 0 or 1 IGW
- A IGW can only be attached to 1 VPC
- Runs from within the [Public Zone](../../Fundamentals/Public%20vs%20Private%20Services.md#Public%20service)
- Traffic between VPC and internet or AWS Public Zone ([S3](../../Storage/S3/S3.md), SQS, SNS)
- Managed - AWS handles performance

![Pasted image 20250222113814.png](_atts/Pasted%20image%2020250222113814.png)

- Public IPs of services like [EC2](../../Compute/EC2/EC2.md) are not stored on the OS. IGW holds a mapping between the public IP and the instances private IP #AWSCommonTest 
- Packet starts with the source being the private IP, then IGW changes the source to the public IP

![Pasted image 20250222114446.png](_atts/Pasted%20image%2020250222114446.png)

## Bastian Host
- Also known as a jumpbox
- An instance in a public subnet
- Used to manage incoming management connections
- Then access internal VPC resources
- Often the only way IN to a [VPC](VPC.md)