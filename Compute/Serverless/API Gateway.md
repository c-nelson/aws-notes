API Gateway is a managed service from AWS which allows the creation of API Endpoints, Resources & Methods.

The API gateway integrates with other AWS services and can even access some without the need for dedicated compute.

It serves as a core component of many serverless architectures using [Lambda](Lambda.md) as event-driven and on-demand backing for methods.

It can also connect to legacy monolithic applications and act as a stable API endpoint during an evolution from a monolith to microservices and potentially through to serverless.

- Create and manage APIs
- Sits between applications & integrations/services
- Highly available, scalable, 
- Handles authorization, throttling, caching, CORS, transformations 
- OpenAPI spec
- Direct integration with other services
- Can connect to services/endpoints in AWS or on-premises
- HTTP APIs, REST APIs, or Websocket APIs

![Pasted image 20250429211751.png](_atts/Pasted%20image%2020250429211751.png)

## Authentication
Examples using [Cognito](../../Security/Cognito.md) or [Lambda](Lambda.md)
![Pasted image 20250429212354.png](_atts/Pasted%20image%2020250429212354.png)

## Endpoint Types
- Edge-Optimized
	- Routed to nearest [[CloudFront]] POP
- Regional
	- Clients in the same region
- Private
	- Endpoint accessible only within a [VPC](../../Network/VPC/VPC.md) via interface endpoint

## Stages
![Pasted image 20250429212858.png](_atts/Pasted%20image%2020250429212858.png)
Canary deployment can be used to slowly redirect more and more traffic to a new version so it can be adequately tested.

## Errors
Uses standard REST response error codes
- 4XX - Client Error - invalid request
- 5XX - Server Error - backend issue
- 400 - Bad Request - Generic
- 403 - Access Denied
- 429 - API Gateway throttle exceeded
- 502 - Bad Gateway - bad output returned by [Lambda](Lambda.md) for example
- 503 - Service Unavailable
- 504 - Integration Failure/Timeout - 29s limit

## Caching
![Pasted image 20250429213626.png](_atts/Pasted%20image%2020250429213626.png)