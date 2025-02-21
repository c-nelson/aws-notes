Containers for organization of [IAM Users](IAM%20Users.md).

Groups have no log in credentials, you cannot log in as a IAM Group. For the exam, don't over state what a group is capable of, it is simple a container of users. #AWSCommonTest 

A user can be a member of multiple groups.

Benefits:
- Allow effective admin style management of users
- Groups can have [Identity Policies](Identity%20Policies.md) attached to them

A user can have multiple policies attached via multiple group policies, and managed and inline individual policies.

IAM User can be a member of 10 groups.

No limit for the number of users within a group (all 5000 IAM users could be in a group).

There is not a built in "all users group". #AWSCommonTest

Groups cannot be nested.

Soft limit of 300 groups per [account](Accounts.md).

Groups are not a true [IAM](IAM.md) identity. They can't be referenced as a principal in a policy. (A resource policy cannot grant access to a group.)

