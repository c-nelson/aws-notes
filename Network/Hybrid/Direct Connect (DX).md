AWS Direct Connect links your internal network to an AWS Direct Connect location over a standard Ethernet fiber-optic cable. One end of the cable is connected to your router, the other to an AWS Direct Connect router. 

With this connection, you can create _virtual interfaces_ directly to public AWS services (for example, to Amazon [S3](../../Storage/S3/S3.md)) or to Amazon [VPC](../VPC/VPC.md), bypassing internet service providers in your network path. An AWS Direct Connect location provides access to AWS in the Region with which it is associated. You can use a single connection in a public Region or AWS GovCloud (US) to access public AWS services in all other public Regions.

- Physical connection (1, 10, 100 Gbps)
- Business Premises => DX Location => AWS Region
- Provides a port allocation at a DX location
- Port Hourly Cost & Outbound Data transfer
- Takes time to provision, physical cables & no resilience
- Low & consistent latency + high speeds
- Can access AWS Private Services and AWS Public Services but not the public internet

![Pasted image 20250608212022.png](_atts/Pasted%20image%2020250608212022.png)