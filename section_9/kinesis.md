## What is Streaming Data
Streaming Data is data that is generated continuously by thousands of data sources, which typically send in the data records simultaneously, and in small sizes (order of Kilobytes).
* Purchases from online stores
* Stock Prices
* Game Data
* Social Network Data
* Geospatial Data
* iOT Sensor Data

## What is Kinesis
A platform to send streaming data to. Kinesis makes it easy to load and analyze streaming data, and also provides the ability for you to build your own custom applications for your business needs.

## 3 Different Types of Kinesis
* Kinesis Streams
* Kinesis Firehose
* Kinesis Analytics

# Kinesis Streams
* Can store the data for 24 Hours
* Can store it for up to 7 Days
## Kinesis Streams Consis of Shards
* 5 transactions per second for reads, up to a maximum total data read rate of 2 MB per second and up to 1000 records per second for writes, up to a maximum total data write rate of 1 MB per second.
* The data capacity of your stream is a function of the number of shards that you specify for the stream. The total capacity of the stream is the sum of the capacities of its shards.

# Kinesis Firehose
You have to do something with it the second you get it, you can't store it.

# Kinesis Analytics

# Exam Tips
* Know the difference between Kinesis Streams, and Kinesis Firehose. You will be given scenario questions and you must choose the most relevant service.
* Understand what Kinesis Analytics is.