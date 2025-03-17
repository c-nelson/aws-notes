[ECS](ECS.md) is capable of running in EC2 mode or Fargate mode.
## [EC2](../EC2/EC2.md) Mode
- Deploys EC2 instances into your account
- Pay for instances regardless of container usage
- Use if you need to manage scaling and capability
- Can use your [reserved](../EC2/Purchase%20Options.md#Reserved) EC2 instances

![Pasted image 20250309211741.png](_atts/Pasted%20image%2020250309211741.png)

## Fargate mode
- Shared infrastructure
- Don't have to manage EC2 instances
- ECS task inject [ENIs](../EC2/Networking.md#Elastic%20Network%20Interfaces%20(ENI)) into your [VPC](../VPC/VPC.md)
	- From there the network interface acts just like any other resource in a VPC
- Pay only for container resources used while they are running

![Pasted image 20250309212244.png](_atts/Pasted%20image%2020250309212244.png)

## [EC2](../EC2/EC2.md) vs ECS
Which to pick between EC2 instances, ECS in EC2 mode and EC2 in Fargate mode:
- If you use containers, use ECS
- Large workload - price conscious, use ECS EC2 Mode
- Large workload - overhead conscious, use Fargate
- Small / Burst workloads, use Fargate
- Batch / Periodic workloads, use Fargate