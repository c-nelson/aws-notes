AWS WAF is a web [Application Layer Firewalls](Application%20Layer%20Firewalls.md) that helps protect your web applications or APIs against common web exploits and bots that may affect availability, compromise security, or consume excessive resources.

![Pasted image 20250621222442.png](_atts/Pasted%20image%2020250621222442.png)

## Web Access Control Lists (WEBACL)
WEBACL is the main unit of configuration within WAF. WEBACLs control if traffic is allowed or blocked.
- WEBACL default action can be ALLOW or BLOCK
- They are created for:
	- [CF](../../Network/CloudFront/CF.md) - global services
	- Regional Services - [ALB](../../Network/ELB/ALB%20vs%20NLB.md), [API Gateway](../../Compute/Serverless/API%20Gateway.md), [[AppSync]]
- Add Rule Groups or Rules which are processed in order
- Web ACL Capacity Units (WCU) - Default 1500
	- Compute requirements rules can use to filter
	- Can be increased with support ticket
- WEBACL's are associated with resources (can take time)
	- Adjusting a WEBACL takes less time than associating one

## Rule Groups
- Contain rules
- They don't have default actions - that's defined when groups or rules are added to WEBACLS
- Can be Managed (AWS or Marketplace), Yours, or Service Owned (i.e [Shield](Shield.md) & Firewall Manager)
- Rule groups can be referenced by multiple WEBACLs
- Have a WCU capacity (defined upfront, max 1500)

## Rules
- Contains:
	- Type - how the rule works
		- Regular - match if something occurs
			- Ex allow an IP to connect via SSH
		- Rate-based - match if something occurs at a certain rate
			- Ex if someone tries to connect to SSH 5000x
	- Statement - matches traffic
		- WHAT to match
		- COUNT
		- WHAT & COUNT
		- Match against origin county, IP, label, header, cookies, query parameter, URI path, query string, body (first 8192 bytes only), HTTP method
		- A rule can have multiple statements and use AND, OR, NOT
	- Action - what WAF does when matches occur
		- Allow
			- Response can be custom header prefixed with (x-amzn-waf-) so that application can react
		- Block
			- Response can be custom response or custom header
		- Count
			- Response can be custom header
		- Captcha
			- Response can be custom header
		- Labels can be added to any action
			- Can be referenced later in the same WEBACL for multi-stage flows
		- ALLOW & BLOCK stop processing, Count/Captcha actions continue (where labels can be used)

## Pricing
- WEBACL - Monthly ($5 / month*)
- RULE on WEBACL - monthly ($1 / month*)
- REQUESTS per WEBACL - Monthly ($0.60 / 1 million requests*)
- Intelligent Threat Mitigation
	- Bot Control ($10/month*) & ($1/1mil requests*)
	- Captcha ($0.40 /100 challenge attempts)
	- Fraud Control/Account Takeover ($10/month* & $1/100 login attempts)
- Marketplace Rule Groups - extra costs

[https://calculator.aws/#/](https://calculator.aws/#/)