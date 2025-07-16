With the DeletionPolicy attribute you can preserve or (in some cases) backup a resource when its stack is deleted. You specify a DeletionPolicy attribute for each resource that you want to control. If a resource has no DeletionPolicy attribute, [CloudFormation](CloudFormation.md) deletes the resource by default.

- If you delete a logical resource from a template, the default behavior is to delete the physical resource
- With deletion policy, you can define on each resource
- Delete (Default)
- Retain
- Snapshot (if supported)
	- [EBS](../../Storage/EBS/EBS.md) volumes, ElastiCache, Neptune, [RDS](../../Database/RDS/RDS.md), Redshift
- ONLY APPLIES TO DELETE, NOT REPLACE

![Pasted image 20250712204235.png](_atts/Pasted%20image%2020250712204235.png)