## History
- 3 Types of load balances available within AWS
- Split between v1 (avoid) and v2
- Classic Load Balancer (CLB) v1
	- Introduced in 2009
	- Not really layer 7, lacking features, 1 SSL per CLB
- Application Load Balancer (ALB) v2
	- HTTP/S/ Web socket
- Network Load Balancer (NLB) v2
	- TCP, TLS, UDP
	- Pick for applications which don't use HTTP
- V2 are faster, cheaper and support target groups and rules

## Architecture
![Pasted image 20250410212411.png](_atts/Pasted%20image%2020250410212411.png)
![Pasted image 20250410212906.png](_atts/Pasted%20image%2020250410212906.png)
- #AWSCommonTest
- ELB is a [DNS A Record](../R53/DNS%20Record%20Types.md#A%20and%20AAAA) pointing at 1+ Nodes per AZ
- Nodes (in one subnet per AZ) can scale
- Internet-facing means nodes have public IPs
- Internal is private only IPs
- [EC2](../../Compute/EC2/EC2.md) doesn't need to be public to work with a LB
- Listener Configuration controls what the LB does
- Require 8+ free IPs per subnet, and /27 subnet to allow scaling
## CROSS-ZONE LB
![Pasted image 20250410213430.png](_atts/Pasted%20image%2020250410213430.png)