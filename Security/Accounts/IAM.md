Identity and Access Management

Location: Services Search -> "IAM"

Creating entities and provide permissions.

IAM responsibilities:
- Manages Identities
- Authenticate
- Authorize

Types of IAM entities:
- User - users or applications
- Group - collections of related users
- Role - used by AWS services or external access. If you want to grants access to an unknown number of instances or users.

## Policy
Objects or documents used to define rules that allow or deny access to AWS when they are attached to IAM Users, Groups or Roles.

## Sign In
There is a unique url under the IAM dashboard for IAM users to sign in.
You can create an alias for the account so the url is easier.

## Create Users
IAM -> Users -> Create User
Assign a policy.

## Access Keys
Location: Username -> Security -> Create Access Keys
Long-Term Credentials

Generally used for CLI or APIs.

An IAM user can have up to 2 access keys.

Can be created, deleted, made active and inactive.

Composed of Access Key ID and Secret Access Key. The secret can only be access once.