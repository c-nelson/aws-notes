CreationPolicy, WaitConditions and cfn-signal can all be used together to prevent the status if a resource from reaching create complete until AWS CloudFormation receives a specified number of success signals or the timeout period is exceeded.The [cfn-signal](cfn-init.md#CFN-SIGNAL) helper script signals AWS CloudFormation to indicate whether Amazon EC2 instances have been successfully created or updated.

- Configure [CloudFormation](CloudFormation.md) to wait for X number of success signals
- Wait for timeout for those signals (12 hours max)
- If success signals received continue - CREATE_COMPLETE
- If failure signal received - stack fails
- If timeout is reached - stack fails

## CreatePolicy
![Pasted image 20250709211717.png](_atts/Pasted%20image%2020250709211717.png)

## WaitCondition
![Pasted image 20250709212017.png](_atts/Pasted%20image%2020250709212017.png)