Amazon Macie is a fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data in AWS.

[https://docs.aws.amazon.com/macie/latest/user/managed-data-identifiers.html](https://docs.aws.amazon.com/macie/latest/user/managed-data-identifiers.html)

[https://docs.aws.amazon.com/macie/latest/user/custom-data-identifiers.html](https://docs.aws.amazon.com/macie/latest/user/custom-data-identifiers.html)

[https://docs.aws.amazon.com/macie/latest/user/findings-types.html](https://docs.aws.amazon.com/macie/latest/user/findings-types.html)

- Discover, monitor and protect data stored in [S3](../Storage/S3/S3.md) buckets
- Automated discovery of data i.e PII, PHI Finance
- Managed Data Identifiers
	- Built-in - ML/Patterns
- Custom Data Identifiers
	- Proprietary - Regex Based
- Integration with security hub & 'finding events' to [CloudWatch Events & EventBridge](../Messages-Logs/CW/CloudWatch%20Events%20&%20EventBridge.md)
- Centrally managed either via [Organizations](Accounts/Organizations.md) or one Macie Account Inviting

![Pasted image 20250630214147.png](_atts/Pasted%20image%2020250630214147.png)

## Findings
- Policy Findings
	- When security config of an S3 bucket changes
	- Policy:IAMUser/S3BlockPublicAccessDisabled,  Policy:IAMUser/S3BucketEncryptionDisabled, Policy:|AMUser/ S3BucketPublic, Policy:IAMUser/S3BucketShared
- Sensitive Data Findings
	- SensitiveData:S3Object/Credentials, SensitiveData:S30bject/Customldentifier, SensitiveData:S30bject/Financial, SensitiveData:S3Object/Multiple, SensitiveData:S3Object/Personal
