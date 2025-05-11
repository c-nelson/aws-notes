The Simple Notification Service is a PUB SUB style notification system which is used within AWS products and services but can also form an essential part of serverless, event-driven and traditional application architectures.

Publishers send messages to TOPICS

Subscribers receive messages SENT to TOPICS.

SNS supports a wide variety of subscriber types including other AWS services such as [Lambda](../Compute/Serverless/Lambda.md) and [SQS](SQS.md).

- [Public](../Fundamentals/Public%20vs%20Private%20Services.md) AWS Service - network connectivity with public endpoint
- Coordinates the sending and delivery of messages
- Messages are <= 256KB payloads
- SNS Topics are the base entity of SNS - permissions and configuration
- A Publisher sends messages to a TOPIC
- TOPICS have Subscribers which receive messages
	- HTTP, EMAIL, SQS, Mobile Push, SMS messages, Lambda
- Used all across AWS for notifications

![Pasted image 20250427213855.png](_atts/Pasted%20image%2020250427213855.png)


Supports:
- Delivery Status
- Delivery Retries
- HA and Scalable (Region)
- Server Side Encryption
- Cross-Account via TOPIC Policy