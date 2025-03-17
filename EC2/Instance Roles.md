Instance roles and Instance Profiles are how applications running on an [[EC2]] instance can be given permissions to access AWS resources on your behalf.

Short Term Temporary credentials are available via the EC2 Instance [[Metadata]] and are renewed automatically by the EC2 and [[STS]] Services.

Instance Profile -
- Wrapper around an [[IAM Roles]]
- The profile is what is attached to the instance, not the role.
- Allows permissions to get into the instance
- When creating an instance role in UI, profile is created automatically
- In [[CFN]] or command-line, instance role and profile need to be created separately
- Credentials at `http://169.254.169.254/latest/meta-data/iam/security-credentials/role-name`
- Automatically rotated

![[Pasted image 20250313215117.png]]