RDS (OLTP)
* SQL
* MySQL
* PostgreSQL
* Oracle
* Aurora
* MariaDB

DynamoDB(NoSQL)

RedShift (OLAP)

Elasticache
* Memcached
* Redis

* RDS runs on virtual machines
* You cannot log into these operating systems however.
* Patching of the RDS Operating System and DB is Amazon's responsibility
* RDS is NOT Serverless
* Aurora Serverless IS Serverless

There are two different types of Backups for RDS
* Automated Backups
* Database Snapshots

Read Replicas
* Can be Multi-AZ
* Used to increase performance
* Must have backups turned on
* Can be in different regions
* Can be Aurora or MySQL
* Can be promoted to master, this will break the replication with the Read Replica.

MultiAZ
* Used for DR.
* You can force a failover from one AZ to another by rebooting the RDS instance

Encryption is supported for all RDS. Encryption is done using the AWS KMS service. Once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots.

DynamoDB
* Stored on SSD Storage
* Spread across 3 geographically distinct dat acenters
* Eventual Consistent Reads (Default)
* Strongly Consistent Reads

Redshift
* Redshift is used for business intelligence
* Available in only 1 AZ

Redshift Backups
* Enabled by default with a 1 day retention period
* Maximum retention period is 35 days
* Redshift always attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in Amazon S3)
* Redshift can also asynchronously replicate your snapshots to S3 in another region for disaster recovery.

Aurora
* 2 copies of your data is contained in each availability zone, with minimum of 3 availability zones. 6 copies of your data.
* You can share Aurora Snapshots with other AWS accounts
* 2 types of replicas available. Aurora Replicas and MySQL replicas. Automated failover is only available with Aurora Replicas.
* Aurora has automated backups turned on by default. You can also take Snapshots with Aurora. You can share these snapshots with other AWS accounts.

Elasticache
* Use Elasticache to increase database and web application performance
* Reddis is Multi-AZ
* You can do backups and restores of Reddis
* If you need to scale horizontally, use Memcached