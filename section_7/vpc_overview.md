Think of a VPC as a Virtual Data Center

AWS VPC lets you provision a logically isolated section ofthe AWS Cloud where you can launch AWS resources in a virtual network that you define.

# What can we do with a VPC
* Launch instances into a subnet of your choosing
* Configure route tables between subnets
* Create internet gateway and attach it to our VPC

# Default VPC vs Custom VPC
* Default VPC is user friendly, allowing you to immediately deploy instances
* All subnets in default VPC have a route out to the internet
* Each EC2 instance has both a public and private IP address

# VPC Peering
* Allows you to connect one VPC with another via a direct network route using private IP addresses
* Instances behave as if they were on the same private network
* You can peer VPC's with other AWS accounts as well as with other VPCs in the same account
* Peering is in a start configuration, ie 1 central VPC peers with 4 others.

# Exam Tips
* Think of a VPC as a logical datacenter in AWS
* Consists of IGWs (Or Virtual Private Gateways), route tables, network Access Control Lists, subnets, and security groups
* 1 subnet = 1 availability zone
* Security Groups are stateful; Network Access control Lists are stateless
* No transitive peering

