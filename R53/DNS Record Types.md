## Nameserver (NS)

How delegation works in DNS

![Pasted image 20250128213614.png](_atts/Pasted%20image%2020250128213614.png)

## A and AAAA
Map host names to IPs

![Pasted image 20250128213806.png](_atts/Pasted%20image%2020250128213806.png)

## CNAME
Conical Name

DNS Shortcuts, Host to Host

![Pasted image 20250128214032.png](_atts/Pasted%20image%2020250128214032.png)

CNAMES cannot point to other IPs, only names. #AWSCommonTest 

## MX

How a server can find the mail server for a specific domain. MX records are given priorities.

![Pasted image 20250128214529.png](_atts/Pasted%20image%2020250128214529.png)

## TXT

Allow arbitrary text to a domain.

For example, to prove ownership.

![Pasted image 20250128214737.png](_atts/Pasted%20image%2020250128214737.png)

# DNS TTL - Time to Live
Indicates how long records can be cached for.

In the example below, amazon.com is cached on the resolver server for all clients for 3600 seconds, short circuiting the need to go to the authoritative service.

![Pasted image 20250128215219.png](_atts/Pasted%20image%2020250128215219.png)

