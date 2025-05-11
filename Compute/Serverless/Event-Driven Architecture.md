Problems with Tier Architecture 
![Pasted image 20250420212207.png](_atts/Pasted%20image%2020250420212207.png)

With queues instead, asynchronous:
![Pasted image 20250420212933.png](_atts/Pasted%20image%2020250420212933.png)

Event Driven:
![Pasted image 20250420213556.png](_atts/Pasted%20image%2020250420213556.png)

- no constant running or waiting
- producers generate events when events happens
- events are delivered to consumers
	- actions are taken & system returns to waiting
- mature event-driven architecture only consumes resources while handling events (serverless)