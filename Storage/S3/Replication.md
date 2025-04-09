Replicate [S3](S3.md) objects between a source and destination bucket in the same or different AWS accounts.

With different account replication a [bucket policy](S3%20Security.md#Bucket%20Policies) on the destination bucket is required to allow the role in the source account to replicate.

![Pasted image 20250215205447.png](_atts/Pasted%20image%2020250215205447.png)

## Options
- All objects or subset by filters
	- Filter by prefixes or tags
- Pick [Storage Classes](Storage%20Classes.md) for the destination - default is same class #AWSCommonTest 
- Ownership - default is the source account
	- Could end up with the destination account not being able to read the bucket on their account
- Replication Time Control (RTC) - feature adds a guaranteed 15 minute replication.
	- Without it is best effort
	- Use if it is required that the buckets are in sync with as little latency as possible

## Considerations #AWSCommonTest 
- By default, replication is not retroactive.
	- When enabled objects are copied from that point forward
- Both source and destination need versioning enabled
- Batch replication can be used to replicate existing objects
- One-way replication by default - source to destination
	- There is a setting for bi-directional
- Can handle any encryption type
	- [SSE-KMS](Server-Side%20Encryption.md#SSE-KMS) requires extra configuration
- Source bucket owner needs permissions to objects
	- It is possible with replication that the source objects comes from another account, which can't be copied
- No system events replicated
	- If [Lifecycle Configs](Lifecycle%20Configs.md) changes are made to an object in source, it will not be made in destination
- Glacier objects cannot be replicated
- By default deletes are not replicated
	- Can be configured with DeleteMakerReplication

## Common uses
- Same-Region Replication (SRR)
	- Log aggregation
	- PROD and TEST Sync
	- Resilience with strict sovereignty requirements
- Cross-Region Replication (CRR)
	- Global resilience of data
	- Latency Reduction