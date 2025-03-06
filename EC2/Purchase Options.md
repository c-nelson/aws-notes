[EC2](EC2.md) Purchase Options, often called Launch Types

## On-Demand
- Default
![Pasted image 20250304204850.png](_atts/Pasted%20image%2020250304204850.png)

## Spot
- Cheapest
- Not reliable
- You set a maximum price, as availability gets scarcer price may go up. Then if the price goes over your maximum price, your instance is shut down.
![Pasted image 20250304205541.png](_atts/Pasted%20image%2020250304205541.png)

## Reserved
- Long term commitment for reduced or no price/second
- Locked to AZ or region
![Pasted image 20250304210156.png](_atts/Pasted%20image%2020250304210156.png)
#### Scheduled Reserved Instances
- Not running constantly but long term usage
- Specify frequency and time
- 1200 hr/year and 1 year term minimums
![Pasted image 20250305190022.png](_atts/Pasted%20image%2020250305190022.png)

#### Capacity Reservations
- When resources become scarce, AWS priority is:
	- Reserved
	- On-demand
	- Spot
- Capacity Reservations ensures you will have compute
- Capacity is reserved but don't necessarily need to have an instance running
- Zonal reservation vs Regional reservation vs On-Demand capacity reservation:
![Pasted image 20250305190857.png](_atts/Pasted%20image%2020250305190857.png)


## Dedicated Hosts
- Pay for entire host
- Designed for special instances
- No charges for instances
- Put any amount of instances you like
	- Resources managed by you
- Most common use is if software licensing is based on hardware
![Pasted image 20250304210700.png](_atts/Pasted%20image%2020250304210700.png)

## Dedicated Instances
- You don't share a host but the resources are AWS managed.
- Extra charges for instances
![Pasted image 20250304211228.png](_atts/Pasted%20image%2020250304211228.png)

## Savings Plan
- A hourly commitment for a 1 or 3 year term
- Options
	- A reservation of general compute dollar amounts
		- EC2, Fargate & Lambda
	- Or specifically [EC2](EC2.md) compute for better savings
- Products have an on-demand rate and a savings plan rate
- Resource usage consumes saving plan commitment at reduced savings plan rate
- Beyond your commitment, on-demand rate is used