[CF](CF.md) origins store content distributed via edge locations.

The features available differ based on using S3 origins vs Custom origins

[Supported SSL/TLS protocols and ciphers for communication between viewers and CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/secure-connections-supported-viewer-protocols-ciphers.html#secure-connections-supported-ciphers)


CloudFront supports two main origin types:

- **S3 Origins**: Use Amazon S3 buckets to serve static content.
    
- **Custom Origins**: Use other AWS services (like EC2, ELB) or any web server (e.g., Nginx, Apache) over HTTP/HTTPS.
    

#### **Comparison Table: S3 Origins vs Custom Origins**

| Feature                  | **S3 Origin**                                                       | **Custom Origin**                            |
| ------------------------ | ------------------------------------------------------------------- | -------------------------------------------- |
| **Use Case**             | Static assets (images, CSS, JS, video)                              | Dynamic content, APIs, apps, websites        |
| **Supported Protocols**  | HTTP/HTTPS                                                          | HTTP/HTTPS                                   |
| **Signed URLs/Cookies**  | Supported with CloudFront                                           | Supported with CloudFront                    |
| **Origin Access**        | Can use Origin Access Control (OAC) or Origin Access Identity (OAI) | Public or private (security handled by app)  |
| **Origin Type**          | Amazon S3 bucket                                                    | Any HTTP(S) server (e.g., EC2, ALB, on-prem) |
| **Range GETs**           | Supported                                                           | Supported                                    |
| **Custom Headers**       | Not supported (unless using OAC with signed requests)               | Fully supported                              |
| **Redirection Handling** | CloudFront handles S3 redirects                                     | Handled by the origin server                 |
| **TLS Support**          | Auto-managed by AWS                                                 | Requires TLS setup on origin                 |
| **Object Versioning**    | Supported via S3                                                    | Handled by app logic                         |

### Origin Access

**Origin Access** controls how Amazon CloudFront communicates with your origin, especially when using **Amazon [S3](../../Storage/S3/S3.md)** as the origin. It ensures that users **can't bypass CloudFront** and access your content directly from the origin (e.g., your S3 bucket).

#### 🔹 **Why Use Origin Access?**

- To **secure S3 content**, so it's only accessible through CloudFront.
    
- To **prevent direct access** to your S3 URLs, which could bypass caching, signed URLs, or security headers.
    

#### 🔹 **Types of Origin Access for S3:**

|**Method**|**Description**|
|---|---|
|**Origin Access Identity (OAI)**|Legacy method. Creates a virtual identity for CloudFront to access S3. You update the S3 bucket policy to allow this OAI only.|
|**Origin Access Control (OAC)**|Modern, recommended approach. More flexible and supports advanced security features like **signed requests** and **headers**.|

> 🔐 **OAC is now the preferred method**, especially for new distributions. It offers improved security and simplifies IAM-based access.
