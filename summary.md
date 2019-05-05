* Reliability: The probability that a system will work as designed
* Availability: The probability that a system will be available
* Durability: The ongoing existence of the object or resource

# S3 & IAM Summary
### IAM
* Identity Access Management Consists of the Following:
    * Users
    * Groups
    * Roles
    * Policies
* IAM is universal. It does not apply to regions
* The "root account" is simply the account created when first setup your AWS account. It has complete Admin access.
* New Users have NO permissions when first created.
* New USers are assigned Access Key ID & Secret Access Keys when frist created.
* You cannot use the Access key ID & Secret Access Key to Login to the console.
* You only get to view your Access keys once. If you lose them you have to create new ones.
* You can create and customise your own password rotation policies.

### S3
* S3 is Object-Based: Allows you to upload files
* Files can be from 0 Bytes to 5 TB
* There is unlimited storage
* Files are stored in Buckets
* S3 is a universal namespace, bucket names must be unique globally
* https://s3-eu-west-1.amazonaws.com/bucketname
* Not suitable to install an operating system on
* Successful uploads will generate a HTTP 200 status code
* By default all newly created buckets are PRIVATE
* You can setup access control to your buckets using:
    * Bucket Policies
    * Access Control Lists
* S3 Buckets can be configured to create access logs
* S3 fundamentals:
    * Key (The name of the object)
    * Value (The file data)
    * Version ID (Versioning)
    * Metadata (Data about data)
    * Subresources:
        * Access Control Lists
        * Torrent
* Read after Write consistency for PUTS of new Objects
* Eventual Consistency for overwrite PUTS and DELETES (can take time to propogate)
* Types of S3
    * S3 Standard
        * 99.99% Availability
        * 99.99999999999% durability
        * Stored redundantly across multiple devices in multiple facilities, and is designed to sustain the loss of 2 facilities concurrently
    * S3 IA
        * For data that is access less frequently, but requires rapid access when needed. Lower fee than S3, but you are charged a retrieval fee.
    * S3 One Zone - IA
        * For when you want a lower cost option for infrequently accessed data, but do not require the multiple Availability Zone data resilience.
    * S3 Intelligent Tiering
        * Designed to optimize costs by automatically moving data to the most cost-effective access tier, without performance impact or operational overhead
    * S3 Glacier
        * S3 Glacier is a secure, durable, and low-cost storage class for data archiving. Retrieval times configurable from minutes to hours.
    * S3 Glacier Deep Archive
        * S3 Glacier Deep Archive is Amazon S3's lowest-cost storage class where a retrieval time of 12 hours is acceptable.
* Encryption in Transit is achieved by:
    * SSL/TLS
* Encryption At Rest (Server Side) is achieved by:
    * S3 Managed Keys - SSE-S3
    * AWS Key Management Service, Managed Keys - SSE-KMS
    * Server Side Encryption with Customer Provided keys - SSE-C
* Client Side Encryption:
    * Encrypt it client side and move it to S3
* Cross Region Replication
    * Versioning must be enabled on both the source and destination buckets.
    * Regions must be unique
    * Files in an existing bucket are not replicated automatically
    * All subsequent updated files will be replicated automatically
    * Delete markers are not replicated
    * Deleting individual version or delete markers will not be replicated
* Lifecycle Policies
    * Automates moving your objects between the different storage tiers
    * Can be used in conjunction with versioning
    * Can be applied to current versions and previous versions
* Cloudfront
    * Edge Location - This is the location where content will be cached. This is separate to an AWS Region/AZ
    * Origin - This is the origin of all the files that the CDN will distribute.  This can either be an S3 Buckets, an EC2 Instance, an Elastic Load Balancer, or Route53.
    * Distribution - This is the name given to the CDN which consists of a collection of Edge Locations.
    * Web Distribution - Typically used for Websites
    * RTMP - Used for Media Streaming
* Edge Locations are not just READ only - you can write to them too
* Objects are cached for the life of the TTL
* You can clear cached objects, but you will be charged
* Storage Gateway
    * File Gateway
        * For flat files, sotred directly on S3
    * Volume Gateway
        * Entire Dataset is stored on site and is asynchronously backed up to S3
    * Cached Volumes
        * Entire Dataset is stored on S3 and the most frequently accessed data is cached on site.
    * Gateway Virtual Tape Library
        * Used for backup and uses popular backup applications

