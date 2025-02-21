[[IAM]] users are an identity used for anything requiring long-term AWS access e.g. Humans, Apps, or a service accounts.

A Principal is the user or app requesting to be authenticated. After authentication, that Principal becomes an Authenticated Identity.

![[Pasted image 20250130210316.png]]

### Important figures #AWSCommonTest 
- 5000 IAM Users per account
- IAM User can be a member of 10 groups
- This has design impacts, don't use IAM users for end users of an applications.