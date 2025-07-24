Local Secondary Indexes (LSI) and Global Secondary Indexes (GSI) allow for an alternative presentation of data stored in a [DynamoDB](DynamoDB.md) base table.

LSI allow for alternative SK's whereas with GSIs you can use alternative PK and SK.

- [Query](Operations.md#Query) is most efficient operation in DDB
- But can only work on 1 PK value at a time
- Indexes are alternative views on table data
- LSI allows different SK
- GSI allows different PK and SK
- On some or all attributes (projection)
- Recommended to use GSIs as default, LSI only when strong [Consistency Model](Consistency%20Model.md) is needed

## Local Secondary Indexes
- Must be created with the table
- 5 LSIs per base table
- Alternative SK on the table
- Shares the RCU and WCU with the main table
- Attributes - ALL, KEYS_ONLY, or INCLUDE

![Pasted image 20250716203402.png](_atts/Pasted%20image%2020250716203402.png)

## Global Secondary Indexes
- Can be created at any time
- Default limit of 20 per base table
- Alternative PK and SK
- GSIs have their own RCU and WCU allocations
- Attributes - ALL, KEYS_ONLY or INCLUDE
- Always Eventually [Consistency Model](Consistency%20Model.md)

![Pasted image 20250716203947.png](_atts/Pasted%20image%2020250716203947.png)

