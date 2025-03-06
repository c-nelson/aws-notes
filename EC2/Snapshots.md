[EBS](../EBS/EBS.md) Snapshots are backups of data consumed within EBS Volumes - Stored on [S3](../S3/S3.md).

Snapshots are incremental, the first being a full backup - and any future snapshots being incremental. Each snapshot only records changed data.

Snapshots can be used to migrate data to different availability zones in a region, or to different regions of AWS.

Volumes can be created/restored from snapshots.

![Pasted image 20250301200914.png](_atts/Pasted%20image%2020250301200914.png)

- Snaps restore lazily - fetched gradually
	- Will be lower performance until all data is fetched
- Requested blocks are fetched immediately

Forcing all data to restore from S3
- To force EBS to pull all the data from S3, you can use something like DD to read the whole volume
- Fast Snapshot Restore (FSR) - feature created to immediately restore
	- Up to 50 snaps per region
	- Set on Snap & AZ
	- Extra cost

#### Pricing
- GB/month
- Billed on used data, not allocated
	- A snapshot can be less than a volume capacity if not filled