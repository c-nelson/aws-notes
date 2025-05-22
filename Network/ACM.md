The AWS certificate Manage is a service which allows the creation, management and renewal of certificates. It allows deployment of certificates onto supported AWS services such as [CloudFront](CloudFront/CF.md) and [ALB](ELB/ALB%20vs%20NLB.md).

- Can generate or import certificates
- If generated, can automatically renew
- Certificates can be deployed out to supported services
	- Eg CloudFront, ALBs but not EC2
- ACM is a regional service
- Certs cannot leave the region they are generated or imported in
- To use a cert with an ALB in us-west-1 you need a cert in ACM in us-west-1
- Global service such as [CF](CloudFront/CF.md) operate as though within us-east-1

![Pasted image 20250513210444.png](_atts/Pasted%20image%2020250513210444.png)