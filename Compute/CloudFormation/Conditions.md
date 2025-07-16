The optional `Conditions` section contains statements that define the circumstances under which entities are created or configured. You might use conditions when you want to reuse a [CloudFormation](CloudFormation.md) template that can create resources in different contexts, such as a test environment versus a production environment.

- Conditions are evaluated to TRUE or FALSE
- Processed before resources are created
- Uses AND, EQUALS, IF, NOT, OR
- Associated with logical resources to control if they are created or not

![Pasted image 20250709205627.png](_atts/Pasted%20image%2020250709205627.png)