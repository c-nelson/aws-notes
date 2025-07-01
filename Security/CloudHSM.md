CloudHSM is an AWS provided Hardware Security Module products.

Provides similar functionality to [KMS](KMS/KMS.md), with some key differences.
- [KMS](KMS/KMS.md) is a shared by separate service - other accounts use the same service

CloudHSM is required to achieve compliance with certain security standards such as [FIPS 140-2]([https://en.wikipedia.org/wiki/FIPS_140-2](https://en.wikipedia.org/wiki/FIPS_140-2)) Level 3.

#AWSCommonTest
- True "single tenant" hardware security module
- AWS provisioned but fully customer managed
- Fully FIPS 120-2 Level 3 compliant
	- KMS is L2 overall, some L3
- Access with industry stand APIs - PKCS#11, java cryptography extensions, microsoft CryptoNG CNG libraries
- KMS can use CloudHSM as a custom key store, CloudHSM integration with KMS

![Pasted image 20250625214208.png](_atts/Pasted%20image%2020250625214208.png)

## Use cases
- No native AWS integration.. e.g. no S3 SSE
- Offload the SSL/TLS processing for web servers
- Enabled transparent data encryption (TDE) for Oracle databases
- Protect the private keys for an Issuing Certificate Authority