# Encrypted Root Device Volumes & Snapshots
* To create a snapshot for Amazon EBS Volumes that serve as root devices, you should stop the isntance before taking the snapshot.
* Snapshots of encrypted volumes are encrypted automatically.
* Volumes restored from encrypted snapshots are encrypted automatically.
* You can share snapshots, but only if they are unencrypted.
    * These snapshots can be shared with other AWS accounts or made public.
