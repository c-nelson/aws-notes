The Database Migration Service (DMS) is a managed service which allows for 0 data loss, low or 0 downtime migrations between 2 database endpoints.

The service is capable of moving databases INTO or OUT of AWS.

- Runs using a replication instance
- Source and Destination endpoints point at
	- Source and Target Databases
	- One endpoint must be on AWS

![Pasted image 20250405210442.png](_atts/Pasted%20image%2020250405210442.png)

## Schema Conversion Tool (SCT)
- Used when converting one database engine to another
- Including DB -> S3 (Migrations using DMS)
- Not used when migrating between same types of DBs
- Works with OLTP DB types (MySQL, MSSQL, Oracle)
- And OLAP (Teradata, Oracle, Vertica, Greenplum)
 