# [EBS](EBS.md) Volume Types

## General Purpose

#### GP2
- Default
- Good for boot volumes
- SSD based
- 1GB - 16TB
- Created with an IO Credit allocation
	- Credits fill at minimum 100 per second + 3 per second per GB of volume size
![Pasted image 20250301133449.png](_atts/Pasted%20image%2020250301133449.png)

#### GP3
- SSD based
- Different IO credit system
![Pasted image 20250301133930.png](_atts/Pasted%20image%2020250301133930.png)

## Provisioned IOPS SSD
Provides high performance for mission-critical, low-latency, or high-throughput workloads.

IPOS can be adjusted independently of size of volume.

- IO1
- IO2
- IO2 Block Express
	- Larger throughput
	- Larger volumes

![Pasted image 20250301134950.png](_atts/Pasted%20image%2020250301134950.png)

## HHD Based
- st1
	- Throughput Optimized HDD
	- A low-cost HDD designed for frequently accessed, throughput-intensive workloads.
- sc1
	- Cold HDD
	- The lowest-cost HDD design for less frequently accessed workloads.
![Pasted image 20250301141153.png](_atts/Pasted%20image%2020250301141153.png)