Operations in [DynamoDB](DynamoDB.md)

## Reading and Writing
- Modes:
- **On-Demand** - unknown, unpredictable load, or need low admin
	- Price per million R or W units
	- Much more expensive
- **Provisioned** - RCU and WCU set on a per table basis
	- Every operation consumes at least 1 RCU/WCU*
	- 1 RCU is 1 x 4KB read operation per second
	- 1 WCU is 1 x 1KB write operation per second
	- Every table has a RCU and WCU burst pool (300 seconds)
#### Query
Must query by PK/SK
![Pasted image 20250715212636.png](_atts/Pasted%20image%2020250715212636.png)

### Scan
More flexible, less efficient. Needs to step through and consume the entire table.
![Pasted image 20250715213241.png](_atts/Pasted%20image%2020250715213241.png)


#### Details of RCU and WCU consumption
[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughput.html#ItemSizeCalculations.Writes](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughput.html#ItemSizeCalculations.Writes)