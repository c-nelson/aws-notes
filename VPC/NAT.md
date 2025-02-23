Network Address Translation

A process of giving a process outgoing only access to the internet.

A set of processing which remaps source and destination IPs.

[IGW](Routing%20&%20Internet%20Gateway.md#Internet%20Gateway%20(IGW)) implements a form of static NAT when it maps public and private IPs.

**IP masquerading** - hiding CIDR Blocks behind one IP, many private IPs to one single public IP
- Used because public IPv4 addresses running out

NAT gives a private [CIDR](VPC.md#VPC%20CIDR) range outgoing internet access
 - Because many private IPs use a single public IP, incoming access doesn't work

## NAT Gateway
[AZ resilient](../Fundamentals/Resilience.md#AZ) - for every AZ you use you need at least one Route Table & NATGW

AWS NAT-as-a-service Product available within a [VPC](VPC.md).

- Traditionally you could use an [EC2](../EC2/EC2.md) instance set up to be a NAT service before NAT Gateway was created
- Uses Elastic IPs (Static IPv4 Public)
- AWS managed service, scales to 45 Gbps, cost for duration & data volume #AWSCommonTest
- Not required and don't work with IPv6
	- IPv6 doesn't need the concept of public/private IPs

Can be set up within a public [subnet](Subnets.md) to receive and route traffic out from a private subnet. Then route that traffic to the [IGW](Routing%20&%20Internet%20Gateway.md#Internet%20Gateway%20(IGW)).

It is needed to allow private instances access to the public internet.

![Pasted image 20250222222509.png](_atts/Pasted%20image%2020250222222509.png)

#### Example Setup
![Pasted image 20250222223428.png](_atts/Pasted%20image%2020250222223428.png)

### NATGW vs NAT Instance

| Attribute       | NAT gateway                                                                                                                                                                              | NAT instance                                                                                                         |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Availability    | Highly available. NAT gateways in each Availability Zone are implemented with redundancy.<br><br>Create a NAT gateway in each Availability Zone to ensure zone-independent architecture. | Use a script to manage failover between instances.                                                                   |
| Bandwidth       | Can scale up to 45 Gbps.                                                                                                                                                                 | Depends on the bandwidth of the instance type.                                                                       |
| Maintenance     | Managed by AWS. You do not need to perform any maintenance.                                                                                                                              | Managed by you, for example, by installing software updates or operating system patches on the instance.             |
| Performance     | Software is optimized for handling NAT traffic.                                                                                                                                          | A generic Amazon Linux AMI that's configured to perform NAT.                                                         |
| Cost            | Charged depending on the number of NAT gateways you use, duration of usage, and amount o lata that you send through the NAT gateways                                                     | Charged depending on the number of NAT instances that you use, duration of usage, and instance type and size.        |
| Type and size   | Uniform offering; you don't need to decide on the type or size.                                                                                                                          | Choose a suitable instance type and size, according to your predicted workload.                                      |
| Security groups | Cannot be associated with a NAT gateway. You can associate security groups with your resources behind the NAT gateway to control inbound and outbound traffic.                           | Associate with your NAT instance and the resources behind your NAT instance to control inbound and outbound traffic. |
| Network ACLs    | Use a network ACL to control the traffic to and from the subnet in which your NAT gateway resides.                                                                                       | Use a network ACL to control the traffic to and from the subnet in which your NAT instance resides.                  |
| Flow logs       | Use flow logs to capture the traffic.                                                                                                                                                    | Use flow logs to capture the traffic.                                                                                |
| Port forwarding | Not supported.                                                                                                                                                                           | Manually customize the configuration to support port forwarding.                                                     |
| Bastion servers | Not supported.                                                                                                                                                                           | Use as a bastion server.                                                                                             |