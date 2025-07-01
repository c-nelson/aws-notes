AWS Site-to-Site VPN is a hardware VPN solution which creates a highly available [IPSEC VPN](IPSEC%20VPN.md) between an AWS VPN and external network such as on-premises traditional networks. VPNs are quick to setup vs [[Direct Connect]], don't offer the same high performance, but do encrypt data in transit.

- Full HA if you design and implement it correctly
- Quick to provision vs direct connect, under and hour
- Connect [VPC](../VPC/VPC.md)s to on-premises networks

Considerations
- Speed limitations ~ 1.25 Gbps
- Latency - inconsistent, public internet
- Cost - hourly cost, GB out cost, data cap (on premises)
- Fast to setup - hours, all software configuration
	- Dynamic VPNs need BGP support
- Can be used as a backup for [[Direct Connect]]
- Can be used with Direct Connect

### Components
- Virtual Private Gateway (VPG)
	- Logical gateway which can be the target of route tables
	- Within a VPC
- Customer Gateway (CGW)
	- Can refer to two different things
	- Logical configuration in AWS
	- Or the physical device that is targets
- VPN Connection between the VGW and CGW

## Single point of failure on-prem router
![Pasted image 20250604210732.png](_atts/Pasted%20image%2020250604210732.png)

## Making it fully HA
![Pasted image 20250604211008.png](_atts/Pasted%20image%2020250604211008.png)

## Static vs Dynamic (BGP) VPN
![Pasted image 20250604211428.png](_atts/Pasted%20image%2020250604211428.png)