CloudWatch Events and EventBridge have visibility over events generated by services.

EventBridge is the successor to CloudWatch Events that can handle events from third parties or custom apps.

They can monitor the default account event bus  and pattern match events flowing through and deliver these events to multiple targets.

They are also the source of scheduled events which can perform certain actions at certain times of day, days of the week, or multiple combinations of both, using the Unix CRON time expression format.

They are a way for [Event-Driven Architecture](../../Compute/Serverless/Event-Driven%20Architecture.md) to be implemented.

- Messages are piped through the default event bus for the account
	- CloudWatch Event this is the only bus
	- EventBridge can have additional event busses
- Route the events to targets, e.g [Lambda](../../Compute/Serverless/Lambda.md)
- Events are in JSON

![Pasted image 20250424204912.png](_atts/Pasted%20image%2020250424204912.png)

