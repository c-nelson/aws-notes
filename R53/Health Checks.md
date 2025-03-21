[R53](R53.md) health checks monitor the health and performance of your web applications, web servers, and other resources. Each health check that you create can monitor one of the following:

- Endpoint - The health of a specified resource, such as a web server
- The status of other health checks (Calculated)
- The status of a [CW](../Logs/CW.md) alarm

- Health checks are separate from, but used by [Records](DNS%20Record%20Types.md)
- Health checkers located globally
- Check every 30 seconds
	- every 10s costs extra
- TCP, HTTP/S
- HTTP/S with String Matching
	- Must contain a string in the response body
- Healthy or Unhealthy
![Pasted image 20250317213109.png](_atts/Pasted%20image%2020250317213109.png)