# Gateway Endpoints
Gateway endpoints are a type of [VPC](VPC.md) endpoint which allow access to [S3](../../Storage/S3/S3.md) and [[DynamoDB]] without using public addressing.

Gateway endpoints add 'prefix lists' to route table, allowing the VPC [router](Routing%20&%20Internet%20Gateway.md) to direct traffic flow to the public services via the gateway endpoint.

- Highly Available across all AZs in a region by default
- Endpoint policy is used to control what it can access
- Regional - can't access cross-region services
- Helps prevent leaky buckers - S3 buckets can be set to private only by allowing access only from a gateway endpoint

#### Without Gateway Endpoints
![Pasted image 20250528202417.png](_atts/Pasted%20image%2020250528202417.png)

#### With Gateway Endpoints
![Pasted image 20250528202633.png](_atts/Pasted%20image%2020250528202633.png)

# Interface Endpoints
Interface endpoints are used to allow private IP addressing to access public AWS services.

S3 and DynamoDB are handled by Gateway Endpoints - other supported services are handled by interface endpoints.

- Added to specific subnets - an ENI
	- NOT Highly Available by default
	- For HA, add one endpoint to one subbet per AZ used in the VPC
- Network access controlled via [Security Groups](Security%20Groups.md)
- Endpoint policies - restrict what can bee done with the endpoint
- TCP and IPv4 only
- Uses PrivateLink
- Endpoint provides a NEW service endpoint DNS
	- e.g `vpce-123-xyz.sns.us-east-1.vpce.amazonaws.com`
	- Gets both a endpoint for regional and zonal DNS
	- Applications can use either
	- PrivateDNS overrides the default DNS for services

#### Without Interface Endpoints
![Pasted image 20250528203804.png](_atts/Pasted%20image%2020250528203804.png)

#### With Interface Endpoints
![Pasted image 20250528203926.png](_atts/Pasted%20image%2020250528203926.png)

#### With Interface Endpoints & PrivateDNS
![Pasted image 20250528204035.png](_atts/Pasted%20image%2020250528204035.png)