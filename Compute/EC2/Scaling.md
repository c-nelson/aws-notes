How to handle increasing/decreasing user load
## Horizontal
Adding more [EC2](EC2.md) instances

Cons:
- Requires a load balancer
- Sessions are spread between instances
	- Requires application support or off-host sessions
	- Servers need to be stateless
Pros:
- No disruption when scaling
- No limits to scaling
- Less expensive than large instances
- More granular on scaling

## Vertical
Adding more resources to a server

Cons:
- Each resize requires a reboot
	- Usually means rescaling at outage times
	- Limits how fast you can react to load
- Larger instances cost is not linear
- Upper cap on performance
Pros:
- No app modification
- works for all applications, even monoliths