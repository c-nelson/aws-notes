[EC2](EC2.md) Bootstrapping is the process of configuring an [EC2](EC2.md) instance to perform automated install & configuration steps 'post launch' before an instance is brought into service.

With [EC2](EC2.md) this is accomplished by passing a script via the User Data part of the [Metadata](Metadata.md) service - which is then executed by the [EC2](EC2.md) Instance OS.

- Allows for EC2 build automation
- Bootstrapping enabled though User Data [Metadata](Metadata.md)
	- `http://169.254.169.25/latest/user-data`
	- Anything in User Data is executed by the instance OS
	- Only executed on launch
- EC2 doesn't interpret or validate, OS needs to understand the User Data
- User Data script can be passed into [CFN](../CFN/CFN.md)

### User Data
- ﻿﻿It's opaque to EC2 .. its just a block of data
- ﻿﻿It's NOT secure - don't use it for passwords or long term credentials (ideally)
- ﻿﻿User data is limited to 16 KB in size
- ﻿﻿Can be modified when instance stopped
- ﻿﻿But only executed once at launch