DataSync is a product which can orchestrate the movement of large scale data from on-premises NAS/SAN into AWS or vice-versa.

- Migrations, Data Processing Transfers, Archival/Cost effective storage or DR/BC
- Designed to work at huge scale
- Keeps metadata (eg permissions/timestamps)
- Features
	- Built in data validation
	- Scalable - 10 Gbps per agent (~100TB per day)
	- Bandwidth limiters
	- Incremental and scheduled transfers
	- Compression and encryption
	- Automatic recovery from transit errors
	- Integrations - [S3](../../Storage/S3/S3.md), [EFS](../../Storage/EFS/EFS.md), FSx
	- Pay as you use, per GB cost

![Pasted image 20250619133710.png](_atts/Pasted%20image%2020250619133710.png)

- Components
	- Task - a job within DataSync, defines what is being synced, how quickly, FROM where TO where
	- Agent - Software used to read or write to on-premises data stores using NFS or SMB
	- Location - every task has two locations FROM and TO. eg NFS, SMB, EFS, FSx, S3