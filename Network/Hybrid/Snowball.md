Snowball, Snowball Edge and Snowmobile are three parts of the same product family designed to allow the physical transfer of data between business locations and AWS.

- Move large amounts of data IN and OUT of AWS
- Physically shipped storage - suitcase or truck
- Order them empty and load data
- Or order with AWS data, empty and return
- Data Encryption uses [KMS](../../Security/KMS/KMS.md)
- 50TB or 80TB capacity
- 1 Gbps or 10 Gbps network transfer
- 10 TB to 10 PB is the economical range (multiple devices)
- Multiple devices to multiple premises

- Snowball
	- Only includes storage

# Snowball Edge
- Both storage and compute
- Larger capacity
- 10 Gbps, 10/25 (SFP), 45/50/100 Gbps (QSFP+)
- Storage Optimized (with EC2)
	- 80TB, 24 vCPU, 32 Gib RAM, 1 TB SSD
- Compute Optimized
	- 100TB + 7.68 NVME, 52 vCPU, 208 GiB RAM
- Compute with GPU
	- Same as above with GPU
- Ideal for remote sites or where data processing on ingestion is needed

# Snowmobile
- Portable datacenter within a shipping container on a truck
- Special order
- Ideal for single location when 10 PB+ is required
- Up to 100PB per snowmobile
- Not economical for multi-site or sub 10PB