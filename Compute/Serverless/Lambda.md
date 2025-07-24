- Functions as a Service
- Lambda function - piece of code lambda runs
- Specify a runtime (python, node, go)
- Functions loaded an run in a runtime environment
- The environment has a directory memory allocation
	- indirect CPU allocation
- Bill for duration of function runs

- Stateless
	- Assume every time a function runs it is in a new environment
- 128MB - 10240MB memory
- 512MB - 10240MB storage in `/tmp`
- 15 minute max runtime

![Pasted image 20250421203850.png](_atts/Pasted%20image%2020250421203850.png)

## Common uses
- Serverless Apps ([S3](../../Storage/S3/S3.md), [API Gateway](API%20Gateway.md), Lambda)
- File Processing (S3, S3 [Events](../../Storage/S3/Events.md), Lambda)
- Database Triggers ([DynamoDB](../../Database/DynamoDB/DynamoDB.md), Streams, Lambda)
- Serverless CRON ([[EventBridge]], [CW](../../Messages-Logs/CW/CW.md) Events, Lamdba)
- Realtime Stream Data Processing ([[Kinesis]], Lambda)


# Networking

## Public
![Pasted image 20250421204925.png](_atts/Pasted%20image%2020250421204925.png)

## Private VPC
![Pasted image 20250421205549.png](_atts/Pasted%20image%2020250421205549.png)

# Security
![Pasted image 20250421205925.png](_atts/Pasted%20image%2020250421205925.png)

# Logging
- Uses [CW](../../Messages-Logs/CW/CW.md), [CloudWatch Logs](../../Messages-Logs/CW/CloudWatch%20Logs.md) and [[X-Ray]]
- Logs from Lambda executions -> CloudWatchLogs
	- CloudWatch Logs requires permissions via Execution Role
- Metrics - invocation success/failure, retries, latency -> CloudWatch
- Can be integrated with X-Ray for distributed tracing

## Invocation
- Synchronous
![Pasted image 20250422221245.png](_atts/Pasted%20image%2020250422221245.png)

- Asynchronous
![Pasted image 20250422221711.png](_atts/Pasted%20image%2020250422221711.png)

- Event Source mappings
![Pasted image 20250422222230.png](_atts/Pasted%20image%2020250422222230.png)

## Version
- Lambda functions have versions - v1, v2, v3
- A version is the code + the configuration of the lambda function
- It's immutable - it never changes once published & has its own [ARN](../../Fundamentals/ARN.md)
- `$Latest` points at the latest version
- Aliases (DEV, STAGE, PROD) point at a version - can be changed

## Execution Context
![Pasted image 20250422223143.png](_atts/Pasted%20image%2020250422223143.png)