A user pool is a user directory in Amazon Cognito. With a user pool, your users can sign in to your web or mobile app through Amazon Cognito. Your users can also sign in through social identity providers like Google, Facebook, Amazon, or Apple, and through SAML identity providers. Whether your users sign in directly or through a third party, all members of the user pool have a directory profile that you can access through a Software Development Kit (SDK).

Amazon Cognito identity pools (federated identities) enable you to create unique identities for your users and federate them with identity providers. With an identity pool, you can obtain temporary, limited-privilege AWS credentials to access other AWS services.

- Provides Authentication, Authorization and user management for web/mobile apps
- #AWSCommonTest Cognito has bad naming, there are two main services:
## User Pools
- About log in and managing user identities
- Sign-in and get a JSON Web Token JWT
- Provides:
	- User directory management and profiles
	- sign-up & sign-in with customizable web UI
	- MFA and other security features
![Pasted image 20250510204838.png](_atts/Pasted%20image%2020250510204838.png)

## Identity Pools
- Is about swapping an identity for AWS credentials
- Allow you to offer access to temporary AWS Credentials
- Unauthenticated Identities - Guest Users
- Federated Identities - SWAP - Google, FB, Twitter SAML, User Pool for short term AWS Credentials to access AWS Resources
![Pasted image 20250510205252.png](_atts/Pasted%20image%2020250510205252.png)

## Both combined
Identity pool only needs to be configured to handle User pool JWTs.
![Pasted image 20250510205520.png](_atts/Pasted%20image%2020250510205520.png)