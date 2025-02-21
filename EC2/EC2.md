Elastic Compute Cloud

Resilience: [[Resilience#AZ|AZ]] 

Infrastructure as a Service (IAAS)
Provides access to virtual machines, instances. Meaning you manage from the operating system upwards.

EC2 is a [[Public vs Private Services#Private service|private services]] and uses [[VPC|VPC networking]] and launches into a single VPC subnet.

On-demand billing - per second.

Local on-host storage or Elastic Block Storage (EBS)

## States
- Running
- Stopped
- Terminated

Understanding [[Billing]] with EC2 states.

When an instance is stopped you still pay for storage.

![[Pasted image 20250121220955.png]]

## AMI
Amazon Machine Image

Similar to a operating system image.

Contains:
- Attached permissions for who is allowed to create instances using the image.
- Root volume
- Block Device mapping

