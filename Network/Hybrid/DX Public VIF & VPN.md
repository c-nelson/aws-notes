Neither public or private [VIFS](Direct%20Connect%20(DX).md) offer any form of encryption.

Public VIFs+[IPSec VPN](IPSEC%20VPN.md) is a way to provide access to private VPC resources, using an encrypted IPSEC tunnel for transit.

- Encrypted & Authenticated tunne
- Over DX (low letency)
- Uses Public VIF + [VGW](Site-to-Site%20VPN.md)/[Transit Gateway](Transit%20Gateway.md) public endpoints
- VPNs are transit agnostic (DX / Public internet)
- Wider vendor support
- VPN has more cryptographic overhead vs MACsec
- Can be used as backup to DX

![Pasted image 20250608214230.png](_atts/Pasted%20image%2020250608214230.png)