[[S3]] access logging provides detailed records for the requests that are made to a bucket.

Access log information can be useful in security and access audits. It can also help you learn about your customer base and understand your S3 bill.

![[Pasted image 20250217124257.png]]
- Logs are made to a target bucket
- Enable logging on source bucket
- S3 Log Delivery Group reads configuration on source bucket
	- Given access by [[S3 Security#Access Control Lists (ACLs)|ACLs]]
- Best efforts process
- Log records are space-delimited files
- One log target can be set for many buckets, separated by prefixes