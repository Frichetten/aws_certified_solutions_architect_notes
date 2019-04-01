## THIS LAB IS REALLY IMPORTANT
* EBS Volumes must be in the same availability zone as the EC2 Instance
* There is no downtime when upgrading an EBS volume

# Volumes & Snapshots
* Volumes exist on EBS:
    * Virtual Hard Disk
* Snapshots exist on S3
* Snapshots are point in time copies of Volumes
* Snapshots are incremental - this means that only the blocks that have changed since your last snapshot are moved to S3
* If this is your first snapshot is may take some time to create
* To create a snapshot for Amazon EBs volumes that serve as root devices, you should stop the instance before taking the snapshot
* However you can take a snap while the instance is running
* You can create AMI's from EBS-backed Instances and Snapshots
* You can change EBS volume sizes on the fly, including changing the size and storage type
* Volumes will ALWAYS be in the same availability zone as the EC2 instance.
* To move an EC2 volume from on AZ/Region to another take a snap or an image of it, then copy it to the new AZ/Region.

# Volumes & Snapshots - Security
* Snapshots of encrypted volumes are encrypted automatically
* Volumes restored from encrypted snapshots are encrypted automatically
* You can share snapshots, but only if they are unencrypted
    * These snapshots can be shared with other AWS acounts or made public