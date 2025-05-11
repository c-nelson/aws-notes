Deals with keeping a user session on the same instance while also using [ELB](ELB.md)

When user makes first request the [ELB](ELB.md) generates a cookie called `AWSALB` which locks the device to a single backend for a duration.

