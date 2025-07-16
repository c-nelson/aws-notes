[CloudFormation](CloudFormation.md) provides several built-in functions that help you manage your stacks. Use intrinsic functions in your templates to assign values to properties that are not available until runtime.

[https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html)

### `Ref` & `Fn::GetAtt`
![Pasted image 20250707211036.png](_atts/Pasted%20image%2020250707211036.png)
### `Fn::Join` & `Fn::Split`
![Pasted image 20250707211524.png](_atts/Pasted%20image%2020250707211524.png)
### `Fn:GetAZs` & `Fn::Select`
![Pasted image 20250707211405.png](_atts/Pasted%20image%2020250707211405.png)
### `Fn:Base64` & `Fn::Sub`
Example with invalid sub, you can't reference itself
![Pasted image 20250707211751.png](_atts/Pasted%20image%2020250707211751.png)
### `Fn:Cidr`
![Pasted image 20250707212035.png](_atts/Pasted%20image%2020250707212035.png)