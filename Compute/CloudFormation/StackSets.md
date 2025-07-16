StackSets are a feature of [CloudFormation](CloudFormation.md) allowing infrastructure to be deployed and managed across multiple regions and multiple accounts from a single location.

Additionally it adds a dynamic architecture - allowing automatic operations based on accounts being added or removed from the scope of a StackSet.

- StackSets are containers in an admin account
- Contain stack instances which are references to stacks
- Stack instances & stacks are in 'target accounts'
- Each stack = 1 region in 1 account
- Uses self-managed or service-managed roles

![Pasted image 20250710203415.png](_atts/Pasted%20image%2020250710203415.png)

- Terms
	- Concurrent Accounts - how many accounts can be used at the same time
	- Failure Tolerances - amount of individual deployments can fail before the StackSet itself is failed
	- Retain Stacks - by default removing a StackSet removes all, this allows some to be retained