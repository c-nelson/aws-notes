Virtual Private Cloud

Used to create private networks within AWS so services can communicate.

Can always be used to connected to on premises servers to create a hybrid cloud.

A VPC is within 1 account and 1 region.

Two types:
- Default VPC
	- Max of 1 per region
	- Preconfigured
- Custom VPC
	- Can have many per region
	- Require configuration
	- By default completely cutoff and private

## VPC CIDR
**VPC CIDR** is the range of IPs within a VPC.

## Default VPC
The default VPC is always 172.31.0.0/16.

Preconfigured with Internet Gateway, Security Group, and NACL.

Subnets assign public IPv4 addresses.

The default VPC spans a complete [[Global Infrastructure#AWS Regions|region]] but contains a subnet for each [[Global Infrastructure#Availability Zones|AZ]].

![[Pasted image 20250121214553.png]]