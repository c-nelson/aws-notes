[S3](S3.md) Encryption

Buckets aren't encrypted, objects are.

AWS has made server-side encryption mandatory, data must be encrypted at rest.
## Client vs Server side encryption
Generally, data in transit to S3 is always encrypted. We are comparing data a rest inside S3.

Client side - data is encrypted before it is even sent, it is never seen by S3 unencrypted. You are then responsible for handling the key.

Sever side - data is sent to S3, then encrypted. AWS handles the key.

## Types of SSE
#### SSE-C
Server-side encryption with customer-provided keys
- S3 still does the encryption/decryptions
- When uploading object, provide the object and encryption key
- After encryption, a hash of the key is attached to the object and the key is destroyed
- To request data, you need to provide the key
- This saves local compute resources vs client-side
#### SSE-S3
Server-side encryption with [S3](S3.md) managed keys
- Default option
- AES256 algo #AWSCommonTest
- Just provide the object, S3 creates and manages a key for every object
- S3 also has a service level key on top of the object key that is unmanaged by the user
	- This key encrypts the object level key, then the object key is destroyed
	- Then the encrypted object key and the encrypted object are put onto storage
- Pros - easy to manage
- Cons:
	- no control over encryption,
	- may not be acceptable for highly controlled environments
	- The S3 admin manager role can always view the data
#### SSE-KMS
Sever-side encryption with [KMS](../../Security/KMS/KMS.md) managed keys
- This allows the customer to create and manage the key in KMS
- When an object is upload, KMS sends S3 a plaintext key and a [DEK key](../../Security/KMS/KMS.md#Data%20Encryption%20Keys%20(DEKs))
	- KMS Keys can only encrypt up to 4KB, so DEK keys are used
	- KMS does not store the DEK key, only generates them and gives them to S3
- Object is encrypted using the plaintext key, and then the encrypted object and the DEK are stored on S3
- KMS does not store
- Pros:
	- Gives more control over the keys being used
	- Logging and auditing on keys
	- Allows for role separation
		- Need access to key and S3 bucket to decrypt
		- Admin can have control over bucket but not given access to read data



[https://docs.aws.amazon.com/AmazonS3/latest/user-guide/default-bucket-encryption.html](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/default-bucket-encryption.html)
[https://docs.aws.amazon.com/kms/latest/developerguide/services-s3.html](https://docs.aws.amazon.com/kms/latest/developerguide/services-s3.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingServerSideEncryption.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingServerSideEncryption.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerSideEncryptionCustomerKeys.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerSideEncryptionCustomerKeys.html)