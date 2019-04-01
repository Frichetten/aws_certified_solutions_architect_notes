# Back Ups with RDS
There are two kinds

# Automated Backups
* Automated Backups allow you to recover your database to any point in time within a "retention period". The retention period can be between one and 35 days. Automated Backups are enabled by default. The backup data is stored in S3 and you get free storage space equal to the size of your database. So if you have an RDS instance of

# Database Snapshots
DB Snapshots are done manually ( they are user initiated). They are stored even after you delte the original RDS instance, unlike automated backups.

# Restoring Backups
Whenever you restore either an Automatic Backup or a manual Snapshot, the restored version of the database will be a new RDS instance with a new DNS endpoint.

# Encryption at Rest
Encryption at rest is done using the AWS Key Management Service (KMS). Once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots.

# What is Multi-AZ
Multi-AZ allows oyu to have an exact copy of your production database in another Availability Zone. AWS handles the repllication for you, so when your production database is written to, this write will automatically be synchronized to the stand by database. In the even of planned database maintenance, DB instance failure, or an Availability Zone failure, Amazon RDS will automatically failover to the standby so that database operations can resume quickly without administrative intervention.

Multi-AZ is for Disaster Recovery only

# What is Read Replica
Read Replicas allow you to have a read-only copy of your production database. This is achieved by using Asynchronous replication from the primary RDS instance to the read replica. You use read replicas primarily for very read-heavy database workloads.

# Things to know about Read Replicas
* Used for scaling, not for DR!
* Must have automatics backups turned on in order to deploy a read replica
* You can have up to 5 read replica copies of any database
* You can have read replicas of read replicas (but watch out for latency)
* Each read replica will have its own DNS endpoint
* You can have read replicas that have Multi-AZ
* You can create read replicas of Multi-AZ source databases.
* Read replicas can be promoted to be their own databases. This breaks the replication
* You can have a read replica in a second region

# Exam Tips
There are two different types of Backups for RDS
    * Automated Backups
    * Database Snapshots
Read Replicas
    * Can be Multi-AZ
    * Used to increase performance
    * Must have backups turned on
    * Can be in different regions
    * Can be Aurora or MySQL
    * Can be promoted to master, this will break the Read Replica
Multi-AZ
    * Used for DR (Data Recovery)
    * You can force a failover from one AZ to another by rebooting the RDS instance
Encryption at rest is supported for MySQL, ORacle, SQL Server, PostgreSQL, MariaDB 7 Aurora. Encryption is done using the AWS Key Management Service (KMS) service. Once your RDS instance is encrypted, the data stored at rest in the udnerlying storage is encrypted, as are its automated backups, read replicas, and snapshots