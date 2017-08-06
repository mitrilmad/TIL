# RDS

## automated backup , snapshot
- snapshots are stored even after orgitinal RDS instances are deleted. **unlike automated backup**
- restoring backup, will be new RDS instance with new end point.

## encryption
- by using AWS KMS
- encrypting an existing DB instance is not supported.

## multi-az , read replica
**Multi-az is for DR only. not used for improving performance.**
**for performance , need replicas for scaling**

### readreplica
- Asynchronous replication from the primary RDS instance to the read replica.
- Read replica support Mysql Server, PostgreSQL, MariaDB
- must have automatic backups turned on in order to deploy a read replica
- can have up to 5 read replicas.

## DynamoDB
- stored SSD storage
- Spread across 3 geographically
- eventual consistency reads (default) , take whithin a second. best read performance

### pricing
- write throughput 0.0065 per hour for every 10 units
- read thruougput  0.0065 per hour for every 50 units.


**value**
**iops mysql DB can have 6 TB default**
**the maximum provisioned IOPS capacity on oracle , mysql is 30,000 IOPS**

## Aurora scaling
- Start with 10Gb, up to 64Tb
- scale up to 32vCPU and 244Gb of memory
- 2 copies of your data in each az, minimum of 3 az ,  6 copies of your data
- 2 types of replica , aurora , mysql read replica
