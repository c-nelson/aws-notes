Right click on the instance and select "Connect".

## EC2 Instance Connect
brings up a console in the browser.

Instance connect uses [IAM](../../Security/Accounts/IAM.md) policies to control SSH access to your instance, without the need to manage SSH keys.
## Session Manager

## SSH client
Use the [SSH Key Pair](Creating%20EC2.md#SSH%20Key%20Pair) previously created.

1. Change the permissions of the `.pem` file.
   `chmod 400 example.pem`
2. SSH into the instance using the `.pem`
   `ssh -i "example.pem" ec2-user@ec2-id-123.compute-1.amazonaws.com`