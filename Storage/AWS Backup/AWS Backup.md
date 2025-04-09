Use AWS Backup to centralize and automate data protection across AWS services and hybrid workloads. AWS Backup offers a cost-effective, fully managed, policy-based service that further simplifies data protection at scale. AWS Backup also helps you support your regulatory compliance or business policies for data protection. Together with AWS Organizations, you can use AWS Backup to centrally deploy data protection policies to configure, manage, and govern your backup activity across your company’s AWS accounts and resources.

[https://aws.amazon.com/backup-restore/services/](https://aws.amazon.com/backup-restore/services)

- Fully managed data-protection (backup/restore) service
- Consolidate backup management into one place
	- across accounts
	- across regions
- Supports wide range of AWS Products

![Pasted image 20250408202415.png](_atts/Pasted%20image%2020250408202415.png)

## Terms
- Backup Plans
	- frequency
	- window
	- lifecycle
	- vault
	- region copy
- Resources - what is being backed up
- Values - backup destination (container)
	- assign [KMS](../../Security/KMS/KMS.md) key for encryption
	- Read/Write by default
- Vault Lock
	- Write Once, Read Many (WORM)
	- 72 hour cool off, then even AWS can't delete
	- Compliance situations
- On-Demand - manual backups
- PITR - Point in time recovery