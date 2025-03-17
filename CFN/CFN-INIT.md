CFN-INIT is a powerful desired-state-like configuration engine which is part of the [[CFN]] suite of products, allowing complex [[Bootstrapping]].

It allows you to set a state for things like packages, users, groups, sources and files within resources inside a template and it will make that change happen on the instance, performing whatever actions are required.

- cfn-init helper script install on [[EC2]] OS
- Simple configuration management system
- Allows for Desired state
	- vs Procedural for [[Bootstrapping#User Data|User Data]]
- Packages, groups, users, sources, files, commands and services
- Provided with directives via [[Metadata]] and `AWS::CloudFormation::Init` on a [[CFN]] resource.

![[Pasted image 20250313202712.png]]

## CFN-SIGNAL
Creation policies create a 'WAIT STATE' on resources, not allowing the resource to move to CREATE_COMPLETE until signaled using the cfn-signal tool.

If the output of the cfn-init command is an ok status or an error, cfn-signal reports back to [[CFN]]. If no signal for timeout period, then the stack is unsuccessful.

![[Pasted image 20250313203435.png]]