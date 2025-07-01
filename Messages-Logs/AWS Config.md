AWS Config is a service which records the configuration of resources over time (configuration items) into configuration histories.

All the information is stored regionally in an [S3](../Storage/S3/S3.md) config bucket.

AWS Config is capable of checking for compliance and generating notifications and events based on compliance.

- Does not prevent changes from happening
- Changes can generate [SNS](SNS.md) notifications and near-realtime events via [EventBridge](CW/CloudWatch%20Events%20&%20EventBridge.md) & [Lambda](../Compute/Serverless/Lambda.md)

![Pasted image 20250630213430.png](_atts/Pasted%20image%2020250630213430.png)