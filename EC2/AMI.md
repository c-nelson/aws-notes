Amazon Machine Images (AMI)'s are the images which can create [EC2](EC2.md) instances of a certain configuration.

- Used to launch instances
- AWS or community provided
- Marketplace - can include commercial software
	- Extra cost for licenses
- Each region has a set of AMIs
	- Each has a unique ID
	- Can only be used in same region
- Permissions on custom AMI access
	- Public
	- Your account
	- Specific accounts
- Can create an AMI from an existing instance to use as a template
- Instances should be stopped before creating an AMI from it

## Lifecycle
When creating a custom AMI with linked [EBS](../EBS/EBS.md) volumes, [Snapshots](Snapshots.md) are taken. The snapshots are referenced inside the AMI using a Block Device Mapping (contains mapping to snapshot ID and the device mapping ex. /dev/xvda). 
When the AMI is used for a new instance, new [EBS](../EBS/EBS.md) volumes are created with the same data from the snapshots.

![Pasted image 20250304193733.png](_atts/Pasted%20image%2020250304193733.png)

## Key points #AWSCommonTest 
- AMIs are within one region
- AMI Baking - creating an AMI from a configured instance with applications
- AMIs can't be edited
	- To update one, launch an instance, update configuration and make a new AMI
- Can be copied between regions and includes its snapshots
- Default permissions is your account only
- AMIs include snapshots so there is billing related to that storage



