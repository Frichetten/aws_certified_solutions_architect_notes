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

