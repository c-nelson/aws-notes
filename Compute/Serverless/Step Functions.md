Separate product from [Lambda](Lambda.md) which lets you build long running serverless workflow based applications.

Chaining lambda functions together gets messy and is bad practice. Each runtime environment with a lambda function is stateless.

## State Machines
Step Functions allows you to create State Machines:
- Serverless workflow, START -> STATES -> END
- Used for backend processing
	- Uses Amazon States Language (ASL) - JSON Template
- States are _things_ which occur
- [IAM Roles](../../Security/Accounts/IAM%20Roles.md) used for permissions
- Standard workflow
	- default
	- Maximum Duration - 1 year
- Express workflow
	- high volume event processing, eg streaming
	- Maximum Duration - 5 minutes
- Started via:
	- [API Gateway](API%20Gateway.md)
	- IOT Rules
	- [[EventBridge]]
	- [Lambda](Lambda.md)

Available states:
- SUCCEED & FAIL
- WAIT
- CHOICE - different set of behavior based on input
- PARALLEL - perform at same time
- MAP - accepts a list, performs action on them
- TASK - single unit of work performed by state machine
	- [Lambda](Lambda.md), Batch, [DynamoDB](../../Database/DynamoDB/DynamoDB.md), [ECS](../ECS/ECS.md), [SNS](../../Messages-Logs/SNS.md), [SQS](../../Messages-Logs/SQS.md), Glue, SageMaker, EMR, Step Functions

![Pasted image 20250429205151.png](_atts/Pasted%20image%2020250429205151.png)