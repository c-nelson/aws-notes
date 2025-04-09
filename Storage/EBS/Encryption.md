By default data on [EBS](EBS.md) is not encrypted.

EBS encryption uses [KMS](../../Security/KMS/KMS.md).

Can be the default service key `aws/ebs`, or a custom managed key.

The key is used to create a [DEK](../../Security/KMS/KMS.md#Data%20Encryption%20Keys%20(DEKs)) that is used to encrypt the data. `GenerateDataKeyWithoutPlaintext`

KMS sends the [EC2](../../Compute/EC2/EC2.md) host the encryption key to hold in memory.

[Snapshots](../../../linux/Snapshots.md) are encrypted using the same key.

No cost for data encryption, should be used by default for EBS.

![Pasted image 20250302194415.png](_atts/Pasted%20image%2020250302194415.png)

- [Accounts](../../Security/Accounts/Accounts.md) can be set to use encryption by default
	- Default KMS key
	- Otherwise choose a KMS key
- Each volume uses 1 unique DEK
	- Snapshots & future volumes from snapshots use the same DEK
- Can't change a volume back to unencrypted
- OS isn't aware of the encryption - no performance loss






