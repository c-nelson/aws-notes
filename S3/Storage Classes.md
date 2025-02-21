https://aws.amazon.com/s3/storage-classes/
https://aws.amazon.com/s3/pricing/

Types of [[S3]] storage classes:
## Standard
- Default
- Objects are replicated across at least 3 [[Resilience#AZ|AZs]] within the region.
- 99.999999999% durability, for 1:10,000,000 objects loss per 10,000 years
- Content-MD5 Checksums
- Cyclic Redundancy Checks (CRCs) - detect and fix corruption
- #AWSCommonTest Responds with HTTP/1.1 200 OK status if object is stored durably.
- Billed GB/month fee for data stored
	- $1 per GB for transfer OUT
	- A price per 1,000 requests
	- No specific retrieval fees
	- No minimum duration
	- No minimum size
- Milliseconds first byte latency, data accessible within milliseconds of uploading, and can be public
- Should be used in most cases
	- For frequently accessed data which is important and non replaceable

## Standard-IA
- Infrequent Access
- Overall the same as standard but:
	- Object storage per month is cheaper
	- There is a retrieve fee
		- Results increased cost if accessed frequently
	- Minimum of 30 days charged for an object
	- Minimum capacity charged for 128KB per object
- Should be used for long-lived data, which is important but accessed infrequently, guideline of ~1 retrieval per month

## One Zone-IA
- Same as Standard-IA but:
	- Data is only stored in one AZ
		- Same reliability (data is replicated) but within AZ
	- The storage is cheaper
- Should be long-lived non-critical or replaceable data which is accessed infrequently

## Glacier - Instant
- Similar to Standard-IA but:
	- Cheaper storage
	- More expensive retrieval
	- 90 day minimum charged
- Should be used for long-lived data which is accessed ~1 per quarter.
- Still offers instant access

## Glacier - Flexible
- Cold storage
- Even cheaper but:
	- Objects cannot be made publicly accessible
	- Requires a retrieval process which is not instant
		- Fee for retrieval
		- Which retrieved objects are stored on Standard-IA for a temporary basis
		- Fees for faster retrieval:
			- Expedited (1-5 minutes)
			- Standard (3-5 hours)
			- Bulk (5-12 hours)
		- #AWSCommonTest First byte latency of minutes or hours
	- 40KB minimum charge data charge
	- 90 day minimum charge
- Used for archival data where frequent or realtime access isn't needed. ~1 per year.

## Glacier - Deep Archive
- Frozen storage
- The cheapest storage class but:
	- Longer retrieval times
		- Standard (12 hours)
		- Bulk (up to 48 hours)
	- First byte latency of hours or days
	- 180 day minimum charge
- Should be used for archival data that rarely if ever needs to be accessed.

## Intelligent-Tiering
- Contains 5 different storage tiers
	- Frequent Access
	- Infrequent Access
	- Archive Instant Access
	- Achieve Access - optional
	- Deep Archive - optional
- You don't move objects yourself
- Object usage is monitored
	- Automatically moves objects not accessed for 30 days to infrequent tier
	- Buckets configuration or object tags can set to move to Archive tiers, 
	- 90 days of no access for Archive Instant Access
	- 90 - 270 days for Archive Access
	- 180 - 730 days for Deep Archive
- Only use the optional archive tiers if the application can tolerant non-instant access
- Data is moved back to frequent access when used
- Charged for a monitoring and automation cost per 1000 objects
	- Frequent access charges the same as Standard
	- Infrequent the same as Standard-IA, etc
- Used for long-lived data with changing or unknown patterns of data usage.