MySQL compatible, relation database engine that combines the speed and availability of high-end commercial databases with teh simplicity and cost-0effectiveness of open source databases. Amazon Aurora provides up to five times better performance than MySQL at a price point one tenth that of a commercial database while delivering similar performance and availability.

# The basics
* Start with 10GB, Scales in 10GB increments to 64TB
* Compute resources can scale up to 32vCPUs and 244GB of Memory
* 2 copies of your data is contained in each availability zone, with minimum of 4 availability zones. 6 copies of your data.

# Scaling Aurora
* Aurora is designed to transparently handle the loss of up to two copies of data wihtout affecting database write availability and up to three copies without affecting read availability.
* Aurora storage is also self-healing. Data blocks and disks are continuously scanned for errors and repaired automatically.

# Two types of Aurora replicas are available
* Aurora Replicas (currently 15)
* MYSQL Read Replicas (currently 5)

# Backups with Aurora
* Automated backups are always enabled on Amazon Aurora DB instances. Backups do not impact database performance
* You can also take snapshots with Aurora. This also does not impact on performance.
* You can share Aurora Snapshots with other AWS accounts.

# Exam Tips
* 2 copies of your data is contained in each availability zone, with minimum of 3 availability zones. 6 copies of your data.
* You can share Aurora Snapshots with other AWS accounts.
* 2 Types of replicas available. Aurora Replicas and MySQL replicas. Automated failover is only available with Aurora Replicas.
* Aurora has automated backups turned on by default. You can also take Snapshots with Aurora. You can share these snapshots with other AWS accounts.