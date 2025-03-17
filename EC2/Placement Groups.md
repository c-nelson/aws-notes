[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)

Placement groups allow you to influence where a group of [[EC2]] instances will be hosted physically relatively. Whether instances are close together or not.
## Cluster (Performance)
- Pack instances close together
- Can't span AZs - locked after launching first instance
- Can span [[VPC]] peers, but impacts performance
- Requires a supported instance type
- Use the same type of instance (not mandatory)
- Launch instances at the same time (highly recommended)
- 10Gbps single stream performance
![[Pasted image 20250316201141.png]]
## Spread (Resilience)
- Keep instances separated
- 7 instances per AZ limit
- Provides infrastructure isolation
	- Each instance runs from a different rack
- [[Purchase Options#Dedicated Hosts|Dedicated Hosts & Instances]] not supported
![[Pasted image 20250316202010.png]]
## Partition (Topology Awareness)
- Groups of instances spread apart
- Like Spread but divided into Partitions
	- Max of 7 partitions per AZ
	- But each partition can contain multiple instances
	- Instances can be placeds in a specific partition
		- Or auto placed
	- Contain impact of failure to part of an application
![[Pasted image 20250316202611.png]]