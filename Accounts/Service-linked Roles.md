A service-linked role is a unique type of [IAM Roles](IAM%20Roles.md) that is linked directly to an AWS service. 

Service-linked roles are predefined by the service and include all the permissions that the service requires to call other AWS services on your behalf. 

The linked service also defines how you create, modify, and delete a service-linked role. A service might automatically create or delete the role. It might allow you to create, modify, or delete the role as part of a wizard or process in the service. Or it might require that you use IAM to create or delete the role.

You can't delete the role until it is no longer required by a service.

[https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html)

![Pasted image 20250204214105.png](_atts/Pasted%20image%2020250204214105.png)

## PassRole

Allows a user to pass an existing role to a newly created service without having the permissions to edit that role.

![Pasted image 20250204215757.png](_atts/Pasted%20image%2020250204215757.png)