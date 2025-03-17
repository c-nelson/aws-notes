Instance roles and Instance Profiles are how applications running on an [EC2](EC2.md) instance can be given permissions to access AWS resources on your behalf.

Short Term Temporary credentials are available via the EC2 Instance [Metadata](Metadata.md) and are renewed automatically by the EC2 and [STS](../Misc/STS.md) Services.

Instance Profile -
- Wrapper around an [IAM Roles](../Accounts/IAM%20Roles.md)
- The profile is what is attached to the instance, not the role.
- Allows permissions to get into the instance
- When creating an instance role in UI, profile is created automatically
- In [CFN](../CFN/CFN.md) or command-line, instance role and profile need to be created separately
- Credentials at `http://169.254.169.254/latest/meta-data/iam/security-credentials/role-name`
- Automatically rotated

![Pasted image 20250313215117.png](_atts/Pasted%20image%2020250313215117.png)