# What is IAM
IAM allows you to manage users and their level of access to the AWS console.  
It is important to understand IAM and how it works.

# Key features of IAM
* Centralized control of your AWS account
* Shared Access to your AWS account
* Granular Permissions
* Identity Federation (Active Directory, Facebook, LinkedIn)
* MFA (multifactor authentication)
* Provide temporary access for users/devices and services where necessary
* Setup password rotation policy
* Supports PCI DSS Compliance

**Users**: End Users such as people, employees  
**Groups**: A collection of users. Each user in the group will inherit the permissions of the group.  
**Policies**: Policies are made up of documents, called Policy documents. Define what a User/Group/Role can do  
**Role**: You create roles and then assign them to AWS resources.  

IAM is global, it is not locked down to a region.  

# Exam Tips
* IAM is universal. It does not apply to regions
* the "root" account is simply the account created when first setting up the AWS account. It has complete admin access.
* New Users have NO permissions when first created.
* New Users are assigned Access Key ID & Secret Access Keys when first created.
* You cannot use the access key ID & secret access key to log in to the console.
* You only get to view these once. If you lost them, you have to regenerate them.
* Always setup MFA on the root account
* You can create and customise your own password rotation policy