# EC2 Summary
### EC2 Exam Tips
EC2 is a web service that provides resizable compute capacity in the cloud. Amazon EC2 reducates the time required to obtain and boot new server instances to minutes, allowing you to quickly scal capacity, both up and down, as your computing requirements change.

1. On Demand - allows you to pay a fixed rate by the hour (or by the second) with no commitment.
2. Reserved - Provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance. Contract Terms are 1 Year or 3 Year Terms.
3. Spot - Enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications have flexible start and end times.
4. Dedicated Hosts - Physical EC2 server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses.

If the Spot instance is terminated by Amazon EC2, you will not be charged for a partial hour of usage. However, if you terminate the instance yourself, you will be charged for any hour in which the instance ran.

#### EC2 Instance Types
FIGHT DR MCPXZ AU

#### EBS
* Termination Protection is turned off by default, you must turn it on.
* On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated.
* EBS root volumes of your default AMI's cannot be encrypted. You can also use a third party tool to encrypt the root volume, or this can be done when creating AMI's in the AWS console or using the API.
* Additional volumes can be encrypted.

#### Security Groups
* All inbound traffic is blocked by default
* All outbound traffic is allowed.
* Changes to Security Groups take effect immediately
* You can have any number of EC2 instances within a security group
* You can have multiple security groups attached to EC2 Instances
* Security Groups are STATEFUL
* Network ACLs are STATELESS
* If you create an inbound rule allowing traffic in, that traffic is automatically allowed back out again.
* You cannot block specific IP addresses using Security Groups, instead use Network Access Control lists.
* You can specify allow rules, but not deny rules

#### EBS Snapshots
* Volumes exist on EBS. Think of EBS as a virtual hard disk
* Snapshots exist on S3. Think of snapshots as a photograph of the disk
* Snapshots are point in time copies of Volumes
* Snapshots are incremental - this means that only the blocks that have changed since your last snapshot are moved to S3
* If this is your first snapshot, it may take some time to create
* To create a snapshot for Amazon EBS volumes that serve as root devices, you should stop the isntance before taking the snapshot
* However you can take a snap while the instance is running
* You can create AMI's from both Volumes and Snapshots
* You can change the EBS volume sizes on the fly, including changing the size and storage type.
* Volumes will ALWAYS be in the same availability zone as the EC2 instance.

#### Migrating EBS
* To move an EC2 volume from one AZ to another, take a snapshot of it, create an AMI from the snapshot and then use the AMI to launch the EC2 instance in a new AZ.
* To move an EC2 volume from one region to another, take a snapshot of it, create an AMI from the snapshot and then copy the AMI from one region to the other. Then use the copied AMI to launch the new EC2 instance in the new region.

#### EBS Encryption
* Snapshots of encrypted volumes are encrypted automatically
* Volumes restored from encrypted snapshots are encrypted automatically
* You can share snapshots, but only if they are unencrypted
* These snapshots can be shared with other AWS accounts or made public

#### EBS vs Instance Store
* Instance Store Volumes are sometimes called Ephemeral Storage
* Instance Store Volumes cannot be stopped. If the underlying host fails, you will lose your data.
* EBS backed instances can be stopped. You will not lose the data on this instance if it is stopped.
* You can reboot both, you will not lose your data
* By default both ROOT volumes will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volume.

#### Encrypting Root Device Volumes
* Create a snapshot of the unencrypted root device volume
* Create a copy of the Snapshot and select the encrypt option
* Create an AMI from the encrypted Snapshot
* Use that AMI to launch new encrypted instances

#### CloudWatch
* CloudWatch is used for monitoring performance
* CloudWatch can monitor most of AWS as well as your applications that run on AWS.
* CloudWatch with EC2 will monitor events every 5 minutes by default
* You can have 1 minute intervals by turning on detailed monitoring
* You can create CloudWatch alarms which trigger notifications
* Cloud watch is all about performance. CloudTrail is all about auditing
##### What can I do with CloudWatch
* Dashboards - Creates awesome dashboards to see what is happening with your AWS environment
* Alarms - Allows you to set Alarms that notify you when particular thresholds are hit.
* Events - CloudWatch Events helps you to respond to state changes in your AWS resources.
* Logs - CloudWatch Logs helps you to aggregate, monitor, and store logs.

