Elastic Container Registry is a managed container image registry service, like Docker Hub for AWS.

Stores images that can be used in things like  [ECS](ECS.md) or [EKS](EKS.md).

Each AWS account has a public and private registry.

Each registry can have many repositories.

Each repo can have many images.

Images can have serval tags - needs to be unique to repo.

Public means anyone has read-only access. Read-write requires permissions.

Private means permissions are required for read-only or read-write.

## Benefits
- Integrated with [IAM](../../Security/Accounts/IAM.md)
- Security - image scanning, basic and enhanced
- Metrics into [CW](../../Messages-Logs/CW/CW.md)
- API Actions into [CloudTrail](../../Messages-Logs/CloudTrail.md)
- Events into [[EventBridge]]
- Replication of image cross region or cross account