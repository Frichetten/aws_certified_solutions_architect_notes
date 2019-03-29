# Lambda - The Basics
## Lambda is the Ultimate Extraction Layer
* Data Centres
* Hardware
* Assembly Code/Protocols
* High Level Languages
* Operating Systems
* Application Layer/AWS APIs
* AWS Lambda

AWS Lambda is a compute service where you can upload your code and create a Lambda function. AWS Lambda takes care of everything for you.

## You can use Lambda in the following ways
* As an event-driven compute service where AWS Lambda runs your code in response to events. These events could be changes to data in an Amazon S3 bucket or an Amazon DynamoDB table.
* As a compute service to run your code in response to HTTP requests using Amazon API Gateway or API calls made using AWS SDKs. This is what we use at A Cloud Guru.

## What Languages Does Lambda Support
* Node.js
* Java
* Python
* C#
* Go
* PowerShell

## How is Lambda Priced
1. Number of Requests
2. Duration

## Why is Lambda Cool?
* NO SERVERS!
* Continuous Scaling
* Super Super Super Cheap!

# Exam Tips
* Lambda scales out (not up) automatically
* Lambda Functions are independent, 1 event = 1 function
* Lambda is serverless
* Know what services are serverless!
* Lambda functions can trigger other lambda functions, 1 event can = x functions if functions trigger other functions
* Architectures can get extremely complicated, AWS X-ray allows you to debug what is happening.
* Lambda can do things globally, you can use it to back up S3 buckets to other S3 buckets, etc.
* Know the triggers. (Memorize them).