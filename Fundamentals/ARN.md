Amazon Resource Name

All resources have a unique identifier

Format:
```
arn:partition:service:region:account-id:resource-id 
arn:partition:service:region:account-id:resource-type/resource-id 
arn:partition:service:region:account-id:resource-type:resource-id
```
Example: `arn:aws:s3:::koalacampaign19900000`

If a portion of the ARN is not needed to be specified, it can be skipped with double colons, `::`. In the example above, s3 is global so a region is not needed.

### Common issues

#AWSCommonTest 

```
arn:aws:s3:::catgifs    // access to the bucket
arn:aws:s3:::catgifs/*  // access to objects inside bucket
```

When referenced in an [identity policy](../Security/Accounts/Identity%20Policies.md), the first allows access to operations on the bucket itself and not the objects inside.

