[S3](S3.md) Security is controlled via a combination of Identity Policies, Bucket Policies (Resource Policies) and Legacy Bucket and Object ACLs.

**S3 is private by default**. Root user of the account is the only identity that can access the bucket.
## Bucket Policies
- A form of resource policy
- Like identity policies but attached to a bucket
- Resource perspective permissions
	- Inverse of [Identity Policies](../../Security/Accounts/Identity%20Policies.md), you control who can access the resource
- Allow/Deny from the same or different accounts
	- [Identity Policies](../../Security/Accounts/Identity%20Policies.md) cannot provide rules for access from outside account sources
- Allow/Deny from anonymous principals

[Example Bucket Policies](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html)

The "Principal" key within the JSON policy is what differentiates resource policies from identity policies.

![Pasted image 20250209214313.png](_atts/Pasted%20image%2020250209214313.png)

Conditions can be used in the policy to grant access to specific IPs, only multi-factor authentication, and many more options.

## Access Control Lists (ACLs)
- Legacy security for buckets. Not best practice to use.
- Ways to provide security on objects and buckets
- It is a sub-resource
- Inflexible and simple

## Block Public Access
A setting to block all anonymous, non AWS Identity, from accessing a bucket.

## Resource vs [Identity Policies](../../Security/Accounts/Identity%20Policies.md)

- Identity: Controlling different resources
- Identity: You have a preference for IAM
- Identity: Same account
- Bucket: Just controlling S3
- Bucket: Anonymous or Cross-Account
- ACLS: NEVER - unless you must