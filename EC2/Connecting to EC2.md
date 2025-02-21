Right click on the instance and select "Connect".

## EC2 Instance Connect
brings up a console in the browser.

## Session Manager

## SSH client
Use the [[Creating EC2#SSH Key Pair|SSH Key Pair]] previously created.

1. Change the permissions of the `.pem` file.
   `chmod 400 example.pem`
2. SSH into the instance using the `.pem`
   `ssh -i "example.pem" ec2-user@ec2-id-123.compute-1.amazonaws.com`