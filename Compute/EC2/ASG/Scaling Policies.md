- [ASGs](Auto%20Scaling%20Groups.md) don't have to have a scaling policy - they can have none
- Manual - Min, max & desired

## Dynamic Scaling
- Simple Scaling - when a [CW](../../../Messages-Logs/CW/CW.md) alarm goes into an alarm state
  
- Step Scaling - varying scaling based on alarm severity
![Pasted image 20250415202834.png](_atts/Pasted%20image%2020250415202834.png)

- Target Tracking - scales keeping a metric at the value you want, ex 50% CPU usage
  
- Scaling based on [SQS](../../../Messages-Logs/SQS.md) - ApproximateNumberOfMessagesVisible