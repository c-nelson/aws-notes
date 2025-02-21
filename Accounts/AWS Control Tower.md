AWS Control Tower offers a straightforward way to set up and govern an AWS multi-account environment, following prescriptive best practices. AWS Control Tower orchestrates the capabilities of several other AWS services, including AWS [Organizations](Organizations.md), AWS Service Catalog, and AWS IAM Identity Center (successor to AWS Single Sign-On), to build a landing zone in less than an hour. Resources are set up and managed on your behalf.

AWS Control Tower orchestration extends the capabilities of AWS [Organizations](Organizations.md). To help keep your organizations and accounts from drift, which is divergence from best practices, AWS Control Tower applies preventive and detective controls (guardrails).
For example, you can use guardrails to help ensure that security logs and necessary cross-account access permissions are created, and not altered.

![Pasted image 20250209134108.png](_atts/Pasted%20image%2020250209134108.png)
## Landing Zone
Where most of the Control Tower multi-account operations are performed.

Allows for well architected multi-account environtments with a Home Region.

Build with [Organizations](Organizations.md), [[AWS Config]], and [CFN](../CFN/CFN.md).

Creates:
- Security Organizational Unit for Log Archive and Audit Accounts
- Sandbox OU for test/less rigid security

Ability to create other OU's and accounts

[[IAM Identity Center]] - Provides SSO/ID Federation, Centralized Logging & Auditing.

## Guard Rails
Detect/Mandate rules and standards across all accounts.

Types:
- Mandatory
- Strongly Recommended
- Elective

Functions:
- Preventive - stops accounts from doing things ([SCPs](SCPs.md))
	- enforced or not enabled
	- Ex. allow/deny regions, disallow policy changes
- Detective - compliance checks ([[AWS Config]] rules)
	- Clear, in violation or not enabled
	- Ex. CloudTrail enabled or EC2 public IPv4

## Account Factory
Automates and standardizes new account creation.

Can be performed by cloud admins or end users (with proper permissions).

Guardrails are automatically added to new accounts.

Can give account admin to [IAM Users](IAM%20Users.md) that already exist within the [Organizations](Organizations.md).

Allows you to defined a standard for account and network creations.

Accounts can be closed or repurposed.

Account Factory can be accessed through APIs, so you can manage accounts via software.

