Elastic Compute Cloud

Resilience: [AZ](../Fundamentals/Resilience.md#AZ) 

Infrastructure as a Service (IAAS)
Provides access to virtual machines, instances. Meaning you manage from the operating system upwards.

EC2 is a [private services](../Fundamentals/Public%20vs%20Private%20Services.md#Private%20service) and uses [VPC networking](../VPC/VPC.md) and launches into a single VPC subnet.

On-demand billing - per second.

Local on-host storage or Elastic Block Storage (EBS)

## States
- Running
- Stopped
- Terminated

Understanding [Billing](../Accounts/Billing.md) with EC2 states.

When an instance is stopped you still pay for storage.

![Pasted image 20250121220955.png](_atts/Pasted%20image%2020250121220955.png)

## AMI
Amazon Machine Image

Similar to a operating system image.

Contains:
- Attached permissions for who is allowed to create instances using the image.
- Root volume
- Block Device mapping

