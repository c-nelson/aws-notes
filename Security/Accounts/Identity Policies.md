[IAM](IAM.md) Policies

Grants or denies access AWS products and features to any identity that uses the policy.

IAM Policy Document is JSON, containing `"Statement"` objects.

## Statements

AWS has a collection of Statements from various policies which apply to an identity.

A statement only applies if the action you are trying to perform matches both the action and resouce.

Statement properties:
- Sid - name the statement
- Effect - Allow/deny
- Action - `service:operation`, wildcard, or list of operations
- Resource - wildcards or [ARN](../../Fundamentals/ARN.md), ARN list

```json
{
	"Version": "2012-10-17" ,
	"Statement": [
		"Sid": "FullAccess",
		"Effect": "Allow",
		"Action": ["s3:*"],
		"Resource": ["*"]
	},
	{
		"Sid": "DenyCatBucket",
		"Action": ["s3:*"],
		"Effect": "Deny",
		"Resource": ["arn:aws:s3::: catgifs", "arn:aws:53::: catgifs/*" ]
	}
}
```

## Policy Priority

The above statements allow full access to any bucket and then denies access to the "catgifs" bucket.

#AWSCommonTest 

Priorities of policies, order of operation:
1) Explicit denies
2) Explicit allows
3) Default deny

This means that a deny will always take priority.

By default, all users have no access. There has to be an allow for you to have access.

There can be multiple policies for any action, for example a user policy, group policy and resource policy. AWS gathers all policies to be evaluated when performing an action.

## Inline vs Managed Policies

Managed - create a single json document and apply it to many identities.

Inline - applying the json document to each identity individually. Generally used for special or exceptional access rights.


