[https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/enhanced-networking.html](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/enhanced-networking.html)

Enhanced networking is the AWS implementation of SR-IOV, a standard allowing a physical host network card to present many logical devices which can be directly utilized by [EC2](EC2.md) instances.

This means lower host CPU usage, better throughput, lower and consistent latency.

- Uses SR-IOV - NIC is virtualization aware
- No charge - available on most EC2 [Instance Types](Instance%20Types.md)
- Higher I/O, Lower Host CPU Usage
- More Bandwidth
- Higher packets-per-second
- Consistent lower latency

## EBS Optimization
[EBS](../../Storage/EBS/EBS.md) optimization on instances means dedicated bandwidth for storage networking - separate from data networking.

- Most instances support and have enabled by default