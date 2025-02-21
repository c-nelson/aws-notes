https://aws.amazon.com/about-aws/global-infrastructure/regions_az/
## AWS Regions
Full deployment of all AWS services to a location.

Benefits:
- Geographic Separation
- Geopolitical Separation
- Location Control - performance

Some services are global like [[IAM]], or [[Route 53]]. While mosts others like [[EC2]] or tied to a region.

### Availability Zones
Within a Region there are multiple availability zones which are isolated.
![[Pasted image 20250121212626.png]]

## AWS Edge Locations
Smaller, Local Distribution Points

Generally only have content distribution systems and some type of edge computing. Allows low latency.

## Service Resilience
- Global
	- Operates globally in every location
	- IAM
	- Route 53
- Region
	- Operate in a single region with one set of data per region
	- RDS database
	- EC2
- AZ (Availability Zone)
	- Operate from a single "datacenter".

