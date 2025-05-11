3 ways [ELB](ELB.md) can handle SSL

## SSL Bridging
- Default for [ALB](ALB%20vs%20NLB.md#Application%20LB)
- Listener is configured for HTTPS
	- ELB unwraps the HTTP
- Connection is terminated on the ELB
- ELB needs a certificate for the domain name.
- ELB initiates a new SSL connection to backend instances
- Instances need SSL certificates and compute required for cryptographic operations

- Pros
	- ELB can see the HTTP and take actions on it
- Cons
	- Both ELB and [EC2](../../Compute/EC2/EC2.md) need SSL certs
	- Doubles cryptographic operations

## SSL Pass Through
- Used for [NLB](ALB%20vs%20NLB.md)
- Listener configured for TCP
- ELB just passes the encrypted text through to the instance
- Each instances needs to have SSL cert
- No cert exposed to AWS

## SSL Offloading
- ELB Listener is configured for HTTPS
- Connection is terminated
- Then backend connections use unencrypted HTTP
	- Data in plain text across [VPC](../VPC/VPC.md)
- No cert or crypto compute required on instances
