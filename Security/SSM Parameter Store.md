The SSM Parameter store is a service which is part of Systems Manager which allows the storage and retrieval of parameters - string, stringlist or secure string.

The service supports encryption which integrates with [KMS](KMS/KMS.md), versioning and can be secured using [IAM](Accounts/IAM.md).

The service integrates natively with many AWS services - and can be accessed using the CLI/APIs from anywhere with access to the AWS Public Space Endpoints.

- Storage for configuration & secrets
- String, stringlist, secure string
	- License codes, Database string,s full configs, and passwords
- Hierarchies & versioning
	- organize in trees like
		- myDBpassword
		- /wordpress/DBUser
		- /wordpress/DBpassword
- Plaintext and ciphertext
- Access from apps, [Lambda](../Compute/Lambda/Lambda.md) or [EC2](../Compute/EC2/EC2.md)
- Changes can create events

Commands:
```bash
aws ssm get-parameters --names /wordpress/DBUser

aws ssm get-parameters-by-path --path /wordpress

aws ssm get-parameters-by-path --path /wordpress --with-decryption
```



