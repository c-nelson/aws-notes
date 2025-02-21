An AWS Account is a container for identities (users) and Resources.

An Account has:
- Name
- Unique email address
	- Each account has a root user using email
- Credit card

Root user always has full control.

You should always create an [[IAM]] admin user to do admin tasks. Then the root account should rarely be used.

Use Identity and Access Management ([[IAM]]) Users, Groups and Roles to allow access.

Creating multiple accounts is a good idea to containerize
- Ex. - DEV, TEST, PROD

Gmail trick to use the same email for multiple accounts, use `+sometext`:
nelson.christian.m+awsaccount1@gmail.com
nelson.christian.m+awsaccount2@gmail.com

Good Idea to set up MFA under username menu -> Security Credentials
