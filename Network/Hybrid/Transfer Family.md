- Managed file transfer service
- Supports transferring TO/FROM [S3](../../Storage/S3/S3.md) and [EFS](../../Storage/EFS/EFS.md)
- Provides managed "servers" which support protocols
	- FTP
	- FTPS - FTP with TLS
	- SFTP - SSH transfer
	- AS2 - Applicability Statement 2 - structured business to business data
- Identities - service managed, [Directory Service](Directory%20Service.md), Custom ([Lambda](../../Compute/Serverless/Lambda.md), [API Gateway](../../Compute/Serverless/API%20Gateway.md))
- Managed File Transfer Workflows (MFTW) - serverless file workflow engine
- Multi-AZ
- Provision Server per hour cost + data transferred cost
- Use if you need to access S3/EFS but with existing protocols

![Pasted image 20250619141531.png](_atts/Pasted%20image%2020250619141531.png)

## Endpoint Types
![Pasted image 20250619142038.png](_atts/Pasted%20image%2020250619142038.png)