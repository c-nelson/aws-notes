The AWS Transit gateway (TGW) is a network gateway which can be used to significantly simplify networking between [VPC](../VPC/VPC.md)'s, VPN and [Direct Connect (DX)](Direct%20Connect%20(DX).md).

It can be used to peer [VPC](../VPC/VPC.md)s in the same account, different account, same or different region and supports transitive routing between networks.

- Network transit hub to connect VPCs to on premises networks
- Peer with different regions, same or cross account
	- Share between accounts using AWS RAM
- Significantly reduces network complexity
- Supports transitive routing
- Single network object - HA and Scalable
- Can be used to create global network
- Create attachments to other network types
	- [VPC](../VPC/VPC.md), [Site-to-Site VPN](Site-to-Site%20VPN.md), [Direct Connect (DX)](Direct%20Connect%20(DX).md)

## Without Transit Gateway
We need [VPN routing](../VPC/Routing%20&%20Internet%20Gateway.md) between every VPC and on-prem network.

See below, it would take at least 8 tunnels to connect all networks or 12 with HA.
![Pasted image 20250610202024.png](_atts/Pasted%20image%2020250610202024.png)

## With Transit Gateway
Each Customer Gateway only needs to connect to the one Transit Gateway

Can create attachments to VPCs. Configured with a subnet in each AZ.

![Pasted image 20250610202538.png](_atts/Pasted%20image%2020250610202538.png)


