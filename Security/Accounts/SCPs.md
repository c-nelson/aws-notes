Service Control Policies

A feature of AWS [Organizations](Organizations.md) which allow restrictions to be placed on MEMBER accounts in the form of boundaries.

JSON policies that can be attached to the organization root container, organization units, or individual accounts.

The management account is special, because even if it has SCPs attached to it either by the organization root or directly attached, it is never affected by SCPs. Since the management account cannot be restricted, it is best practice to not use the management account for resources.

![Pasted image 20250208202014.png](_atts/Pasted%20image%2020250208202014.png)

- SCPs are account permission boundaries
	- They limit even what the root of an account can do
- SCPs do not grant any permissions, they just provide boundaries for what an account can do.
	- Any service that is allowed through SCPs is a service that CAN have permissions set up for identities within the accounts

## Allow list vs Deny list

- Allow list - everything is denied by default, you provide a list of services member accounts are allowed to use.
	- To use allow list you need to remove the default "FullAWSAccess" SCP
- Deny list (default) - everything is allowed by default, you provide a list of services member accounts are not allowed to use.
	- Default is applied to the root org and all containing OUs.

## How SCPs affect [Identity Policies](Identity%20Policies.md)
Only actions that are the overlap of the SCP and the Identity polices are allowed. If it is allowed with the SCP and not within the identity policy, then it has no affect.

![Pasted image 20250208210014.png](_atts/Pasted%20image%2020250208210014.png)

