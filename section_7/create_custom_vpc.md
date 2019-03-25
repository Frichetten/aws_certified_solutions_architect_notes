When a VPC is created it creates a Route Table, a Network ACL, and a Security Group

You can only have 1 internet gateway per VPC.

# Exam Tips
* When you create a VPC a default Route Table, Network Access Control List (NACL) and a default Security Group.
* It won't create any subnets, nor will it create a default internet gateway.
* US-East-1A in your AWS account can be completely different availability zone to US-EAST-1A in another AWS account. The AZ's are randomized.
* Amazon always reserve 5 IP addresses within your subnets
* You can only have 1 Internet Gateway per VPC
* Security Groups can't span VPCs