Cross stack references allow one [CloudFormation](CloudFormation.md) stack to reference another

Outputs in one stack reference logical resources or attributes in that stack

They can be exported, and then using the `!ImportValue `intrinsic function, referenced from another stack.

- Example would be a shared [VPC](../../Network/VPC/VPC.md) between stacks
- Outputs are normally not visible from other stacks
	- [Nested Stacks](Nested%20Stacks.md) can references them
- Outputs can be exported, making them visible from other stacks
- Exports must have a unique name in the region
- `Fn::ImportValue` used to reference resource

![Pasted image 20250710202543.png](_atts/Pasted%20image%2020250710202543.png)

