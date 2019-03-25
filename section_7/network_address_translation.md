# Exam Tips
## Nat Instance Exam Tips
* Nat Instances are out of date but are still on test
* When creating a NAT instance, Disable source/Destination check on the instance.
* NAT Instances must be in a public subnet
* There must be a route out of the private subnet to the NAT instance, in order for this to work
* The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
* You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a sccript to automate failover
* Behind a Security Group
## Nat Gateways
* Redundant inside the Availability Zone
* You can only have one Nat Gateway per AZ
* Preferred by the enterprise
* Starts at 5Gbps and scales currently to 45Gbps
* No need to patch
* Not associated with Security Groups
* Automatically assigned a public ip address
* Remember to update your route tables.
* No need to disable Source/Destination Checks
* If you have resources in multiple Availability zones and they share one NAT gateway, in the event that the NAT Gateway's AZ is down, resources in the other AZ lose internet access. To create an AZ independent architecture, create a NAT gateway in each AZ and configure your routing to ensure that resources use that NAT gateway in the same AZ.
