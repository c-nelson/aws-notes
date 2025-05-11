Kinesis data streams are a streaming service within AWS designed to ingest large quantities of data and allow access to that data for consumers.

Kinesis is ideal for dashboards and large scale real time analytics needs.

Kinesis data firehose allows the long term persistent storage of kinesis data onto services like [S3](../../Storage/S3/S3.md).

- Scalable streaming service
- Producers send data into a stream
- Streams can scale from to to near infinite data rates
- [Public](../../Fundamentals/Public%20vs%20Private%20Services.md) service & [highly available](../../Fundamentals/High%20Availability,%20Fault-Tolerance,%20and%20Disaster%20Recovery.md)
- Streams store a 24 hour moving window of data
	- Temporary storage included in service
	- Can be increased to a max of 365 days
- Multiple consumers can access data from that moving window

![Pasted image 20250508211244.png](_atts/Pasted%20image%2020250508211244.png)

## [SQS](../SQS.md) vs Kinesis
- SQS - 1 production group, 1 consumption group
	- Decoupling and asynchronous communications
	- No persistence of messages
- Kinesis designed for huge scale ingestion
	- Multiple consumers
	- Data ingestion, analytics, monitoring, app clicks
