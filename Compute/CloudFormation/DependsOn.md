With the `DependsOn` attribute you can specify that the creation of a specific [CloudFormation](CloudFormation.md) resource follows another. When you add a `DependsOn` attribute to a resource, that resource is created only after the creation of the resource specified in the `DependsOn` attribute.

- CloudFormation tries to do things in parallel
- Automatically tries to determine a dependency order (VPC => SUBNET => EC2)
- Determines based on references or functions
- DependsOn lets you explicitly define theses

![Pasted image 20250709210522.png](_atts/Pasted%20image%2020250709210522.png)