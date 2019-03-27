# 3 Different Types of Load Balancers
* Application Load Balancers
* Network Load Balancers
* Classic Load Balancers

* 504 Error means the gateway has timed out. This means that the application not responding within the idle timeout period

* Troubleshoot the application. Is it the Web Server or Database Server?

* If you need the IPv4 address of your end user, look for the X-Forwarded-For header.

* Instances monitored by ELB are reported as InService or OutofService
* Health Checks check the instance health by talking to it
* Load Balancers have their own DNS name. You are never given an IP address
* Read the ELB FAQ for each Load Balancer

# CloudFormation
* Is a way of completely scripting your cloud environment
* Quick Start is a bunch of CloudFormation templates already built by AWS Solutions Architects allowing you to create complex environments very quickly