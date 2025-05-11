An _Auto Scaling group_ contains a collection of [EC2](../EC2.md) instances that are treated as a logical grouping for the purposes of automatic scaling and management. 

An Auto Scaling group also enables you to use [EC2](../EC2.md) Auto Scaling features such as health [Status Checks](../Status%20Checks.md) replacements and [Scaling](../Scaling.md) policies. 

Core Functionality:
	- Self-healing
	- Automatic scaling
- Uses [Launch Configurations & Templates](../Launch%20Configurations%20&%20Templates.md)
- Has a minimum, desired, and maximum size (1:2:4)
- Keep running instances at the desired capacity by provisioning or terminating instances
- [Scaling Policies](Scaling%20Policies.md) automate based on metrics

![Pasted image 20250412220200.png](_atts/Pasted%20image%2020250412220200.png)

## [Types of Scaling](Scaling%20Policies.md)
- Manual - adjust the desired capacity
- Scheduled - time based adjustment, eg sales
- Dynamic
	- Simple
		- Simple metric conditions
		- ex, "CPU above 50% +1, CPU Below 50% -1"
	- Stepped
		- Bigger +/- based on difference
		- ex, >50% add 1, >80% add 3
	- Target Tracking
		- ex, Desired aggregate CPU = 40%
- Cooldown Periods - how long to wait before performing another scaling operation

## Scaling Processes
- `Launch` and `Terminate`
	- Suspend and Resume
- `AddToLoadBalancer` - add to [Load Balancer](../../../Network/ELB/ASG%20+%20Load%20Balancers.md) on launch
- `AlarmNotification` - from [CW](../../../Messages-Logs/CW/CW.md)
- `AZRebalance` - even across all of the AZs
- `HealthCheck` - checks on/off
- `ReplaceUnhealthy` - replace unhealthy
- `ScheduleActions` - schedule on/off
- `Standby` - suspend auto scaling for specific instance, 'InService vs Standby'

## Key points
- Autoscaling Groups are free
- Only the resources created are billed
- Use cooldowns to avoid rapid scaling
- Think about more, smaller instances - granularity
- Uses ALB's for elasticity - abstraction
- AGS defines WHEN and WHERE, [LT](../Launch%20Configurations%20&%20Templates.md) defines WHAT