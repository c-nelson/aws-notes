**CloudFront behaviors** control how Amazon [CloudFront](CF.md) handles requests for your content. Each behavior defines a set of rules for a specific path pattern (e.g., `/images/*`) and lets you customize the way CloudFront interacts with your origin.

![Pasted image 20250513201233.png](_atts/Pasted%20image%2020250513201233.png)
#### **Key Behavior Settings:**

- **Path Pattern**: Specifies which requests this behavior applies to (e.g., `*`, `/api/*`, `/static/*`).
    
- **Origin**: Determines which origin to forward requests to.
    
- **Cache Policy**: Defines how CloudFront caches content (e.g., based on headers, query strings, cookies).
    
- **Origin Request Policy**: Controls what CloudFront includes in requests to your origin.
    
- **Allowed HTTP Methods**: Choose GET/HEAD or include POST, PUT, DELETE, etc.
    
- **Viewer Protocol Policy**: Enforce HTTPS (e.g., Redirect HTTP to HTTPS).
    
- **TTL Settings**: Set how long objects stay in the cache (min, max, and default TTL).
    
- **Lambda@Edge / CloudFront Functions**: Attach functions to customize request/response processing at edge locations.
    

#### **Default Behavior:**

- The default behavior (`*`) applies to all requests unless another behavior with a more specific path pattern matches.