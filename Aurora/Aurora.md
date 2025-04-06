Aurora is a AWS designed database engine officially part of [RDS](../RDS/RDS.md).

Aurora implements a number of radical design changes which offer significant performance and feature improvements over other [RDS](../RDS/RDS.md) database engines.

- Aurora architecture is very different from [RDS](../RDS/RDS.md)
- Uses [Cluster Mode](../RDS/MultiAZ.md#Cluster%20Mode)
- A single primary instance + 0 or more replicas
- No local storage - uses cluster volume
- Faster provisioning & better performance

## Storage
- Up to 15 replicas
- All SSD Based
- Storage is billed based on what is used
	- Doesn't have to be provision ahead of time
	- Up to 128 TiB
	- High water mark - billed for the most used
	- Storage which is freed up can be re-used
- Replicas can be added and removed without requiring storage provisioning
![Pasted image 20250403201337.png](_atts/Pasted%20image%2020250403201337.png)

## Endpoints
![Pasted image 20250403202019.png](_atts/Pasted%20image%2020250403202019.png)

## Cost
- No free-tier
- Aurora doesn't support micro instances
- Beyond RDS singleAZ (micro) Aurora offers better value
- Compute - hourly charge, per second, 10 minute minimum
- Storage - GB-Month consumed, IO cost per request
- 100% DB size in backups are included

## Restore, Clone, Backtrack
- Backups in Aurora work the same way as RDS [Backups](../RDS/Backups.md)
- Restores create a new cluster
- Backtrack can be used to allow in-place rewinds to a previous point in time
- Fast clones make a new db much faster than copying all the data - copy-on-write. Only record changes between source and clone
