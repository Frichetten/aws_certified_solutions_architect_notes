* A Security Group is a virtual firewall
* Security Group rules are applied immediately
* Security Groups are stateful, inbound rules will automatically allow outbound
* VPC networking is not stateful
* Everything is blocked by default

# Security Group Lab
* All inbound Traffic is Blocked By Default 
* All Outbound Traffic is Allowed by Default
* Changes to Security Groups take effect immediately
* You can have any number of EC2 instances within a security group
* You can have multiple security groups attached to EC2 Instances
* Security Groups are STATEFUL
    * If you create an inbound rule allowing traffic in, that traffic is automatically allowed back out again.
* You cannot block specific IP addresses using Security Groups instead use Network Access Control Lists
* You can specify allow rules, but not deny rules