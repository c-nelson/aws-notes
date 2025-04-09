Elastic Block Store Service
***
[AZ Resilient](../../Fundamentals/Resilience.md#AZ)
***

- Block storage - raw disk allocations
	- Can be encrypted using [KMS](../../Security/KMS/KMS.md)
	- Instances see block device
		- Instance can create a file system on top
- EBS is provisioned in one AZ
- Generally attached to \*one [EC2](../../Compute/EC2/EC2.md) instance over a storage network
	- Multi-attach - Some storage types allow for connecting to multiple instances for things like clusters
- Not to the lifecycle of an instance - persistent
	- Can be detached and reattached
- Snapshots can be made into [S3](../S3/S3.md)
	- This can make the data regionally resilient
	- Allows migrating between AZs
- Can have different physical storage types
	- Different sizes
	- Different performance
- Bill based on GB/month
	- Extras for extra performance

![Pasted image 20250301132222.png](_atts/Pasted%20image%2020250301132222.png)