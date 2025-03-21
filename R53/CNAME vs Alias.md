#### The Problem
- ["A"](DNS%20Record%20Types.md#A%20and%20AAAA) maps a NAME to an IP Address
	- `catagram.com => 1.3.3.7`
- [CNAME](DNS%20Record%20Types.md#CNAME) maps a NAME to another NAME
	- `www.catagram.io => catagram.io`
- CNAME is invalid for naked/apex (catagram.io)
- Many AWS services use a DNS Name ([[ELB]]s)
- With CNAME: `catagram.io => ELB` would be invalid

## CNAME
CNAME works when you want to point a NAME, that is not the naked domain, to another NAME.

## Alias
- ALIAS records map a NAME to an AWS resource
- Can be used for naked and normal records
- For non naked - functions like CNAME
- There is no charge for ALIAS requests pointing at AWS resources
- For AWS Service - default to picking ALIAS
- Can have both [A](DNS%20Record%20Types.md#A%20and%20AAAA) type records or [CNAME](DNS%20Record%20Types.md#CNAME) record aliases
	- Should match what the record points to
- Use for:
	- [[API Gateway]]
	- [[CloudFront]]
	- [[Elastic Beanstalk]]
	- [[ELB]]
	- [[Global Accelerator]]
	- [S3](../S3/S3.md)
	- 