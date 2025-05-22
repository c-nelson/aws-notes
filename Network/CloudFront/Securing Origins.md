# Origin Access Identities

Only applicable to [S3 Origins](Origin%20Types.md).

Origin Access Identities are a feature where virtual identities can be created, associated with a [CF](CF.md) Distribution and deployed to edge locations.

Access to an [S3](../../Storage/S3/S3.md) bucket can be controlled by using these OAI's - allowing access from an OAI, and using an implicit DENY for everything else.

They are generally used to ensure no direct access to S3 objects is allowed when using private CF Distributions.

![Pasted image 20250520202036.png](_atts/Pasted%20image%2020250520202036.png)

# Custom Origins

Two was to implement secure origins:
## Custom Headers

Custom headers are injected from the edge location, the custom origin server then verifies the header.

## Firewall

AWS publishes all CloudFront IP ranges, therefore the server can block any other access with a firewall.

![Pasted image 20250520202658.png](_atts/Pasted%20image%2020250520202658.png)