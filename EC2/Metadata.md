[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html)

[https://aws.amazon.com/code/ec2-instance-metadata-query-tool/](https://aws.amazon.com/code/ec2-instance-metadata-query-tool/)

[EC2](EC2.md) instance metadata is data about your instance that you can use to configure or manage the running instance. Instance metadata is divided into categories, for example, host name, events, and security groups.

- Accessible inside all instances
	- http://169.254.169.254/latest/meta-data #AWSCommonTest
- Allows anything running on the instance to access things about the instance like
	- environment 
	- networking
	- authentication
	- user-data
- The meta data service has no authentication and is not encrypted #AWSCommonTest 
	- Anyone with console access can use it