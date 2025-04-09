An _instance store_ provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. Instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content, or for data that is replicated across a fleet of instances, such as a load-balanced pool of web servers.

An instance store consists of one or more instance store volumes exposed as block devices. The size of an instance store as well as the number of devices available varies by instance type.

The virtual devices for instance store volumes are `ephemeral[0-23]`. Instance types that support one instance store volume have `ephemeral0`. Instance types that support two instance store volumes have `ephemeral0` and `ephemeral1`, and so on.

- Differ from [EBS](../../Storage/EBS/EBS.md) in that they are local to the server
	- Physically connected to one [EC2](EC2.md)
	- Highest storage performance
- Temporary storage
	- When changing hosts, data is lost
- Block Storage Devices
- Included in the instance price
- Attached at launch #AWSCommonTest
	- Can't be attached after launch
	- Use or lose

![Pasted image 20250301192917.png](_atts/Pasted%20image%2020250301192917.png)
