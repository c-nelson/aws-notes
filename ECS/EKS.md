Elastic Kubernetes Service is a fully-managed, Kubernetes implementation that simplifies the process of building, securing, operating, and maintaining Kubernetes clusters.

- Can run on:
	- AWS
	- Outposts
	- EKS Anywhere
	- EKS Distro
- Control plane scales an runs on multiple AZs
- Integrates with other services, [ECR](ECR.md), [[ELB]], [IAM](../Accounts/IAM.md), [VPC](../VPC/VPC.md)
- EKS Cluster == EKS Control Plane & EKS Nodes
- etcd distrubuted across multiple AZs
- Nodes can be:
	- [Self managed]([https://docs.aws.amazon.com/eks/latest/userguide/eks-compute.html](https://docs.aws.amazon.com/eks/latest/userguide/eks-compute.html))
		- Deploys on self managed [EC2](../EC2/EC2.md) instances
	- Managed node groups
		- Deploys to AWS managed/provisioned [EC2](../EC2/EC2.md) instances
	- [Fargate Pods]([https://docs.aws.amazon.com/eks/latest/userguide/fargate.html](https://docs.aws.amazon.com/eks/latest/userguide/fargate.html))
		- No need to manage scaling or provisioning
		- Runs on shared resources
	- Need to check node type for things like:
		- windows, GPU, Inferentia, Bottlerocket, Outposts, Local zones
- Persistent storage providers include [EBS](../EBS/EBS.md), EFS or FSx

![Pasted image 20250311215920.png](_atts/Pasted%20image%2020250311215920.png)
## Kubernetes review
Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

- ﻿﻿Cluster - A deployment of Kubernetes, management, orchestration .....
- ﻿﻿Node - Resources; pods are placed on nodes to run
- ﻿﻿Pod - 1+ Containers; smallest unit in kubernetes; often 1 container 1 pod
- ﻿﻿Service - Abstraction, service running on 1 or more pods.
- ﻿﻿Job - ad-hoc, creates one or more pods until completion.
- ﻿﻿Ingress - Exposes a way into a service (Ingress=>Routing=>Service=>1+ Pods)
- ﻿﻿Ingress Controller - used to provide ingress (e.g. AWS LB Controller uses ALB/NLB)
- ﻿﻿Persistent Storage (PV) - Volume whose lifecycle lives beyond any 1 pod using it

![Pasted image 20250311213443.png](_atts/Pasted%20image%2020250311213443.png)
![Pasted image 20250311214023.png](_atts/Pasted%20image%2020250311214023.png)