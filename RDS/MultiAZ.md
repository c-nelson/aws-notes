MultiAZ is a feature of [RDS](RDS.md) which provisions a highly available instance set.

## Instance Mode
Provides a MultiAZ instance where a standby replica is kept in sync synchronously with the primary instance.The standby replica cannot be used for any performance scaling, only availability.

![Pasted image 20250330204027.png](_atts/Pasted%20image%2020250330204027.png)

- Only one standby replica
- Can't be used for reads or writes
- 60-120 seconds failover
- Same region only
- Backups taken from standby to improve performance
## Cluster Mode
A write and two reader instances are kept in sync Synchronously. The reader instances can be used for read operations, allowing for limited read scaling.

![Pasted image 20250330204850.png](_atts/Pasted%20image%2020250330204850.png)

- 1 write & 2 reader DB instances in different AZs
- Much faster hardware, Graviton + local NVME
- Fast writes to local storage => flushed to [EBS](../EBS/EBS.md)
- Application support for reading user readers, frees some resources on the writer
- Replication is via transaction logs
	- More efficient
- Failover is faster ~35s
- Writes are committed when 1 reader as confirmed