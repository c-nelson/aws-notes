Global Tables provides multi-master global replication of [DynamoDB](DynamoDB.md) tables which can be used for performance, HA or DR/BC reasons.

- Tables are created in multiple regions then added to the same global table (becoming replica tables)
- Last write wins used for conflict resolution
- Read and Write can occur to any region
- Sub-second replication between regions
- Strongly [Consistency Model](Consistency%20Model.md) reads only in the same region as writes