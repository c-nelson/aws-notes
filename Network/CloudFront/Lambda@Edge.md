- Allows you to run lightweight [Lambda](../../Compute/Serverless/Lambda.md) at [CF](CF.md) edge locations
- Can adjust data between Viewer & Origin traffic
- Limitations:
	- Limited to Node.js and Python
	- Run in the AWS Public Space not VPC
	- Layers are not supported
	- Different limits vs normal lambda functions

![Pasted image 20250521202255.png](_atts/Pasted%20image%2020250521202255.png)

## Common use cases
[https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-examples.html#lambda-examples-redirecting-examples](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-examples.html#lambda-examples-redirecting-examples)

- A/B testing - Viewer Request
- Migration Between [S3 origins](Origin%20Types.md) - Origin Request
- Different objects based on device - Origin Request
- Content by country - Origin Request