#### CloudTrail vs CloudWatch
* CloudWatch monitors Performance
* CloudTrail monitors API calls in the AWS platform

#### The CLI
* You can interact with AWS from anywhere in the world just by using the command line
* You will need to set up access in IAM
* Commands themselves are not in the exam, but some basic commands will be useful to know for real life

#### Roles
* Roles are more secure than storing your access key and secret access key on individual EC2 instances.
* Roles are easier to manage.
* Roles can be assigned to an EC2 instance after it is created using both the console and the command line
* Roles are universal - you can use them in any region.

#### BootStrap Scripts
* Bootstrap scripts run when an EC2 instance first boots.
* can be a powerful way of automating software installs and updates

#### Instance MetaData & User Data
* Used to get information about an instance (such as public ip)
* curl http://169.254.169.254/latest/meta-data
* curl http://169.254.169.254/latest/user-data

#### EFS
* Supports the Network File System version 4 protocol
* You only pay fro the storage you use
* Can scale up to petabytes
* Can support thousands of concurrent NFS connections
* Data is stored across multiple AZ's within a region
* Read After Write Consistency

#### EC2 Placement Groups
Two Types of Placement Groups:
    * Clustered Placement Group
    * Spread Placement Group
* Clustered placement group can't span multiple AZ
* A spread placement group can span multiple AZ
* The name you specify for a placement group must be unique within your AWS account
* Only certian types of instances can be launched in a placement group (Compute Optimized, GPU, Memory Optimized, Storage Optimized)
* AWS recommended homogenous instances within placement groups
* You can't merge placement groups.
* You can move an existing instance into a placement group. You can create an AMI from your existing instance, and then launch a new instance from the AMI into a placement group

# Database Summary
RDS (OLTP)
* SQL
* MySQL
* PostgreSQL
* Oracle
* Aurora
* MariaDB

DynamoDB(NoSQL)

RedShift (OLAP)

#### Elasticache
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

#### Read Replicas
* Can be Multi-AZ
* Used to increase performance
* Must have backups turned on
* Can be in different regions
* Can be Aurora or MySQL
* Can be promoted to master, this will break the replication with the Read Replica.

#### MultiAZ
* Used for Date Recovery.
* You can force a failover from one AZ to another by rebooting the RDS instance

Encryption is supported for all RDS. Encryption is done using the AWS KMS service. Once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots.

#### DynamoDB
* Stored on SSD Storage
* Spread across 3 geographically distinct data acenters
* Eventual Consistent Reads (Default)
* Strongly Consistent Reads

#### Redshift
* Redshift is used for business intelligence
* Available in only 1 AZ

#### Redshift Backups
* Enabled by default with a 1 day retention period
* Maximum retention period is 35 days
* Redshift always attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in Amazon S3)
* Redshift can also asynchronously replicate your snapshots to S3 in another region for disaster recovery.

#### Aurora
* 2 copies of your data is contained in each availability zone, with minimum of 3 availability zones. 6 copies of your data.
* You can share Aurora Snapshots with other AWS accounts
* 2 types of replicas available. Aurora Replicas and MySQL replicas. Automated failover is only available with Aurora Replicas.
* Aurora has automated backups turned on by default. You can also take Snapshots with Aurora. You can share these snapshots with other AWS accounts.

#### Elasticache
* Use Elasticache to increase database and web application performance
* Reddis is Multi-AZ
* You can do backups and restores of Reddis
* If you need to scale horizontally, use Memcached

# DNS Summary
#### Route 53 Exam Tips
* ELBs do not have pre-defined IPv4 addresses; you resolve to them using a DNS name
* Understand the difference between an Alias Record and a CNAME
* Given the choice, always choose an Alias Record over a CNAME

#### Common DNS Types
* SOA Records
* NS Records
* A Records
* CNAMES
* MX Records
* PTR Records

#### Routing Policies
* Simple Routing
* Weighted Routing
* Latency-based Routing
* Failover Routing
* Geolocation Routing
* Geoproximity Routing
* Multivalue Answer Routing

#### Health Checks
* You can set health checks on individual record sets
* If a record set fails a health check it will be removed from Route53 until it passes the health check
* You can set SNS notifications to alert you if a health check is failed

