# Load Balancer Types
* Application Load Balancer
* Network Load Balancer
* Classic Load Balancer

# Application Load Balancers
Best suited for load balancing of HTTP and HTTPS traffic. They operate at Layer 7 and are application-aware. They are intelligent, and you can create advanced request routing, sending specified requests to specific web servers.

# Network Load Balancers
Best suited for load balancing of TCP traffic where extreme performance is required. Operating at the connection level (Layer 4), Network Load Balancer are capable of handling millions of requests per second, while maintaining ultra-low latencies. Use for extreme performance.

# Classic Load Balancers
Legacy Elastic Load Balancers. You can load balance HTTP/HTTPS applications and use Layer 7 specific features, such as X-Forwarded-For and sticky sessions. You can also use strict Layer 4 load balancing for applications that rely purely on the TCP protocol.

# Errors in Load Balancing
If your application stops responding, the ELB responds with a 504 error. This means that the application is having issues. This could be either at the Web Server layer or at the Databse Layer. Identify where the application is failing, and scale it up or out where possible.

# X-Forwarded-For Header
How you get a clients public IP behind an ELB

# Exam Tips
## 3 Different Types of Load Balancers
* Application Load Balancers
* Network Load Balancers
* Classic Load Balancers

* 504 error means the gateway has timed out. This means that the application not responding within the idle timeout period.
* Trouble shoot the application. Is it the Web Server or Databse Server?
* If you need the IPv4 address of your end user, look for the X-Forwarded-For header.