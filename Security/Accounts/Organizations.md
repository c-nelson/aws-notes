Allows large organizations to manage multiple AWS [Accounts](Accounts.md).

Within a "Standard AWS Account", you create an organization. That account then becomes the "Management Account".

Other "standard accounts" can then be invited to the organization. When a "standard account" joins an organization it becomes known as a "Member Account".

## Hierarchy
Organizations can be used in a hierarchical way, nesting organization. For example a corporate organization with multiple business unit organizations nested.

At the top of the hierarchy, there is the "Organization Root" container. The Organization Root can contain management accounts, member accounts, organizational units, which then can contain other accounts.

New accounts can be created directly within an organization.

![Pasted image 20250206210454.png](_atts/Pasted%20image%2020250206210454.png)

## Billing
Organizations allow consolidated [billing](Billing.md). Member accounts have their billing passed to the Management Account, this could also be referred to as the Payer Account. This allows for volume discounts.

## Users
With organizations, changes the best practice for [IAM Users](IAM%20Users.md). You don't need to have users within each account, you can instead use [IAM Roles](IAM%20Roles.md) within the management account to allow access to the member accounts.

Under the account drop down menu, the Switch Role button can be used on the management account to easily switch into roles for other accounts and save them for later use.

In practice this allows easy switching between accounts.

![Pasted image 20250206213941.png](_atts/Pasted%20image%2020250206213941.png)


