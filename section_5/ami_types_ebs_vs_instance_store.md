# You can select your AMI based on 
* Region
* Operating System
* Architecture
* Launch Permissions
* Storage for the Root device
    * Instance Store
    * EBS back volumes

# EBS vs Instance Store
* All AMIs are categorized as either backed by Amazon EBS or backed by instance store.
* For EBS Volumes: The root device for an instance launched from the AMI is an Amazon EBS volume created from an Amazon EBS snapshot
* For Instance Store Volumes: The root device for an isntance launched from the AMI is an instance store volume created from a template stored in Amazon S3.

# Exam Tips
* Instance Store Volumes are sometimes called Ephemeral Storage.
* Instance store Volumes cannot be stopped. If the underlyin host fail,s you will lose your data.
* EBS backed instances can be stopped. You will not lose the data on this isntance if it is stopped.
* You can reboot both, you will not lose your data.
* By default both ROOT volumes will be deleted on termination, however with EBS volumes you can tell AWS to keep the root device volumes.