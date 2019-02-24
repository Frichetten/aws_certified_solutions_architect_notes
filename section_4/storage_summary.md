# S3 Exam Tips
* Remember that S3 is Object based storage
* Files can be from 0 Bytes to 5TB
* There is unlimited storage
* Files are stored in Buckets
* S3 is a universal namespace, that is names, must be unique globally
* https://s3-eu-west-1.amazonaws.com/acloudguru
* Read after Write consistency for PUTS of new Objects
* Eventual Consistency for overwrite PUTS and DELETES
* Remember the core fundamentals of S3:
    * Key (name)
    * Value (data)
    * Version ID
    * Metadata
    * Access Control Lists
* Object based storage only, not suitable for an operating system

# S3 - Storage Tiers
* S3 Standard: 99.99% availability. 11 9's durability. Designed to sustain the loss of 2 facilities concurrently.
* S3 - IA: For data that is accessed less frequently, but requires rapid access whe needed.
* S3 One Zone - IA: want a lower cost option for IA but do not require multiple AZ data resilience.
* Glacier: Very cheap, but used for archival only. Expedited, standard or bulk. A standard retrieval time takes 3 - 5 hours.

# S3 - Versioning
* Stores all versions of an object (including all writes and even if you delete an object)
* When you delete an object, it will not delete it, it will give it a delete marker.
* Once enabled, Versioning cannot be disabled, only suspended.
* Integrates with Lifecycle rules
* Versioning's MFA Delete capability which uses multi-factor authentication, can be used to provide an additional layer of security.
* Cross Region Replication, requires versioning enabled on the source bucket and the destination bucket

# S3 - Lifecycle Management
* Can be used in conjunction with versioning
* Can be applied to current versions and previous versions
* Following actions can now be done
    * Transition to the Standard - IA Storage Class
    * Archive to the Glacier Storage Class
    * Permanently Delete

# CloudFront - Exam Tips
* Edge Location - This is the location where content will be cached. This is separate from an AWS Region/AZ
* Origin- This is the origin of all the files that the CDN will distribute
* Distribution - This is the name given to the CDN which consists of a collection of Edge Locations
    * Web Distributions - Typically used for Websites
    * RTMP - Used for Media Streaming
* Edge Locations are not just READ only, you can write to them too.
* Objects are cached for the life of the TTL
* You can clear cached objects but you will be charged

# Securing your Buckets
* By default, all newly created buckets are PRIVATE
* You can setup access control to your buckets using:
    * Bucket Policies
    * ACLs
* S3 Buckets can be configured to create access logs which log all requests made to the S3 bucket. This can be done to another bucket.

# Encryption
* In transit
    * SSL/TLS
* At Rest:
    * Server Side Encryption
        * S3 Managed Keys - SSE-S3
        * AWS Key Management Service, Managed Keys - SSE-KMS
        * Server Side Encryption with Customer Provided Keys - SSE-C
    * Client Side Encryption

# Storage Gateway
* File Gateway - For flat files, stored in S3
* Volume Gateway
    * Stored Volumes - Entire Dataset is stored on site and is asynchronously backed up to S3
    * Cached Volumes - Entire Dataset is stored on S3 and the most frequently accessed data is cached on site.
* Gateway Virtual Tape Library (VTL)
    * Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc.

# Snowball
* Snowball
* Snowball Edge
* Snowmobile
* Understand what Snowball is
* Understand what Import/Export is
* Snowball Can
    * Import to S3
    * Export from S3

# S3 Transfer Acceleration
* You can speed up transfers to S3 using S3 transfer acceleration

# S3 Static Websites
* You can use S3 to host static websites
* Serverless
* Very Cheap, scales automatically
* STATIC only, cannot host dynamic sites

# Last few tips
* Write to S3 - HTTP 200 code for successful write.
* You can load files to S3 much faster by enabling multipart upload
* Read the S3 FAQ before taking the exam. It comes up a LOT!
    