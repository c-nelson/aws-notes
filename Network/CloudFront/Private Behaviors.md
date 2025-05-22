![Pasted image 20250520205800.png](_atts/Pasted%20image%2020250520205800.png)

Architecture of a private [CF](CF.md) distribution:
- Requests require signed cookie or URL
- 1 Behavior
	- the whole Distribution is Public or Private
- Multiple Behaviors
	- parts are public and parts are private
- Legacy method:
	- a cloudfront key is created by an account root user
	- the account is added as a TRUSTED SIGNER
- Recommended method:
	- TRUSTED KEY GROUPS
	- Can be managed by CF API

## Signed URLs vs Signed Cookies

Signed URLs
- Signed URLs provides access to *one object*
- Use URLs if you client doesn't support cookies

Signed Cookies
- Cookies provides access to groups of objects
- Use for groups of files
- Or if maintaining application URLs is important