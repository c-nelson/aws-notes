Amazon [DynamoDB](DynamoDB.md) Time to Live (TTL) allows you to define a per-item timestamp to determine when an item is no longer needed. 

Shortly after the date and time of the specified timestamp, DynamoDB deletes the item from your table without consuming any write throughput. 

TTL is provided at no extra cost as a means to reduce stored data volumes by retaining only the items that remain current for your workload’s needs

![Pasted image 20250716212513.png](_atts/Pasted%20image%2020250716212513.png)