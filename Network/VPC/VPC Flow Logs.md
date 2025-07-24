VPC Flow logs is a feature allowing the monitoring of traffic flow to and from interfaces within a [VPC](VPC.md).

VPC Flow logs can be added at a [VPC](VPC.md), Subnet or Interface level.

Flow Logs DON'T monitor packet contents, that requires a packet sniffer.

Flow Logs can be stored on [S3](../../Storage/S3/S3.md) or [CloudWatch Logs](../../Messages-Logs/CW/CloudWatch%20Logs.md).

[https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-s3.html](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-s3.html)

[https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-cwl.html](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-cwl.html)

- Captures metadata, not contents
- Can be attached to:
	- VPC - all ENIs in that VPC
	- Subnet - all ENIs in that subnet
	- ENIs directly
- **Not realtime**
- [Athena](../../Database/Athena.md) for querying

![Pasted image 20250522200947.png](_atts/Pasted%20image%2020250522200947.png)