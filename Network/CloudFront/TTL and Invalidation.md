How [CF](CF.md) objects TTL works, example shows an image version being updated. It won't get through to the edge location until TTL expires.

![Pasted image 20250513203345.png](_atts/Pasted%20image%2020250513203345.png)

- Default TTL ([Behaviors](Behaviors.md)) = 24 hours (validity period)
- You can set Minimum TTL and Maximum TTL values
	- Limit the per object settings set by the following headers
	- Origin Header: `Cache-Control max-age` (seconds)
	- Origin Header: `Cache-Control s-maxage` (seconds)
	- Origin Header: `Expires` (Date & Time)
- Custom Origin or [S3](../../Storage/S3/S3.md) via object metadata

## Invalidations
- Cache invalidation immediately expires any object
- Cache invalidation performed on a distribution
- Applies to all edge locations - takes time
- Ex:
	- `/images/image.jpg`
	- `/images/image*`
	- `/images/*`
	- `/*` - everything
- Costs associated with invalidation
	- Should only really be used for errors
	- More cost effective to use versioning in file names