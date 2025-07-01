AWS Secrets manager is a product which can manage secrets within AWS. There is some overlap between it and the [SSM Parameter Store](SSM%20Parameter%20Store.md) - but Secrets manager is specialized for secrets.

#### Secrets Manager vs Parameter Store
- Shares functionality
- Secrets Manager
	- Designed for secrets (passwords, API Keys)
	- Usable via Console, CLI, API, or SDK's
	- Supports automatic rotation - using [Lambda](../Compute/Serverless/Lambda.md)
	- Directly integrates with some products like [RDS](../Database/RDS/RDS.md)

![Pasted image 20250621220807.png](_atts/Pasted%20image%2020250621220807.png)