* Simple Routing Policy
* Weighted Routing Policy
* Latency Routing Policy
* Failover Routing Policy
* Geolocation Routing
* Geoproximity Routing
* Multivalue Answer Routing

# VPC Summary
* Think of a VPC as a logical datacenter in AWS.
* Consists of IGWs (Or Vitrual Private Gateways), Route Tables, Network Access Control Lists, Subnets, and Security Groups
* 1 Subnet = 1 Availability Zone
* Security Groups are Stateful; Network Access Control Lists are Stateless
* No Transitive Peering

#### Building our VPC
* When you create a VPC a default Route Table, Network Access Control List (NACL) and a default Security Group
* It won't create any subnets, nor will it create a default internet gateway.
* US-East-1A in your AWS account can be completely different availability zone to US-East-1A in another AWS account. The AZ's are randomized.
* Amazon always reserve 5 IP addresses within your subnets
* You can only have 1 Internet Gateway per VPC
* Security Groups cannot span VPCs

#### NAT Instances vs NAT Gateways
##### Nat Instances Exam Tips
* When creating a Nat Instance, Disable Source/Destination Check on the Instance
* NAT Instances must be in a public subnet.
* There must be a route out of the private subnet to the NAT instance, in order for this to work.
* The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
* You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover
* Behind a Security Group

#### NAT Gateways
* Redundant inside the Availability Zone
* Preferred by the enterprise
* Starts at 5Gbps and scales currently to 45Gbps
* No need to patch
* Automatically assigned a public ip address
* Remember to update your route tables
* No need to disable Source/Destination checks
* If you have resources in multiple AZs and they share one NAT Gateway, in the event that the NAT gateway's Availability Zone is down, resources in the other AZs lose internet access. To create an AZ independent architecture, create a NAT gateway in each AZ and configure your routing to ensure that resources use the NAT gateway in the same AZ.

#### Network ACLs
* Your VPC automatically comes with a default network ACL, and by default it allows all outbound and inbound traffic
* You can create custom network ACLs. By default, each customer network ACL denies all inbound and outbound traffic until you add rules.
* Each subnet in your VPC must be associated with a network ACL. If you don't explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default network ACL.
* Block IP Addresses using network ACLs not Security Groups
* You can associate a network ACL wiht multiple subnets; however a subnet can be associated with only one network at a time. When you associate a network ACL with a subnet, the previous association is removed.
* Network ACLs contain a numbered list of rules that is evaluated in order, starting with the lowest numbered rule.
* Network ACLs have separate inbound and outbound rules, and each rule can either allow or deny traffic.
* Network ACLs are stateless; responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa).

#### ELBs and VPCs
* You need a minimum of two public subnets to deploy an internet facing loadbalancer.

#### VPC Flow Logs
* You cannot enable VPC flow logs for VPCs that are peered with your VPC unless the peer VPC is in your account
* You cannot tag a flow log
* After you've created a flow log, you cannot change its configuration; for example; you can't associate a different IAM role with the flow log.
* Traffic generated by instances when they contact the Amazon DNS server. If you use your own DNS server, than all traffic to that DNS server is logged. 
* Traffic generated by a Windows instance for Amazon Windows license activation
* Traffic to and from 169.254.169.254 for instance metadata.
* DHCP traffic
* Traffic to the reserved IP address for the default VPC router

#### Bastion Host
* A NAT Gatewaay or NAT instance is used to provide internet traffic to EC2 instances in a private subnet
* A Bastion is used to securely administer EC2 Instances ( Using SSH or RDP). Bastions are called jump boxes in Australia
* You cannot use a NAT Gateway as a Bastion Host

#### Direct Connect
* Direct Connect directly connects your data center to AWS
* Useful for high throughput workloads
* Or if you need a stable and reliable secure connection

#### VPC Endpoints
- Copy description here -
##### Two types of Endpoints
* Interface Endpoints
* Gateway Endpoints
##### Two Gateway Endpoints
* S3
* DynamoDB

# High Availability Summary
#### 3 Different Types of Load Balancers
* Application Load Balancers
* Network Load Balancers
* Classic Load Balancers

* 504 Error means the gateway has timed out. This means that the application not responding within the idle timeout period

* Troubleshoot the application. Is it the Web Server or Database Server?

