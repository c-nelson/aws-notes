- In transit
	- SSL/TLS (in transit) is available for [RDS](RDS.md)
		- Can be mandatory
- At rest
	- [RDS](RDS.md) supports [EBS Encryption](../../Storage/EBS/Encryption.md) via [KMS](../../Security/KMS/KMS.md)
	- Handled by the [RDS](RDS.md) Host/[EBS](../../Storage/EBS/EBS.md)
		- To the database engine, it is just writing unencrypted data.
	- AWS or Customer Managed CMK generates data keys.
	- Data keys used for encryption operations
	- Storage, Logs, Snapshots & replicas are encrypted
	- Encryption can't be reversed

	- RDS MSSQL and RDS Oracle support Transparent Data Encryption (TDE)
		- DB engine handles encryption
	- RDS Oracle supports integration with CloudHSM
		- Much stronger key controls

![Pasted image 20250403194950.png](_atts/Pasted%20image%2020250403194950.png)

## [IAM](../../Security/Accounts/IAM.md) Authentication
![Pasted image 20250403195232.png](_atts/Pasted%20image%2020250403195232.png)