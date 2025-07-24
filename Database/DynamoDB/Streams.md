[DynamoDB](DynamoDB.md) Streams are a 24 hour rolling window of time ordered changes to ITEMS in a DynamoDB table

- Streams have to be enabled on a per table basis
- Records INSERTS, UPDATES and DELETES
- Different view types include what is in the stream
- 4 view types:
	- KEYS_ONLY
	- NEW_IMAGE
	- OLD_IMAGE
	- NEW_AND_OLD_IMAGES
- [Lambda](../../Compute/Serverless/Lambda.md) can be integrated to provide trigger functionality - invoking when new entries are added on the stream.

![Pasted image 20250716205836.png](_atts/Pasted%20image%2020250716205836.png)

## Triggers
- ITEM changes generate an event
- That event contains the data which changed
- Action is taken using that data using Lambda
- Useful for 
	- Reporting & Analytics
	- Aggregation, Messaging or Notifications

![Pasted image 20250716210249.png](_atts/Pasted%20image%2020250716210249.png)