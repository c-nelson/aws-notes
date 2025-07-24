Amazon Athena is serverless querying service which allows for ad-hoc queries where billing is based on the amount of data consumed.

- Schema-on-read - table-like translation
- Original data never changed - remains on [S3](../Storage/S3/S3.md)
	- Data is conformed to schema on the fly
- Schema translates data => relational-like when read
- Output sent to other services
- No infrastructure needed
- Ideal where loading/transformation isn't desired
- Serverless querying scenarios - cost conscious
- Querying AWS logs, AWS Glue data catalogs, Web Server Logs

![Pasted image 20250718210241.png](_atts/Pasted%20image%2020250718210241.png)
![Pasted image 20250718210954.png](_atts/Pasted%20image%2020250718210954.png)