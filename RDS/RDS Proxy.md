RDS Proxy is a fully managed, highly available database proxy for [RDS](RDS.md) that makes applications more scalable, more resilient to database failures, and more secure.

Facts:
- Fully Managed DB Proxy for [RDS](RDS.md)/[Aurora](../Aurora/Aurora.md)
	- Auto scaling highly available
- Provides connection pooling - reduces DB load
- Only accessible from a VPC
- Accessed via Proxy Endpoint
- Can enforce SSL/TLS
- Can reduce failover time by over 60%
- Abstracts db failure away from your app

Why do you need RDS Proxy:
- Opening and Closing DB Connections consume resources
- With serverless every lambda opens and closes
- Handling DB failure within application adds risk
- DB Proxies help, managing them is not trivial

With RDS Proxy:
Applications => DB proxy (connection pooling) => Database
![Pasted image 20250405205020.png](_atts/Pasted%20image%2020250405205020.png)

When to use:
- Too many connections errors...
- DB Instances using T2/T3 (i.e smaller/burst) instances
- AWS Lambda, time saved/connection reuse & IAM Auth
- Long running connections (SAAS apps) - low latency
- Where resilience to database failure is a priority...
	- RDS proxy can reduce the time for failover
	- and make it transparent to the application
