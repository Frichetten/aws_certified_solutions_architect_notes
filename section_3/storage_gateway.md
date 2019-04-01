# Storage Gateway
A service that connects an on-premise software appliance with cloud-based storage to provide seamless and secure integration between an organizations on-premise IT environment and AWS's storage infrastructure. The service enables you to securely store data to the AWS cloud for scalable and cost-effective storage.

AWS Storage Gateway's software appliance is available for download as a virtual machine image that you install.

# Four Types of Storage Gateways
* File Gateway (NFS)
* Volume Gateway (iSCSI)
    * Stored Volumes
    * Cached Volumes
* Tape Gateway (VTL)

# File Gateway
Files are stored as objects in your S3 buckets, accessed through a Network File System mount point. Ownership, permissions, and timestamps are durably stored in S3. 

# Volume Gateway
The volume interface presents your applications with disk volumes.
Data written to these volumes can be asynchronously backed up as a point in time snapshots of your volumes. Stored as EBS snapshots.

## Stored Volumes
Stored volumes let you store your primary data locally, while asynchronously backing up that data to AWS. 

## Cached Volumes
Cached Volumes let you use Amazon Simple Storage Service as your primary data storage while retaining frequently accessed data locally in your storage gateway.

## Tape Gateway
Tape Gateway offers a durable, cost-effective solution to archive your data in the AWS Cloud.

# Exam Tips
* File Gateway- For flat files, stored directly on S3
* Volume Gateway
    * Stored Volumes - Entire Dataset is stored on site and is asynchronously backed up to S3
    * Cached Volumes - Entire dataset is stored on S3 and the most frequently accessed data is cached on site.
* Gateway Virtual Tape Library (VTL)
    * Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc.