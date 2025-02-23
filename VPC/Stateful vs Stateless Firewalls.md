## TCP Review
![Pasted image 20250222204143.png](_atts/Pasted%20image%2020250222204143.png)

## Stateless Firewalls
No state, the firewall sees the request and response from client and server as two separate connections. Meaning two firewall rules need to be made (1 inbound, 1 outbound).

Consider the case where the application server is requesting updates from a linux server. Another set of two rules will need to be made.

Requests always use ephemeral random ports so with stateless firewalls, you often have to allow the full range of ports.

![Pasted image 20250222205800.png](_atts/Pasted%20image%2020250222205800.png)

## Stateful Firewalls
Identifies the request and response as being related. The firewall automatically knows what data is the response coming from the server.

Generally, with a stateful firewall, you only need to allow the request and the response is allowed automatically.

Lower admin overhead.

Don't need to allow the full ephemeral port range.

![Pasted image 20250222210324.png](_atts/Pasted%20image%2020250222210324.png)

