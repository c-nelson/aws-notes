Nested stacks allow for a hierarchy of related [CloudFormation](CloudFormation.md) templates to be combined to form a single product

A root stack can contain and create nested stacks .. each of which can be passed parameters and provide back outputs.

Nested stacks should be used when the resources being provisioned share a lifecycle and are related.

### Without a nested stack
![Pasted image 20250710195108.png](_atts/Pasted%20image%2020250710195108.png)


### With a nested stack
- When using nested stacks you can reuse the template but new resources are created. 
- You can use [Cross-Stack References](Cross-Stack%20References.md) to reuse the same resources.
- Use only when everything is lifecycle linked
![Pasted image 20250710195954.png](_atts/Pasted%20image%2020250710195954.png)
