- Each [CF](CF.md) Distribution gets a Default Domain Name (CNAME)
- `https://d1111abcdef8.cloudfront.net`
- SSL supported by default at `cloudfront.net` cert
- **Alternate Domain Names** feature used form custom domain names
- Verify Ownership (optionally HTTPS) using a matching certificate
- Generate or import in [ACM](../ACM.md), in **us-east-1** because CF is global
- HTTP options:
	- HTTP or HTTPS 
	- HTTP redirects to HTTPS
	- HTTPS Only
- CF uses two SSL Connections:
	- Viewer => CF
	- CF => Origin
- Both need valid public certificates (and intermediate certs)

![Pasted image 20250515214911.png](_atts/Pasted%20image%2020250515214911.png)
## SNI
- Historically every SSL enabled site needed its own IP
- Encryption starts at the TCP layer and host headers ares on the HTTP layer
	- Host headers specify which application on a server
	- Therefore a server couldn't host multiple HTTPS servers
- SNI is a TLS extension, allowing host to be included
	- Allows for many SSL certs/hots using a shared

- Older browsers don't support SNI
- SNI mode is free with CF
- CF charges extra fro dedicated IPs

