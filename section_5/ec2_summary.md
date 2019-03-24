EC2 is a web service that provides resizable compute capacity in the cloud. Amazon EC2 reducates the time required to obtain and boot new server instances to minutes, allowing you to quickly scal capacity, both up and down, as your computing requirements change.

1. On Demand - allows you to pay a fixed rate by the hour (or by the second) with no commitment.
2. Reserved - Provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance. Contract Terms are 1 Year or 3 Year Terms.
3. Spot - Enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications have flexible start and end times.
4. Dedicated Hosts - Physical EC2 server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses.

If the Spot instance is terminated by Amazon EC2, you will not be charged for a partial hour of usage. However, if you terminate the instance yourself, you will be charged for any hour in which the instance ran.

# EC2 Instance Types
FIGHT DR MCPXZ AU

# EBS
* Termination Protection is turned off by default, you must turn it on.
* On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated.
* EBS root volumes of your default AMI's cannot be encrypted. You can also use a third party tool to encrypt the root volume, or this can be done when creating AMI's in the AWS console or using the API.
* Additional volumes can be encrypted.

# Security Groups
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

# EBS Snapshots
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

# Migrating EBS
* To move an EC2 volume from one AZ to another, take a snapshot of it, create an AMI from the snapshot and then use the AMI to launch the EC2 instance in a new AZ.
* To move an EV2 volume from one region to another, take a snapshot of it, create an AMI from the snapshot and then copy the AMI from one region to the other. Then use the copied AMI to launch the new EC2 instance in the new region.

# EBS Encryption
* Snapshots of encrypted volumes are encrypted automatically
* Volumes restored from encrypted snapshots are encrypted automatically
* You can share snapshots, but only if they are unencrypted
* These snapshots can be shared with other AWS accounts or made public

# EBS vs Instance Store
* Instance Store Volumes are sometimes called Ephemeral Storage
* Instance Store Volumes cannot be stopped. If the underlying host fails, you will lose your data.
* EBS backed instances can be stopped. You will not lose the data on this instance if it is stopped.
* You can reboot both, you will not lose your data
* By default both ROOT volumes will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volume.

# Encrypting Root Device Volumes
* Create a snapshot of the unencrypted root device volume
* Create a copy of the Snapshot and select the encrypt option
* Create an AMI from the encrypted Snapshot
* Use that AMI to launch new encrypted instances

# CloudWatch
* CloudWatch is used for monitoring performance
* CloudWatch can monitor most of AWS as well as your applications that run on AWS.
* CloudWatch with EC2 will monitor events every 5 minutes by default
* You can have 1 minute intervals by turning on detailed monitoring
* You can create CloudWatch alarms which trigger notifications
* Cloud watch is all about performance. CloudTrail is all about auditing
## What can I do with CloudWatch
* Dashboards - Creates awesome dashboard to see what is happening with your AWS environment
* Alarms - Allows you to set Alarms that notify you when particular thresholds are hit.
* Events - CloudWatch Events helps you to respond to state changes in your AWS resources.
* Logs - CloudWatch Logs helps you to aggregate, monitor, and store logs.

# CloudTrail vs CloudWatch
* CloudWatch monitors Performance
* CloudTrail monitors API calls in the AWS platform

# The CLI
* You can interact with AWS from anywhere in the world just by using the command line
* You will need to set up access in IAM
* Commands themselves are not in the exam, but some basic commands will be useful to know for real life

# Roles
* Roles are more secure than storing your access key and secret access key on individual EC2 instances.
* Roles are easier to manage.
* Roles can be assigned to an EC2 instance after it is created using both the console and the command line
* Roles are universal - you can use them in any region.

# BootStrap Scripts
* Bootstrap scripts run when an EC2 instance first boots.
* can be a powerful way of automating software installs and updates

# Instance MetaData & User Data
* Used to get information about an instance (such as public ip)
* curl http://169.254.169.254/latest/meta-data
* curl http://169.254.169.254/latest/user-data

# EFS
* Supports the Network File System version 4 protocol
* You only pay fro the storage you use
* Can scale up to petabytes
* Can support thousands of concurrent NFS connections
* Data is stored across multiple AZ's within a region
* Read After Write Consistency