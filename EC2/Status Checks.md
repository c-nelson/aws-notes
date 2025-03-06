With instance status monitoring, you can quickly determine whether [EC2](EC2.md) has detected any problems that might prevent your instances from running applications. EC2 performs automated checks on every running EC2 instance to identify hardware and software issues. You can view the results of these status checks to identify specific and detectable problems.

- Each instances has 2 status checks
	- System Status
		- Loss of power
		- loss of network
		- Host software issues
		- Host hardware issues
	- Instance Status
		- Corrupt files
		- Incorrect instance networking
		- Kernel issues
- Can be set to stop/restart/terminate on status failure
- Or set to auto recovery
# Auto Recovery
[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-recover.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-recover.html)

When an instance is set to auto recover, it performs the following through [Cloud Watch](../Logs/CW.md):
- Moves an instance to a new host
- Starts it with the same configuration
	- Same instance ID
	- IPs
	- and metadata

- Only works with newer instances
- Doesn't work with instances with [Instance Store](Instance%20Store.md), only [EBS](../EBS/EBS.md)
- Relies on there being capacity in the AZ

## Termination Protection
Termination Protection is a feature which adds an attribute to [EC2](EC2.md) instances meaning they cannot be terminated while the flag is enabled.

It provides protection against unintended termination and also allows role separation, where junior admins can be allowed to terminate but ONLY for instances with no protection attribute set.