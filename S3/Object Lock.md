You can use [S3](S3.md) Object Lock to store objects using a _write-once-read-many_ (WORM) model. It can help you prevent objects from being deleted or overwritten for a fixed amount of time or indefinitely.

![Pasted image 20250217130332.png](_atts/Pasted%20image%2020250217130332.png)

- WORM - no delete or overwrite
- Can be enabled on new buckets, support request for existing buckets
- Requires versioning - individual versions are locked
- 2 ways to lock
	- Retention Period
	- Legal Hold
	- Can have both, one or the other, or none
- Can be set on objects or a bucket can have default object lock settings

## Retention Period
- Specify days and years
- Modes #AWSCommonTest 
	- Compliance
		- Can't be adjusted, deleted or overwritten
		- The retention period itself cannot be reduced or changed, even root user
		- Can't change until retention expires
	- Governance
		- Special permissions can be granted allowing lock settings to be adjusted
		- Permission: `s3:BypassGovernanceRetention`
		- Header: `x-amz-bypass-governance-retention:true`
			- Default for console UI

## Legal Hold
- Set ON or OFF on object version
- No retention period
- No Deletes or Changes until removed
- Action: `s3:PutObjectLegalHold`