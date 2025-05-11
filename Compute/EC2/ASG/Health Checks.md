[Auto Scaling Groups](Auto%20Scaling%20Groups.md) can determine the health status of an instance using one or more of the following:

- Status checks provided by [EC2](../EC2.md) to identify hardware and software issues that may impair an instance. The default health checks for an Auto Scaling group are EC2 status checks only.
- Health checks provided by [ELB](../../../Network/ELB/ELB.md). These health checks are disabled by default but can be enabled.
- Your custom health checks

- Health check grace period (Default 300s) delay before starting checks
	- Allows system/app launch