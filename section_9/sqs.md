## What is SQS
A web service that gives you access to a message queue that can be used to store messages while waiting for a computer to process them.

Using Amazon SQS you can decouple the componeents of an application so they run independently, easing message management between components. Any component of a distributed application can store messages in a fail-safe queue. Messages can contain up to 256 KB of text in any format. Any component can later retrieve the messages programmatically using the Amazon SQS API.

The queue acts as a buffer between the component producing and saving data, and the component receiving the data for processing. This means the queue resolves issues that arise if the producer is producing work faster than the consumer can process it, or if the producer or consumer are only intermittently connected to the network.

## There are Two types of Queue
* Standard Queues (default)
* FIFO

# Exam Tips
* SQS is pull based, not pushed based.
* Messages are 256 KB in size (can go up to 2 GB)
* Messages can be kept in the queue from 1 minute to 14 days; the default retention period is 4 days.
* Visibility Time Out is the amount of time that the message is invisible in the SQS queue after a reader picks up that message. Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue. If the job is not processed within that time, the message will become visible again and another reader will process it. This could result in the same message being delivered twice.
* Visibility timeout maximum is 12 hours. 
* SQS guarantees that your messages will be processed at least once.
* Amazon SQS long polling is a way t oretrieve messages from your Amazon SQS queues. While the regular short polling return immediately (even if the message queue being polled is empty), long polling doesn't return a response until a message arrives in the message queue, or the long poll times out.