# Exam Tips - SQS
* SQS is a way to de-couple your infrastructure
* SQS is pull based, not pushed based
* Messages are 256 KB in size
* Messages can be kept in the queue from 1 minute to 14 days; the default retention period is 4 days.
* 2 Types: Standard SQS and FIFO SQS
    * Standard: Order is not guaranteed and messages can be delivered more than once
    * FIFO: order is strictly maintained and messages are delivered only once.
* Visibility Time Out is the amount of time that the message is invisible in the SQS queue after a reader picks up that message. Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue. If the job is not processed within that time, the message will become visible again and another reader will process it. This could result in the same message bring delivered twice.
* Visibility timeout maximum is 12 hours
* SQS guarantees that your messages will be processed at least once
* Amazon SQS long polling is a way to retrieve messages from your Amazon SQS queues. While the regular short polling returns immediately (even if the message queue being polled is empty), long polling doesn't return a response until a message arrives in the message queue, or the long pull times out.
## SWF vs SQS
* SQS has a retention period of up to 14 days; with SWF, workflow executions can last up to 1 year. 
* Amazon SWF presents a task-oriented API, whereas Amazon SQS offers a message-oriented API.
* Amazon SWF ensures that a task is assigned only once and is never duplicated. With Amazon SQS, you need to handle duplicated messages and may also need to ensure that a message is processed only once.
* Amazon SWF keeps track of all the tasks and events in an application. With Amazon SQS, you need to implement your own application-level tracking, especially if your application uses multiple queues.
## SWF Actors - Exam Tips
* Workflow Starters - An application that can initiate (start) a workflow. Could be your e-commerce website following the placement of an order, or a mobile app searching for bus times.
* Deciders - Control the flow of activity tasks in a workflow execution. If somethign has finished (or failed) in a workflow, a Decider decides what to do next.
* Activity Workers - Carry out the activity tasks.
# SNS
* Instaneous, push-based delivery (no polling)
* Simple APIs and easy integration with applications
* Flexible message delivery over multiple transport protocols
* Inexpensive, pay as you go model with no up-front costs
* Web based AWS Management Console offers the simplicity of a point and click interface

## SNS vs SQS
* Both messaging services in AWS
* SNS - Push
* SQS - Polls (Pulls)

# Elastic Transcoder
Just remember that Elastic Transcoder is a media transcoder in the cloud. It converts media files from their original source format in to different formats that will play on smartphones, tablets, PCs, and etc.

# API Gateway
* Remember what API Gateway is at a high level
* API Gateway has caching capabilities to increase performance
* API Gateway is low cost and scales automatically
* You can throttle API Gateway to prevent attacks
* You can log results to CloudWatch
* If you are using Javascript/AJAX that uses multipel domains with API Gateway, ensure that you have enabled CORS on API Gateway
* CORS is enforced by the client

# Kinesis
* Know the difference between Kinesis Streams and Kinesis Firehose. 
* Understand what Kinesis Analytics is. 