Presigned URL's are a feature of [S3](S3.md) which allows the system to generate a URL with access permissions encoded into it, for a specific bucket and object, valid for a certain time period.

Often used with media is offloaded to S3 or in serverless architecture.

![Pasted image 20250216171638.png](_atts/Pasted%20image%2020250216171638.png)

#AWSCommonTest
- Can be used for GETS or PUTS
- You can create a URL of an object you have no access to
	- Because it is linked to your identity, the URL won't have access
- When using the URL, the permissions match the identity which generated it
- Don't generate with a [role](../Accounts/IAM%20Roles.md), the URL stops working when the role credentials expire, which is typically before the URL expires

## Traditional App Architecture With [S3](S3.md) Media Files
1) User makes request to [EC2](../EC2/EC2.md) server and the request contains media from S3
2) Server has an [IAM Users](../Accounts/IAM%20Users.md) associated with it
3) Server requests a presigned URL to the S3 object
4) The app then uses the presigned URL within html

![Pasted image 20250216172648.png](_atts/Pasted%20image%2020250216172648.png)

## How to Generate

Using [CLI](../CLI.md):
`aws s3 presign {objects-s3-uri} --expires-in {num-of-secs}`

UI:
Object actions -> Share with a presigned URL