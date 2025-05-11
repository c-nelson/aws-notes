Lifecycle hooks enable you to perform custom actions by _pausing_ instances as an [Auto Scaling groups](Auto%20Scaling%20Groups.md) launches or terminates them. When an instance is paused, it remains in a wait state either until you complete the lifecycle action using the `complete-lifecycle-action` command or the `CompleteLifecycleAction` operation, or until the timeout period ends (one hour by default).

- Custom Actions on instances during [ASG](Auto%20Scaling%20Groups.md) actions
	- When instance launch or terminate transitions
- Instances are paused within the flow
	- Until a timeout (then continue or abandon)
	- Or you perform an action and then resum either ASG process with `CompleteLifecycleAction`
- [[EventBridge]] or SNS Notifications

![Pasted image 20250415203920.png](_atts/Pasted%20image%2020250415203920.png)