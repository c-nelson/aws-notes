Aurora Serverless is to [Aurora](Aurora.md) Provisioned what [Fargate](../ECS/Cluster%20Mode.md#Fargate%20mode) is to [ECS](../ECS/ECS.md).

With serverless, you don't need to manage database instances.

## Concepts
- Scalable - ACU - Aurora Capacity Units
- An Aurora Severless cluster has a MIN & MAX ACU
- Cluster adjusts based on load
- Can go to 0 and be paused
- Consumption billing per-second basis
- Same resilience as [Aurora](Aurora.md) (6 copies across AZs)

## Architecture
- Your storage is stored in a cluster across AZs
- AWS manages a shared pool of warm ACU instances
- When needed an instance is provided to you and your storage attached.
- Because any one of the instances can be provisioned to a different account, a proxy fleet is used to broker between an application and the ACU
![Pasted image 20250403204603.png](_atts/Pasted%20image%2020250403204603.png)

## Use Cases
- Infrequently used apps
- New applications, unsure of scale
- Variable workloads
- Unpredictable workloads
- Development and test databases
- Multi-tenant applications



