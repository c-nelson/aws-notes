Storage gateway is a product which integrates local infrastructure and AWS storage such as [S3](../../Storage/S3/S3.md), EBS [Snapshots](../../../linux/Snapshots.md) and [Glacier](../../Storage/S3/Storage%20Classes.md#Glacier%20-%20Instant).

- Normally runs on a virtual machine on-prem (or hardware appliance*)
- Presents storage using iSCSI, NFS, or SMB
- Used for migrations, extensions, storage tiering, DR and replacement of backup systems
## Volume Stored Mode
Behaves just like a NAS but is only for storage backup. Deals with full storage volumes.

All volumes presented to on-prem servers is stored locally. Storage Gateway is the backup.

Any data written to the local storage is also written to a local upload buffer temporarily and then copied asynchronously.

Copied to S3 in the form of EBS Snapshots.

**Doesn't improve local datacenter capacity**

![Pasted image 20250610204803.png](_atts/Pasted%20image%2020250610204803.png)
## Volume Cached Mode
Main location for data is now in an AWS managed S3. 

Local stores cache.
![Pasted image 20250610205935.png](_atts/Pasted%20image%2020250610205935.png)

## Tape (VTL) Mode
VTL mode allows the product to replace a tape based backup solution with one which uses S3 and Glacier rather than physical tape media.

Tape back ups are to actual tape disks that use sequential read/write. Can be used to back up large amounts of data but can only be totally overwritten.
![Pasted image 20250610210832.png](_atts/Pasted%20image%2020250610210832.png)

With Storage Gateway, the backup server uses the virtual tape storage just like a physical one.
![Pasted image 20250610211658.png](_atts/Pasted%20image%2020250610211658.png)

## File Mode
- Bridges on-prem file storage and S3
- Mount points (shares) available via NFS or SMB
- Each mount point maps directly onto a single S3 bucket
- Files stored into a mount point are visible as objects in an S3 bucket.
- Performs read and write caching for performance
- Critically, it allows your files to interact with other AWS services like [Lambda](../../Compute/Serverless/Lambda.md).

Single Site:
![Pasted image 20250610212654.png](_atts/Pasted%20image%2020250610212654.png)

Multiple Sites:
![Pasted image 20250610212945.png](_atts/Pasted%20image%2020250610212945.png)

With Replication:
![Pasted image 20250610213042.png](_atts/Pasted%20image%2020250610213042.png)

With [Lifecycle Configs](../../Storage/S3/Lifecycle%20Configs.md):
![Pasted image 20250610213259.png](_atts/Pasted%20image%2020250610213259.png)