* If you need the IPv4 address of your end user, look for the X-Forwarded-For header.

* Instances monitored by ELB are reported as InService or OutofService
* Health Checks check the instance health by talking to it
* Load Balancers have their own DNS name. You are never given an IP address
* Read the ELB FAQ for each Load Balancer

#### CloudFormation
* Is a way of completely scripting your cloud environment
* Quick Start is a bunch of CloudFormation templates already built by AWS Solutions Architects allowing you to create complex environments very quickly

# Applications Summary
#### SQS
* SQS is a way to de-couple your infrastructure
* SQS is pull based, not pushed based
* Messages are 256 KB in size
* Messages can be kept in the queue from 1 minute to 14 days; the default retention period is 4 days.
* 2 Types: Standard SQS and FIFO SQS
    * Standard: Order is not guaranteed and messages can be delivered more than once
    * FIFO: order is strictly maintained and messages are delivered only once.
* Visibility Time Out is the amount of time that the message is invisible in the SQS queue after a reader picks up that message. Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue. If the job is not processed within that time, the message will become visible again and another reader will process it. This could result in the same message bring delivered twice.
* Visibility timeout maximum is 12 hours
* SQS guarantees that your messages will be processed at least once
* Amazon SQS long polling is a way to retrieve messages from your Amazon SQS queues. While the regular short polling returns immediately (even if the message queue being polled is empty), long polling doesn't return a response until a message arrives in the message queue, or the long pull times out.
#### SWF vs SQS
* SQS has a retention period of up to 14 days; with SWF, workflow executions can last up to 1 year. 
* Amazon SWF presents a task-oriented API, whereas Amazon SQS offers a message-oriented API.
* Amazon SWF ensures that a task is assigned only once and is never duplicated. With Amazon SQS, you need to handle duplicated messages and may also need to ensure that a message is processed only once.
* Amazon SWF keeps track of all the tasks and events in an application. With Amazon SQS, you need to implement your own application-level tracking, especially if your application uses multiple queues.
#### SWF Actors - Exam Tips
* Workflow Starters - An application that can initiate (start) a workflow. Could be your e-commerce website following the placement of an order, or a mobile app searching for bus times.
* Deciders - Control the flow of activity tasks in a workflow execution. If somethign has finished (or failed) in a workflow, a Decider decides what to do next.
* Activity Workers - Carry out the activity tasks.
#### SNS
* Instaneous, push-based delivery (no polling)
* Simple APIs and easy integration with applications
* Flexible message delivery over multiple transport protocols
* Inexpensive, pay as you go model with no up-front costs
* Web based AWS Management Console offers the simplicity of a point and click interface

#### SNS vs SQS
* Both messaging services in AWS
* SNS - Push
* SQS - Polls (Pulls)

#### Elastic Transcoder
Just remember that Elastic Transcoder is a media transcoder in the cloud. It converts media files from their original source format in to different formats that will play on smartphones, tablets, PCs, and etc.

#### API Gateway
* Remember what API Gateway is at a high level
* API Gateway has caching capabilities to increase performance
* API Gateway is low cost and scales automatically
* You can throttle API Gateway to prevent attacks
* You can log results to CloudWatch
* If you are using Javascript/AJAX that uses multipel domains with API Gateway, ensure that you have enabled CORS on API Gateway
* CORS is enforced by the client

#### Kinesis
* Know the difference between Kinesis Streams and Kinesis Firehose. 
* Understand what Kinesis Analytics is. 

#### Cognito
* Federation allows users to authenticate with a Web Identity Provider
* The user authenticates first with the Web ID Provider and receives an authentication token, which is exchanged for temporary AWS credentials allowing them to assume an IAM role.
* Cognito is an Identity Broker which handles interaction between your applications and the Web ID provider
* User pool is user based. It handles things like user registration, authentication, and account recovery.
* Identity pools authorise access to your AWS resources.

# Serverless Summary
* Lambda scales out (not up) automatically
* Lambda functions are independent, 1 event = 1 function
* Lambda is serverless
* Know what services are serverless
* Lambda functions can trigger other lambda functions, 1 event can = x functions if functions trigger other functions
* Architectures can get extremely complicated, AWS X-ray allows you to debug what is happening 
* Lambda can do things globally, you can use it to back up S3 buckets to other S3 buckets, etc
* Know your triggers