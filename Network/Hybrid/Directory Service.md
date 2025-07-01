Provides a managed directory - store of users, objects and other configurations.

### What is a Directory
- Stores objects (eg Users, Groups, Computers, Servers, File Shares) with a structure (domain/tree)
- Multiple trees can be grouped into a forest
- Commonly used in Windows environments
- Sign-in to multiple devices with same username/password provides centrailized management for assets
	- Microsoft Active Directory Domain Services (AD DS)
	- Open-source alternative - SAMBA

### Directory Service
- AWS managed implementation
- Runs within a [VPC](../VPC/VPC.md)
- To implement HA deploy into multiple AZs
- Some AWS services require a directory eg Amazon Workspaces
- Can be isolated within AWS
- Or integrated with existing on-premises system
- Or act as a proxy back to on-premises

## Simple AD Mode
![Pasted image 20250618210032.png](_atts/Pasted%20image%2020250618210032.png)

## Managed Microsoft AD
![Pasted image 20250618210259.png](_atts/Pasted%20image%2020250618210259.png)

## AD Connector
![Pasted image 20250618210524.png](_atts/Pasted%20image%2020250618210524.png)

## Choosing between modes
- Simple AD - the default. Simple requirements. A directory in AWS
- Microsoft AD - applications in AWS which need MS AD DS, or you need to TRUST AD DS
- AD Connector - use AWS services which need a directory without storing any directory info in the cloud - proxy