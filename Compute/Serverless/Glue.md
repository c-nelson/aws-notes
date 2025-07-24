Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.

- Serverless ETL
	- Compared to datapipeline which does ETL using servers
- Moves and transforms data between source and destination
- Crawls data sources and generates Glue Data catalog
- Data Source Stores:
	- [S3](../../Storage/S3/S3.md)
	- [RDS](../../Database/RDS/RDS.md)
	- JDBC Compatible
	- [DynamoDB](../../Database/DynamoDB/DynamoDB.md)
- Data Source Streams:
	- [Kinesis Data Streams](../../Messages-Logs/Kinesis/Kinesis%20Data%20Streams.md)
	- Apache Kafka
- Data Targets
	- [S3](../../Storage/S3/S3.md)
	- [RDS](../../Database/RDS/RDS.md)
	- JDBC Databases

## Data Catalog
- Persistent metadata about data sources in region
- One catalog per region per account
- Avoids data silos
- Configure crawlers for data sources

![Pasted image 20250510210807.png](_atts/Pasted%20image%2020250510210807.png)