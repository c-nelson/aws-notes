```
brew install awscli
```

Use [[IAM#Access Keys]] to with the the following command:
```
aws configure --profile "iamadmin-account"
```

or for configure a default [[IAM]] user to use, just:
```
aws configure
```

Profiles can be specified at the end of a command, for example:
```
aws s3 ls --profile iamadmin-account
```