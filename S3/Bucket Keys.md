[[S3]] Bucket Keys reduce the cost of S3 [[Server-Side Encryption]] using [[KMS]] ([[Server-Side Encryption#SSE-KMS|SSE-KMS]]). Bucket-level keys for SSE can reduce AWS KMS request costs by up to 99 percent by decreasing the request traffic from [[S3]] to [[KMS]].

## Without a Bucket Key
Calls to [[KMS]] API are made for every upload.
![[Pasted image 20250213215415.png]]

## With a Bucket Key
Instead of of the [[KMS]] Key being used to generate each [[KMS#Data Encryption Keys (DEKs)|DEK]] for every object, [[KMS]] generates a time-limited Bucket Key. The bucket key is used for a period of time for every object.

![[Pasted image 20250213215828.png]]

- ﻿﻿CloudTrail KMS events now show the bucket..
- ﻿﻿... Not the Object
- ﻿﻿Works with replication .. the object encryption is maintained
- ﻿﻿if replicating plaintext to a bucket using bucket keys the object is encrypted at the destination side (ETAG changes)

