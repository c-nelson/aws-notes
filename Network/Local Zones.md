AWS Local Zones are a type of infrastructure deployment that places compute, storage, database, and other select AWS services close to large population and industry centers.

[https://aws.amazon.com/about-aws/global-infrastructure/localzones/features/](https://aws.amazon.com/about-aws/global-infrastructure/localzones/features)

- 1 zone - so no built in resilience
- Thank of them like an AZ but near your location
- Closer to you for lower latency
- Not all products support them, many are opt in with limitations
- DX to a local zone is supported
- Utilize parent region, ie EBS snapshots to parent

### Without Local Zones
![Pasted image 20250723212625.png](_atts/Pasted%20image%2020250723212625.png)

### With Local Zones
![Pasted image 20250723213006.png](_atts/Pasted%20image%2020250723213006.png)