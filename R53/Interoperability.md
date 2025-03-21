[R53](R53.md) can both register and host zone files and is typically used for both. Interoperability refers to using [R53](R53.md) to only register or only host and the other part being not within R53.

- R53 normally has 2 jobs:
	- Domain registrar
	- Domain hosting
- R53 can do BOTH, or either
- Steps when creating a hosted zone:
	- Domain Hosting
		- Accepts domain registration fee
		- Allocates 4 Name Servers (NS)
		- Creates a zone file on the NS
	- Domain Registrar
		- Communicates with the registry of the top level domain
		- Sets the NS records for the domain to point at the 4 NS above

![Pasted image 20250320200109.png](_atts/Pasted%20image%2020250320200109.png)
![Pasted image 20250320200331.png](_atts/Pasted%20image%2020250320200331.png)
![Pasted image 20250320200543.png](_atts/Pasted%20image%2020250320200543.png)