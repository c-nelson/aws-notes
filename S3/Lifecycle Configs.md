Automatically transition or expire objects within an [[S3]] bucket.

- Set of rules consisting of actions on a bucket or group of objects
- Is not a monitor, cannot be set on access frequency like [[Storage Classes#Intelligent-Tiering|Intelligent-Tiering]]

## Transition actions
- Change [[Storage Classes]] based on rules
- #AWSCommonTest minimum of 30 days on Standard before transitioning
	- Similarly, a single rule cannot transition and object to Standard-IA/One Zone-IA and then to glacier classes within 30 days

![[Pasted image 20250215204221.png]]

## Expiration actions
- Deletion of objects or versions of objects