[CloudFormation](CloudFormation.md) defines logical resources within templates (using YAML or JSON). The logical resource defines the WHAT, and leaves the HOW up to the CFN product. A CFN stack creates a physical resource for every logical resource - updating or deleting them as a template changes.

- Logical resources - the "WHAT"
- Templates are used to create Stacks
- Stacks create physical resources from the logical
- If a stacks template is changed - physical resources are changed
- If stack is deleted, physical resources are deleted

![Pasted image 20250701204500.png](_atts/Pasted%20image%2020250701204500.png)