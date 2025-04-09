DNSSEC strengthens authentication in DNS using digital signatures based on public key cryptography. With DNSSEC, it's not DNS queries and responses themselves that are cryptographically signed, but rather DNS data itself is signed by the owner of the data.


![Pasted image 20250320203118.png](_atts/Pasted%20image%2020250320203118.png)
Steps of DNSSEC

1) Asymmetric [KMS](../Security/KMS/KMS.md) Keys created by [R53](R53.md) called Key Signing Keys (KSK)
	- Public/Private
	- Stored on US-EAST-1 #AWSCommonTest 
2) R53 creates the Zone Signing Keys (ZSK) internally
	- ZSK creation and rotation handled by R53
3) R53 adds the public KSK and ZSK to the DNSKEY record inside the hosted zone
	- Tells any DNSSEC resolver which keys to use to verify the signature on any records sent
4) The private KSK is used to sign the DNSKEY records to create the RRSIG DNSKEY record
	- Both DNSKEY records can be used by a DNSSEC resolver to verify the keys are valid and unchanged
5) Provide hash of the public KSK to the parent hosted zone

- Can created [CW](../Logs/CW.md) alarms for DNSSEC issues
- Can enable DNSSEC Validation on [VPC](../Network/VPC/VPC.md)s so that invalid results on DNSSEC enabled zones won't be returned
