Elastic Container Service

Run a container without an EC2 instance.

[Cluster Mode](Cluster%20Mode.md)s:
- EC2 mode - regular [EC2](../EC2/EC2.md) hosts running ECS software
- Fargate mode - serverless containers

- [Container Definition](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html)
	- Where the image is
	- Which ports
- [Task Definition](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_TaskDefinition.html)
	- Wraps container definitions
	- Represents an application as a whole
	- Could contain 1 to many container definitions
		- Web app, database containers
	- Stores - Resources, networking, capability
	- Task role - IAM role that the task can use to gain credentials
		- Best way to give ECS containers access to AWS resources
- Service Definition
	- Wraps a task definition
	- Defines how we want a task to scale
	- Adds capacity and resilience 