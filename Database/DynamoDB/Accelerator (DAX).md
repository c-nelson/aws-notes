DynamoDB Accelerator (DAX) is an in-memory cache designed specifically for [DynamoDB](DynamoDB.md).

- Primary NODE (Writes) and Replicas (Read)
- Nodes are HA.. Primary failure = election
- In-Memory cache - 
- Much faster reads, reduced costs
- Scale UP and Scale OUT (Bigger or More)
- Supports write-through
- DAX Deployed WITHIN a VPC
## Tradition Cache vs DAX
![Pasted image 20250716211154.png](_atts/Pasted%20image%2020250716211154.png)

## Architecture
![Pasted image 20250716211526.png](_atts/Pasted%20image%2020250716211526.png)

