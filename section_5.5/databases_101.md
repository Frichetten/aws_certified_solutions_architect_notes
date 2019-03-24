# What is a relational database
Relational databases are what most of us are all used to. They have been around since the 70's. Think of a traditional spreadsheet:
    * Database
    * Tables
    * Rows
    * Fields (colums)

# Relational Databases
* SQL Server
* Oracle
* MySQL Server
* PostgreSQL
* Aurora
* MariaDB

# Multi-AZ vs Read Replicas
## RDS has two key features
* Multi-AZ - For disaster recovery
* Read Replicas - For performance

# Non Relational Databases
* Collection = Table
* Document  = Row
* Key Value Pairs = Fields

# What is Data Warehousing
Used for business intelligence. Tools like Cognos, Jaspersoft, SQL Server Reporting Services.

Used to pull in very large and complex data sets. Usually used by management to do queries on data (such as current performance vs targets etc).

# OLTP vs OLAP
Online Transaction Processing differs from Online Analytics Processing (OLAP) in terms of the types of queries you will run.

OLTP Example:
Order number 2120121
Pulls up a row of data such as Name, Date, Address, etc.

OLAP transaction Example:
Net Profit for EMEA and PAcific for the Digital Radio Product.
Pulls in large number of records.

Sum of Radios Sold in EMEA, sum of radios sold in pacific. Unit cost of Radio in each region.

Data Warehousing databases use different type of architecture both from a database prespective and infrastructure layer.

Amazon's Data Warehouse solution is called Redshift

# What is ElastiCache
ElastiCache is a web service that makes it easy to deploy, operate, and scale an in-memory cache in the cloud. The service improves the performance of web applications by allowing you to retrieve information from fast, managed, in-memory caches, instead of relying entirely on slower disk-based databases.

ElasticCache supports two open-source in-memory caching engines:
    * Memcached
    * Redit

# Exam Tips
RDS (OLTP)
    * SQL
    * MySQL
    * PostgreSQL
    * Oracle
    * Aurora
    * MariaDB
DynamoDB (NoSQL)
Red Shift OLAP
Elasticache
    * Memcahed
    * Redis
Redshift for Business Intelligence or Data Warehousing
Elasticache to speed up performance of existing databases (frequent identical queries).

