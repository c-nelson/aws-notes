- Direct attached storage - Storage on the EC2 [Host](../EC2/Architecture.md#Hosts)
	- Call Instance Store
	- Prone to failure
- Network attached Storage - volumes delivered over Elastic Block Store, [EBS](EBS.md)
- Ephemeral Storage - temporary
- Persistent Storage - permanent past lifetime of the instance

## Types
- Block storage - Volume presented to OS as a collection of blocks, no structure provided.
	- Mountable
	- Bootable
	- Physical or logical
	- EBS
- File storage - presented as a file has, has structure
	- Mountable
	- Not bootable
- Object Storage - collection of objects
	- Flat
	- Not mountable
	- Not bootable
	- [S3](../S3/S3.md)

## Performance
Block Size * IOPS = Throughput
- IO Block Size
- IOPS 
	- IO per second
- Throughput
	- Amount of data per second, mb/s