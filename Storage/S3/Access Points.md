[S3](S3.md) Access Points, a feature of S3, simplifies managing data access at scale for applications using shared data sets on S3. Access points are unique hostnames that customers create to enforce distinct permissions and network controls for any request made through the access point.

https://docs.aws.amazon.com/AmazonS3/latest/dev/creating-access-points.html#access-points-policies

- Simplify managing access for different use cases
- Rather than 1 bucket with 1 bucket policy
	- Create many access points
	- With different policies
	- Can have different network access controls
- Each has its own endpoint address
- Created via console
- #AWSCommonTest or [CLI](../../Misc/CLI.md) `aws s3control create-access-point --name secretcats --account-id 123456789 --bucet catpics`
- Each access point has a unique DNS address
- Common to create access points tiered for more granular control

![Pasted image 20250217132948.png](_atts/Pasted%20image%2020250217132948.png)

## Multi-region access points
[S3](S3.md) Multi-Region Access Points provide a global endpoint for routing S3 request traffic between Regions. Each global endpoint routes S3 data request traffic from multiple sources, including traffic originating in [VPC](../../Network/VPC/VPC.md)s, from on-premises data centers over AWS PrivateLink, and from the public internet without building complex networking configurations with separate endpoints.
- Data gets routed to closest bucket region
- Set up [replication](Replication.md) to sync data