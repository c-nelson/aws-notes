By default data on [[EBS]] is not encrypted.

EBS encryption uses [[KMS]].

Can be the default service key `aws/ebs`, or a custom managed key.

The key is used to create a [[KMS#Data Encryption Keys (DEKs)|DEK]] that is used to encrypt the data. `GenerateDataKeyWithoutPlaintext`

KMS sends the [[EC2]] host the encryption key to hold in memory.

[[03_Resources/aws/EC2/Snapshots|Snapshots]] are encrypted using the same key.

No cost for data encryption, should be used by default for EBS.

![[Pasted image 20250302194415.png]]

- [[Accounts]] can be set to use encryption by default
	- Default KMS key
	- Otherwise choose a KMS key
- Each volume uses 1 unique DEK
	- Snapshots & future volumes from snapshots use the same DEK
- Can't change a volume back to unencrypted
- OS isn't aware of the encryption - no performance loss






