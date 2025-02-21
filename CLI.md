```
brew install awscli
```

Use [IAM \> Access Keys](Accounts/IAM.md#Access%20Keys) to with the the following command:
```
aws configure --profile "iamadmin-account"
```

or for configure a default [IAM](Accounts/IAM.md) user to use, just:
```
aws configure
```

Profiles can be specified at the end of a command, for example:
```
aws s3 ls --profile iamadmin-account
```