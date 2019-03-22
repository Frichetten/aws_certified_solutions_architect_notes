# RAID, Volumes & Snapshots
* RAID = Redundant Array of Independent Disks
    * RAID 0 - Striped, No Redundancy, Good Performance
    * RAID 1 - Mirrored, Redundancy
    * RAID 5 - Good for reads, bad for writes, AWS does not recommend ever putting RAID 5's on EBS (Not recommended, trick question).
    * RAID 10 - Striped & Mirrored, Good Redundancy, Good Performance.
    
# How can I take a snapshot of a RAID array?
* Problem - Take a snapshot, the snapshot excludes data held in the cache by applications and the OS. This tends not to matter on a single volume, however using multiple volumes in a RAID array, this can be a problem due to interdependencies of the array

* Solution - Take an application consistent snapshot

* Stop the application from wirting to disk
* Flush all caches to the disk
* How can we do this?
    * Freeze the file system
    * Unmount the RAID Array
    * Shutting down the associated EC2 instance


    