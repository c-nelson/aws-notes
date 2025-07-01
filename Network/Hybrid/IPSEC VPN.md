IPsec VPN negotiation occurs in two phases. In Phase 1, participants establish a secure channel in which to negotiate the IPsec security association (SA). In Phase 2, participants negotiate the IPsec SA for authenticating traffic that will flow through the tunnel.

- IPSEC is a group of protocols
- It setups secure tunnels across insecure networks between two peers (local and remote)
- Provides Authentications and encryption

Uses asymmetric encryption (slower) to transfer symmetric encryption (faster) keys and then uses symmetric to transfer data.
- IKE Phase 1 (Slow & heavy)
	- Authenticate - pre-shared key/cert
	- Asymmetric encryption to create shared symmetric key
	- IKE SA Created (phase 1 tunnel)
- IKE Phase 2 (Fast & agile)
	- Uses the keys from phase 1
	- Agree on encryption method for bulk transfer
	- Create IPSEC SA (phase 2 tunnel)

![Pasted image 20250604204443.png](_atts/Pasted%20image%2020250604204443.png)![Pasted image 20250604204714.png](_atts/Pasted%20image%2020250604204714.png)

### Policy-based VPNs
- Rule sets match traffic => a pair of SAs
- Different rules/security settings
- One phase 1 tunnel running multiple phase 2 tunnels

### Route-based VPNs
- Target matching based on prefix
- Matches a single pair of SAs
- One Phase 1 tunnel running one phase 2 tunnel

![Pasted image 20250604205111.png](_atts/Pasted%20image%2020250604205111.png)