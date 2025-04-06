Running a database directly on an [EC2](../EC2/EC2.md) is generally not a good idea unless there is a specific reason you need to do so. The other products like [RDS](RDS.md) are preferable.
## Architecture of DBs on [EC2](../EC2/EC2.md)

The usual architecture is a single instance for the app and databases or split off the database to another instance.
![Pasted image 20250325201611.png](_atts/Pasted%20image%2020250325201611.png)
#### Reasons you might use EC2 for DB..
- Access to the DB instance OS
- Advanced DB option tuning (DBROOT)
- DB or DB version AWS doesn't provide
- Specific OS/DB combination requirement
#### Cons
- Admin overhead
- Backup / DR management
- EC2 is in a single AZ
- Lack Features
- No serverless, no easy scaling
- Replication
- Performance