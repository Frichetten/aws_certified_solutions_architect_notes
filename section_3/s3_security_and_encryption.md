# Securing your buckets
* By default all newly created buckets are private
* You can setup access control to your buckets using
    * Bucket Policies
    * Access Control Lists
* S3 Buckets can be configured to create access logs which log all requests made to the S3 bucket. This can be done to another bucket.

# Encryption
* In transit
    * SSL/TLS
* At rest
    * Server Side Encryption
        * S3 Managed Keys - SSE-S3
        * AWS Key Management Service, Managed Keys - SSE-KMS
        * Server Side Encryption with Customer Provided Keys - SSE-C
    * Client Side Encryption