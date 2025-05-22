Neither [Cloud Watch](CW.md) or [CloudWatch Logs](CloudWatch%20Logs.md) can natively capture data _inside_ an [EC2](../../Compute/EC2/EC2.md) instance.

CloudWatch Agent needs to be installed inside the instance.

Requires additional work on security permissions.

![Pasted image 20250315215414.png](_atts/Pasted%20image%2020250315215414.png)

### Steps:
1) Create an IAM role
	- Type : EC2 Role
	- Add Managed Policy 
		- `CloudWatchAgentServerPolicy`
		- `AmazonSSMFullAccess`
2) Attach the role to the EC2 instance
3) Inside the instance install CloudWatch Agent and run wizard
	- Select advanced for default metrics config
	- Select log files to monitor
		- ex `/var/log/httpd/access_log`
	- Save config

```bash
sudo dnf install amazon-cloudwatch-agent

sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard
```

4) Config saved in:
	- `/opt/aws/amazon-cloudwatch-agent/bin/config.json`
	- Wizard prompts to save config in [SSM Parameter Store](../../Security/SSM%20Parameter%20Store.md)
5) Start agent:
```Bash
# Bug Fix (these are needed else the agent won't start)
sudo mkdir -p /usr/share/collectd/
sudo touch /usr/share/collectd/types.db

# Load Config and start agent
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c ssm:AmazonCloudWatch-linux -s
```

