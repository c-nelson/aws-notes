***
[AZ resiliency](../../Fundamentals/Resilience.md#AZ)
***
A subnet is a subnetwork of a VPC within a particular AZ. Services run on subnets inside a [VPC](VPC.md).

Subnets add structure to a [Custom VPCs](Custom%20VPCs.md).

- Subnet start off as private
	- Configurations to make public
- A subnet is within a single AZ
	- To make our service more resilient we put services into different subnets
- Allocated an IPv4 CIDR subset of the [VPC CIDR](VPC.md#VPC%20CIDR)
	- Cannot overlap with other subnets
	- Optional IPv6 CIDR
- Subnets can by default communicate with other subnets within the VPC

## Reserved IPs per Subnet
- 5 IPs within every subnet are reserved
	- Given the range 10.16.16.0/20 (10.16.16.0...10.16.31.255)
	- Network address is the first - 10.16.16.0
	- VPC Router is Network+1 - 10.16.16.1
	- Reserved DNS is Network+2 - 10.16.16.2
	- Reserved for Future is Network+3 - 10.16.16.3
	- Broadcast Address is last address - 10.16.31.255
		- Even though broadcast is not supported within a VPC

## IP Allocation
- IP allocation controlled by the VPC [DHCP Option Set](Custom%20VPCs.md#DHCP%20Option%20Set)
- Configurations within the subnet level:
	- Auto Assign Public IPv4
		- Controls if resources are allocated a public IP address in addition to their private subnet address
	- Auto Assign IPv6