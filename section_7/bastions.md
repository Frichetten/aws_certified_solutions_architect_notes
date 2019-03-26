# Bastion Hosts
A bastion host is a special purpose ocmputer on a network specifically designed and configured to withstand attacks. The computer generally hosts a single application, for example a proxy server, and all other services are removed or limited to reduce the threat to the computer. It is hardened in this manner primarily due to its location and purpose, which is eithe ron the outside of a firewall or in a demilitarized zone (DMZ) and usually involves access from untrusted networks or computers.

# Exam Tips
* A NAT Gateway or NAT Instance is used to provide internet traffic to EC2 instances in a private subnets.
* A Bastion is used to securely administer EC2 instances (Using SSH or RDP). Bastions are called Jump Boxes in Australia.
* You cannot use a NAT Gateway as a Bastion Host