CloudWatch

Provides metric, log and event management services

- Collects and manages operational data
- Metrics - AWS Products, Apps, on-premises
	- Time Ordered Set of Data points
		- CPU Usage
		- Network IO
		- Disk IO
- CloudWatch Logs - AWS Products, Apps, on-premises
- CloudWatch Events - AWS Services & Schedules

![Pasted image 20250128195412.png](Pasted%20image%2020250128195412.png)

## CW Concepts
- Namespace
	- All AWS data goes into a predefined namespaces `AWS/service` ex `AWS/EC2`
	- Custom namespaces can't contain backslashes
- Datapoint - a single metric
	- Timestamp
	- Value
- Dimension - separate datapoints for different things or perspectives within the same metric
	- Name = InstanceID, Value = someID
	- Name = InstanceType, Value = t2.micro
- Alarms - linked to a metric to create events
	- Has **OK** & **Alarm** states
