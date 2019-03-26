# Exam Tips
## 3 Different Types of Load Balancers
* Application Load Balancer
* Network Load Balancer
* Classic Load Balancer
  

* 504 Error means the gateway has timed out. This means that the application not responding within the idle timeout period.

* Trouble shoot the application. 
* If you need the IPv4 address of your user look for the X-Forwarded-For header
* Instances monitored by ELB are reported as InService, or OutofService
* Health Checks check the instance health by talking to it.
* Load Balancers have their own DNS name. You are never given an IP address.
* Read the ELB FAQ for Classical Load Balancers (or read all of them)