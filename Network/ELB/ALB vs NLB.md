Differences between types of [ELB](ELB.md).
## Classic LB vs Application LB
![Pasted image 20250412205720.png](_atts/Pasted%20image%2020250412205720.png)

## Application LB
- Layer 7 Load balancer, listens on HTTP/S
- Can't understand other Layer 7 protocols (SMTP, SSH, Gaming..)
	- No TCP/UDP/TLS Listeners
- Can inspect L7 content types: 
	- cookies
	- custom headers
	- user location
	- app behavior
- HTTP/S always terminated on the ALB, no unbroken SSL
	- A new connection made from LB to the app
- ALBs MUST have SSL certs if HTTPS is used
- ALBs are slower than NLB, more levels of the network stack to process
- Health check evaluate application health
- **Rules** - direct connections which arrive at a listener
	- Processed in priority order
	- Default rule - catchall
	- Rule Conditions
		- host-header
		- http-header
		- http-request-method
		- path-pattern
		- query-string
		- source-ip
	- Actions:
		- forward
		- redirect
		- fixed-response
		- authenticate-oidc
		- authenticate-cognito

![Pasted image 20250412211235.png](_atts/Pasted%20image%2020250412211235.png)

## Network LB
- Layer 4 load balancer:
	- TCP
	- TLS
	- UDP
	- TCP_UDP
- No visibility or understanding of HTTP/S
	- No headers, cookies or session stickiness
- Really fast, millions of rps, 25% of ALB latency
- SMTP, SSH, Game servers, financial apps
- Health checks just check ICMP/TCP Handshake, not app aware
- NLBs can have static IPS, useful for whitelisting
- Can Forward TCP to instance, unbroken encryption
- Used with private link to provide servers to other [VPC](../VPC/VPC.md)s

