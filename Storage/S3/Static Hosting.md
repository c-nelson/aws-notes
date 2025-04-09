Accessing [S3](S3.md) is generally done via APIs

Static Website Hosting is a feature of the product which lets you define a HTTP endpoint, set index and error documents and use [S3](S3.md) like a website.

AWS creates a generated endpoint based on the bucket name.

Custom domains can be created via [R53](../../R53/R53.md). The bucket name needs to follow the domain pattern that is going to be used.

Be aware that there are request charges to objects within [S3](S3.md). 
## Use cases

#### Offloading
To save compute resources, set up a dynamic html page to point to media within a [S3](S3.md) bucket, rather than an [EC2](../../Compute/EC2/EC2.md) gathering the resources and serving them.
#### Out-of-band pages
Set up error or maintenance pages to show when [EC2](../../Compute/EC2/EC2.md) is down.