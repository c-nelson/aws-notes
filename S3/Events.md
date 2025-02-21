[[S3]] notification feature enables you to receive notifications when certain events happen in your bucket.

[[EventBridge]] is likely the better solution.

![[Pasted image 20250217122004.png]]

- Create Event Notification Config
- Receiving service needs a resource policy allowing S3
- Events are JSON

Can be delivered to:
- SNS
- SQS
- Lambda

Event types:
- Created
	- Put
	- Post
	- Copy
	- CompleteMultiPartUpload
- Delete
	- *
	- Delete
	- DeleteMarkerCreated
- Restore
	- Post (initiated)
	- Completed
- Replication
	- OperationMissedThreshold
	- OperationReplicatedAfterThreshold
	- OperationNotTracked
	- OperationFailedReplication

