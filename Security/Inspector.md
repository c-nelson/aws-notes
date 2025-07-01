Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for exposure, vulnerabilities, and deviations from best practices.

- Scans [EC2](../Compute/EC2/EC2.md) & instance OS & containers
- Length of scans 15 mins, 1 hour, 8/12 hours or 1 day
- Provides a report of findings ordered by priority
- Network Assessment - Agentless
- Network & Host Assessment - Agent

## Rules Packages
Rules packages determine what is checked

- Network Reachability - no agent required
	- Agent can provide additional OS visibility
	- Check reachability end to end:
		- EC2, ALB, DX, ELB, ENI, IGW, ACLs, RT's, SG's, Subnets, VPCs, VGWs, VPC Peering
	- Returns RecognizedPortWithListener, RecognizedPortNoListener, RecognizedPortNoAgent
	- UnrecognizedPortWithListener

- Host Assessments - Agent required
	- Common vulnerabilities and exposures (**CVE**)
	- Center for Internet Security (**CIS**) Benchmarks
	- **Security best practices** for Amazon Inspector