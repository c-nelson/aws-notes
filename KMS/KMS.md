Key Management Service
***
[[Resilience#Region|Regional]] & [[Public vs Private Services#Public service|Public Service]]
***
- Create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications.
- Can use symmetric and asymmetric keys.
- Cryptographic operations (encrypt, decrypt)
- **Keys never leave KMS** #AWSCommonTest
- Permissions are granular, ex separate permissions to encrypt vs decrypt
- Provides security standard - FIPS 140-2 (L2) #AWSCommonTest 

## KMS Keys
- Keys are logical - ID, date, policy, desc & state
- Backed by physical key material
- Generated or imported
- Can be used for up to 4KB of data
- Isolated to a region and never leave
	- Support for multi-region keys if required
- AWS Managed Keys
	- Used automatically be certain services
- Customer Managed Keys
	- To use directly within apps or services
- Support rotation - physical backing material changed

![[Pasted image 20250211211254.png]]

## Data Encryption Keys (DEKs)
- GenerateDataKey operation
- Works on > 4KB
- Linked to KMS Keys
- DEK is not stored
- User performs encryption
	- KMS provides a plaintext encryption key
	- KMS provides a ciphertext (encrypted version of the plaintext key)
	- Use the plaintext key to encrypt the data
	- Discard the plaintext key
	- Store the ciphertext with data
	- Send the ciphertext back to KMS to get the plaintext encryption key
	- Decrypt the data
	- Discard the plaintext key

## Policies and Security
- Every key has a Key Policy (like a [[S3 Security#Bucket Policies|resource policy]])
- Unlike other resource policies, key policies have to be told to trust even the root account user.
	- Beware of removing access to key
- Admins can be given access to create and manage keys but withheld access to do encryption/decryption on data.
	- Common security requirement
- Generally key policies are used to allow management of keys
- Then, IAM [[Identity Policies]] are used to allow usage of keys.