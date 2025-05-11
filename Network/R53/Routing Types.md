# [R53](R53.md) Routing Types

## Simple
- Default
- Used when you want to route traffic to a single resource
- Doesn't support [Health Checks](Health%20Checks.md)
![Pasted image 20250317211014.png](_atts/Pasted%20image%2020250317211014.png)


## Failover
Failover routing lets you route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy.

Relies on [Health Checks](Health%20Checks.md) on the primary resource.

![Pasted image 20250318204330.png](_atts/Pasted%20image%2020250318204330.png)

## Multi Value
Multivalue answer routing lets you return multiple values, such as IP addresses for your web servers, in response to DNS queries. You can specify multiple values for almost any record, but multivalue answer routing also lets you check the health of each resource, so [R53](R53.md) returns only values for healthy resources.

![Pasted image 20250320191237.png](_atts/Pasted%20image%2020250320191237.png)

## Weighted Routing
Weighted routing lets you associate multiple resources with a single domain name and choose how much traffic is routed to each resource. This can be useful for a variety of purposes, including load balancing and testing new versions of software.

![Pasted image 20250320191650.png](_atts/Pasted%20image%2020250320191650.png)

## Latency Routing
If your application is hosted in multiple [Regions](../../Fundamentals/Global%20Infrastructure.md#AWS%20Regions), you can improve performance for your users by serving their requests from the Region that provides the lowest latency.

![Pasted image 20250320192032.png](_atts/Pasted%20image%2020250320192032.png)

## Geolocation Routing
Geolocation routing lets you choose the resources that serve your traffic based on the geographic location of your users, meaning the location that DNS queries originate from.

- Not about proximity but serving or locking content to a specific relevant location

![Pasted image 20250320192451.png](_atts/Pasted%20image%2020250320192451.png)

## Geoproximity Routing
Geoproximity routing lets R53 route traffic to your resources based on the geographic location of your users and your resources. You can also optionally choose to route more traffic or less to a given resource by specifying a value, known as a _bias_. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.

- Calculates the distance between the server and client
![Pasted image 20250320193304.png](_atts/Pasted%20image%2020250320193304.png)


