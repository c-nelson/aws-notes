## Single PUT Upload
- Default put operation
- Operation `s3:PutObject`
- Single data stream to [[S3]]
- If stream fails, upload fails
- Speed and reliability limited by 1 stream
- Limited to up to 5GB

## Multipart Upload
- Data is broken up into parts
- Minimum data size 100MB to use multipart
	- Best practice: always use multipart if over 100MB
- 10,000 max parts, 5MB - 5GB each
	- Last part can be smaller than 5MB
- If a part fails, it can be restarted
- Faster uploads, part streams upload in parallel

## Accelerated Transfer
- Disabled by default
	- If disabled, the data travels the public internet to get to the bucket location
	- Restrictions for enabling
		- Bucket name cannot contain periods
		- Must be DNS compatible in naming
- Regardless of bucket location, the data enters the closet edge location.
- Then uses the AWS private network to transfer to the pubic.
- When enabled there is an accelerated endpoint provided
- [Compare Speeds](http://s3-accelerate-speedtest.s3-accelerate.amazonaws.com/en/accelerate-speed-comparsion.html)

![[Pasted image 20250211204734.png]]
![[Pasted image 20250211204649.png]]