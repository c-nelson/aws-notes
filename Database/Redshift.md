Redshift is a column based, petabyte scale, data warehousing product within AWS

Its designed for OLAP products within AWS/on-premises to add data to for long term processing, aggregation and trending.

- Direct Query [S3](../Storage/S3/S3.md) using Redshift Spectrum
- Direct Query other DBs using federated query
- Integrates with AWS tooling such as Quicksight
- SQL-like interface JDBC/ODBC connections

- Server based
- One AZ in a VPC - network cost/performance
- Leader Node - query input, planning and aggregation
- Compute Node - performing queries of data
- Redshift Enhanced VPC Routing - VPC Networking

![Pasted image 20250720213553.png](_atts/Pasted%20image%2020250720213553.png)

## Resilience
![Pasted image 20250720213912.png](_atts/Pasted%20image%2020250720213912.png)
