* What is a CDN
    * A content delivery network is a system of distributed servers that delivar webpages and other web content.

# Cloudfront Key Terminology
* Edge Location - This is the location where content will be cached. This is separate to an AWS Region/AZ
* Origin - This is the origin of all the files that the CDN will distribute. This can be either an S3 Bucket, an EC2 Instance, an Elastic Load Balancer or Route53
* Distribution - This is the name given to the CDN which consists of a collection of Edge Locations

# What is CloudFront
Amazon CloudFront can be used to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations. Requests for your content are automatically routed to the nearest edge location, so content is delivered with the best possible performance.

Amazon CloudFront is optimized to work with other Amazon Web Services, like S3 EC2, ELB, and Route53. Amazon CloudFront also works seamlessly with any non-AWS origin server, which stores the original, definiteive versions of your files.

* Web Distribtuon - Typically used for websites.
* RTMP - Used for Media Streaming.

# Exam Tips
* Edge Location - This is the location where content will be cached. This is separate to an AWS Region/AZ
* Origin - This is the origin of all the files that the CDN will distribute. This can be either an S3 Bucket, an EC2 Instance, an Elastic Load Balancer or Route53.
* Distribution - This is the name given the CDN which consists of a collection of Edge Locations.
    * Web Distribution - Typically used for websites
    * RTMP - Used for Media streaming
* Edge locations are not just READ only, you can write to them too. 
* Objects are cached for the life of the TTL (Time To Live).
* You can clear cached objects, but you will be charged.
