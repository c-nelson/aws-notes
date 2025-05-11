Combining [Auto Scaling Groups](../../Compute/EC2/ASG/Auto%20Scaling%20Groups.md) with [ELB](ELB.md):
- When [ASG](../../Compute/EC2/ASG/Auto%20Scaling%20Groups.md) provision/shutdown instance, automatically added to [ELB](ELB.md) Target Groups
- ASG can be configured to use the Load Balancer health checks rather than EC2 [Status Checks](../../Compute/EC2/Status%20Checks.md), giving application awareness

![Pasted image 20250412221554.png](_atts/Pasted%20image%2020250412221554.png)
