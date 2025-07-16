Template and Pseudo Parameters are two methods to provide input to a [CloudFormation](CloudFormation.md) template, which can influence what resources are provisioned, and the configuration of those resources.

## Pseudo Parameters
- AWS provided parameters that can be referenced
- Example AWS::Region, AWS::StackId, AWS::AccountId
[https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/pseudo-parameter-reference.html](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/pseudo-parameter-reference.html)

![Pasted image 20250707210122.png](_atts/Pasted%20image%2020250707210122.png)

## Template Parameters
- Accept inputs - console/CLI/API
- When a stack is created or updated
- Can be referenced within [logical resource](Physical%20&%20Logical%20Resources.md) which influence physical resources or configuration
- Can be configured with: Defaults, AllowedValues, Min and Max length, AllowedPatterns, NoEcho, Type

![Pasted image 20250707205921.png](_atts/Pasted%20image%2020250707205921.png)
