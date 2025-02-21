[S3](S3.md) Bucket Keys reduce the cost of S3 [Server-Side Encryption](Server-Side%20Encryption.md) using [KMS](../KMS/KMS.md) ([SSE-KMS](Server-Side%20Encryption.md#SSE-KMS)). Bucket-level keys for SSE can reduce AWS KMS request costs by up to 99 percent by decreasing the request traffic from [S3](S3.md) to [KMS](../KMS/KMS.md).

## Without a Bucket Key
Calls to [KMS](../KMS/KMS.md) API are made for every upload.
![Pasted image 20250213215415.png](_atts/Pasted%20image%2020250213215415.png)

## With a Bucket Key
Instead of of the [KMS](../KMS/KMS.md) Key being used to generate each [DEK](../KMS/KMS.md#Data%20Encryption%20Keys%20(DEKs)) for every object, [KMS](../KMS/KMS.md) generates a time-limited Bucket Key. The bucket key is used for a period of time for every object.

![Pasted image 20250213215828.png](_atts/Pasted%20image%2020250213215828.png)

- ﻿﻿CloudTrail KMS events now show the bucket..
- ﻿﻿... Not the Object
- ﻿﻿Works with replication .. the object encryption is maintained
- ﻿﻿if replicating plaintext to a bucket using bucket keys the object is encrypted at the destination side (ETAG changes)

