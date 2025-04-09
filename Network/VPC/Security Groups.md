Security Groups (SGs) are another security feature of [VPC](VPC.md)s, only unlike [NACLs](NACLs.md) they are attached to resources, not VPC [subnets](Subnets.md).

SGs offer a few advantages vs [NACLs](NACLs.md) in that they can recognize resources and filter based on them, they can reference other SGs and also themselves.

But, SGs are not capable of explicitly blocking traffic so often require assistance from [NACLs](NACLs.md).

- SGs are [stateful](Stateful%20vs%20Stateless%20Firewalls.md#Stateful%20Firewalls)
- If an inbound is allowed, then the outbound response is automatically allowed
- No explicit deny, only allow or implicit deny
	- Can't block specific bad actors
- Supports referencing IP/CIDR and logical resources
	- Including other security groups and itself
- Attached to Elastic Network Interfaces (ENIs), not instances #AWSCommonTest
	- Even if it looks that way on the UI

![Pasted image 20250222214956.png](_atts/Pasted%20image%2020250222214956.png)

## Logical References
In the example below, instead of referencing IPs or CIDR ranges, the APP server Security Group can directly references the WEB security group to allow connections. This means that the APP will allow connections to any resource that is using the WEB security group.

Has the benefit of scaling, applying the security group to many resources.

![Pasted image 20250222215614.png](_atts/Pasted%20image%2020250222215614.png)

### Self References
If multiple instances are within a security group, then, for example, the rule can references itself to allow all traffic between instances.

A benefit is that IP changes are automatically handled and intra app communication is set up.

![Pasted image 20250222215837.png](_atts/Pasted%20image%2020250222215837.png)
