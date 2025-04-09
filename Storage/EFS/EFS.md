The Elastic File System (EFS) is an AWS managed implementation of NFS which allows for the creation of shared 'filesystems' which can be mounted within multi [EC2](../../Compute/EC2/EC2.md) instances.

- Implementation of NFSv4
- EFS Filesystems can be mounted in Linux
- Shared between many [EC2](../../Compute/EC2/EC2.md) instances
- File system vs [EBS](../EBS/EBS.md) block storage
- Private service via mount targets inside a [VPC](../../Network/VPC/VPC.md)
- Can be accessed from on-premises - VPN or DX
- For Linux only
- General Purpose and MAX I/O Performance Modes
- Bursting and Provision Throughput Modes
- Standard and Infrequent Access [Storage Classes](../S3/Storage%20Classes.md)
- [Lifecycle Policies](../S3/Lifecycle%20Configs.md) can be used with classes

![Pasted image 20250408194143.png](_atts/Pasted%20image%2020250408194143.png)

[https://en.wikipedia.org/wiki/File_system_permissions](https://en.wikipedia.org/wiki/File_system_permissions)
[https://docs.aws.amazon.com/efs/latest/ug/performance.html](https://docs.aws.amazon.com/efs/latest/ug/performance.html)