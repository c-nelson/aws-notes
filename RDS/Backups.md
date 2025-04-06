[RDS](RDS.md) is capable of performing Manual Snapshots and Automatic backups

![Pasted image 20250330210405.png](_atts/Pasted%20image%2020250330210405.png)
## Manual Snapshots
Much like EBS [03\_Resources/aws/EBS/Snapshots](../EBS/Snapshots.md).

Manual snapshots are performed manually and live past the termination of an RDS instance

Snapshots can be restored but create a new RDS instance.
## Automatic Backups
Automatic backups can be taken of an RDS instance with a 0 (Disabled) to 35 Day retention.

Automatic backups also use [S3](../S3/S3.md) for storing transaction logs every 5 minutes - allowing for point in time recovery.

## Restores
- Creates a new [RDS](RDS.md) instance - new address
	- Update applications
- Snapshots = single point in time
- Automated = any 5 minute point in time
- Backup is restored and transaction logs are 'replayed' to bring DB to desired point in time
- Restores are slow

