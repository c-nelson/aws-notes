The cfn-hup helper is a daemon that detects changes in resource metadata and runs user-specified actions when a change is detected. This allows you to make configuration updates on your running [EC2](../EC2/EC2.md) instances through the UpdateStack API action.

- [cfn-init](cfn-init.md) only runs once, if updated it isn't rerun
- cfn-hup points at a logical resource in a stack and detects metadata changes
- cfn-hup can rerun cfn-init

![Pasted image 20250712210511.png](_atts/Pasted%20image%2020250712210511.png)