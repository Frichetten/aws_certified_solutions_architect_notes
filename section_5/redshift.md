A fast and powerful, fully managed, petabyte-scale data warehouse service in the cloud. Customers can start small for just $0.25 per hour with no commitments or upgront costs and scale to a petabyte or more for $1000 per terabyte per year, less than a tenth of most other data warehousing solutions.

# OLTP vs OLAP
Data warehousing databases use different type of architecture both from a database perspective and infrastructure layer.

# Redshift Configuration
* Single Node (160Gb)
* Multi-Node
    * Leader Node (manages client connections and receives queries)
    * Compute Node (store data and perform queries and computations). Up to 128 Compute Nodes.

# Advanced Compression
Columnar data stores can be compressed much more than row-based data stores because similar data is stored sequentially on disk. Amazon RedShift employes multiple compression techniques and can often achieve significant compression relative to traditional relational data stores.

# Massively Parallel Processing (MPP)
Amazon Redhsift automatically distributes data and query load across all nodes. Amazon Redshift makes it easy to add nodes to your data warehouse and enables you to maintain fast query performance as your data warehouse grows.

# Backups
* Enabled by default with a 1 day retention period.
* Maximum retention poeriod is 35 days
* Redshift always attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in Amazon S3).
* Redshift can also asynchronously replicate your snapshots to S3 in another region for disaster recovery.

# Pricing
* Computer Node Hours (total number of hours you run across all your comput nodes for the billing period. You are billed for 1 unit per node per hour, so a 3-node data warehouse cluster running persistently for an entire mont would incur 2,160 instance hours. You will not be charged for leader nod Hours; only compute nodes will incur charges)
* Backup
* Data transfer (only within a VPC, not outside it).

# Security
* Encrypted in transit using SSL
* Encrypted at rest using AES-256 encryption
* By default RedShift takes care of key management
    * Manage your own keys through HSM
    * AWS KEy management Service

# Availability
* Currently only available in 1 AZ
* Can restore snapshots to new AZs in the event of an outage

# Exam Tips
* Redshift is used for business intelligence
* Only available in 1 AZ
## Backups
* Enabled by default with a 1 day retention period.
* Maximum retention period is 35 days
* Redshift always attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in Amazon S3).
* Redshift can also asynchronously replicate your snapshots to S3 in another region for disaster recovery.
