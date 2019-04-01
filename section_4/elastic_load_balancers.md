# Types of Load Balances
* Application Load Balancer
* Network Load Balancer
* Classic Load Balancer

# Application Load Balancers
Application Load Balancers are best suited for load balancing of HTTP and HTTPS traffic. They operate at Layer 7 and are application-aware. They are intelligent and you can create advanced request routing, sending specified requests to specific web servers.

# Network Load Balancers
Network Load Balancers are best suited for load balancing of TCP traffic where extreme performance is required. Operating at the connection level (Layer 4), Network Load Balancer are capable of handling millions of requests per second, while maintaining ultra low latencies. Used for extreme performance

# Classic Load Balancers
Classic Load Balancers are the legacy Elastic Load Balancers. You can load balance HTTP/HTTPS application sand use Layer 7 specific features such as X-Forwarded and sticky sessions. youo can also use strict Layer 4 Load abalancing for applications that rely purely on the TCP protocol.

# Load Balancer Errors
Classic Load Balancers if your application stops responding the ELB responds with a 504 error.

This means that the application is having issues. This could be either at the Web Server Layer or at the Database Layer.

Identify where the application is failing and scale it up or out where possible.

# X-Forwarded-For Header

# ELB Exam Tips
* 3 Type of Load Balancers
    * Application Load Balancers
    * Network Load Balancers
    * Classic Load Balancers
* 504 Error means the gateway has timed out. This means that the application not responding within the idle timeout period.
    * Trouble shoot the application. Is it the Web Server or Database server?
* If you need the IPv4 address of your end user, look for the X-Forwarded-For Header.