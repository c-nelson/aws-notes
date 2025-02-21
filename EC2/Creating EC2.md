## SSH Key Pair
is needed to SSH into the [[EC2]] instance.

Create one at:
EC2 Console -> Network & Security -> Key Pairs

## Launch Instance
EC2 Console -> Instances -> Launch Instance

1. Name the instance
2. Choose the OS
3. Select the [[EC2#AMI|AMI]] (Amazon Machine Image)
4. Select the instance type
5. Select the key pair for SSH
6. Network settings
	1. Select the [[VPC]]
	2. Selecting a subnet also means selecting an [[Global Infrastructure#Availability Zones|AZ]].
	3. To access the instance from the internet enable "Auto-assign public IP"
	4. Create a security group
		1. Set up SSH to be allowed from anywhere or specific IPs
7. Configure storage

On the instances view, the instance will start up and then begin security checks.

## Deleting Instance
1. Right click -> terminate instance
2. Go to security groups and delete it's security group

