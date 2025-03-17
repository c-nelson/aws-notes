Service Type: [Regional](../Fundamentals/Resilience.md#Region)

Logs API calls and account events.

Examples of logs: Stopping an instance, create/delete S3 buckets.

Almost everything that can be done in AWS gets logged.

It's very often used to diagnose security or performance issues, or to provide quality account level traceability.

It is enabled by default in AWS accounts and logs free information with a 90 day retention.

3 types of Events:
- Management Events
- Data Events
- Insight Events

## Management Events
The only event logs enabled by default.

Provide information on management events of services, like creating an [EC2](../EC2/EC2.md), stopping, deleting, creating a [VPC](../VPC/VPC.md) etc.

## Data Events
Not enabled by default.

Information about resource operations performed on or in a resource. Like objects being uploaded or accessed via [S3](../S3/S3.md), or a [Lambda](../Lambda/Lambda.md) function being invoked.

## Insight Events


## Trails
Customized CloudTrail Events. They way you provide configurations for how CloudTrail operates and logs.

![Pasted image 20250209130528.png](_atts/Pasted%20image%2020250209130528.png)

Unlike a default CloudTrail, a custom trail can be configured to store data indefinitely in S3 or CloudWatch Logs. They are stored as a compressed JSON.

Can also be integrated with [CloudWatch Logs](CloudWatch%20Logs.md) and the data stored there. Making the logs have more features such as being able to search and filter.

Trails can be created at an [Organizations](../Accounts/Organizations.md) level, meaning the logs can be stored for all accounts. 

A trail is only created for a single region, it only logs for that region.

Although trail can be configured
- to a single region
- to all regions
	- the trail is copied to every region but managed as one trail
	- benefit is that if a new region is added, it automatically gets added to the trail

Global Service Events always log to Northern Virginia region.

#AWSCommonTest AWS contains many global and regional services. With CloudTrail they either log to the region the service is located in or us-east-1.

If you want to log things like [IAM](../Accounts/IAM.md), [STS](../Misc/STS.md), and [[CloudFront]], all regions will need to be enabled on a customized trail.

#AWSCommonTest CloudTrail is not realtime, there is a delay. Typically, within 15 minutes of an event.

## Pricing
[https://aws.amazon.com/cloudtrail/pricing/](https://aws.amazon.com/cloudtrail/pricing/)




