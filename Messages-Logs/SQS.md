SQS queues are a managed message queue service in AWS which help to decouple application components, allow Asynchronous messaging or the implementation of worker pools.

- Public
- Fully Managed
- Highly-available Queues
- Standard - best efforts order
- FIFO - guarantee an order

- Messages up to 256KB
	- Link to larger data if needed
- Received messages are hidden (VisibilityTimeout)
	- If a client doesn't explicitly delete a message after processing, there is a timeout after which it will then be put back into queue
- Dead-Letter queues can be used for problem messages
	- Example, if a message failed processing 5 times

- [ASGs](../Network/ELB/ASG%20+%20Load%20Balancers.md) can scale and [Lambda](../Compute/Serverless/Lambda.md)s invoked based on queue length

- Billed based on 'requests'
	- Not the same as a message
	- Requests from a client/worker
	- 1 request - 1-10 messages up to 64KB total
- Short (immediate) Polling
	- Uses 1 request
	- Can receive 0 or more messages
	- If there are no messages it still consumes a request
- Long (waitTimeSeconds) Polling
	- Up to 20 seconds
	- If messages are there they will be returned
	- Otherwise if no messages, it will wait for up to 10 messages

- Messages are encrypted at rest ([KMS](../Security/KMS/KMS.md)) & in-transit
- Queue policies are used just like resource policies

![Pasted image 20250508201943.png](_atts/Pasted%20image%2020250508201943.png)

## SQS Fanout Architecture
#AWSCommonTest 
![Pasted image 20250508202257.png](_atts/Pasted%20image%2020250508202257.png)

## Standard vs FIFO
- Standard - at least once delivery
	- Multilane highway
	- Could get the same message twice
	- Scalable
- FIFO - in order, exactly once
	- Single lane
	- Guarantees order and message sent only once
	- 3000 messages per second with batching
	- Up to 300 messages per second without

![Pasted image 20250508204017.png](_atts/Pasted%20image%2020250508204017.png)

## Delay Queues
Delay queues provide an initial period of invisibility for messages. Predefine periods can ensure that processing of messages doesn't begin until this period has expired.

Visibility Timeout vs Delay Queues
![Pasted image 20250508204919.png](_atts/Pasted%20image%2020250508204919.png)

## Dead Letter Queues
Dead letter queues allow for messages which are causing repeated processing errors to be moved into a dead letter queue. In this queue, different processing methods, diagnostic methods or logging methods can be used to identity message faults.

![Pasted image 20250508205633.png](_atts/Pasted%20image%2020250508205633.png)