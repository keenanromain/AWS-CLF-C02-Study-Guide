# AWS-CLF-C02-Study-Guide
WIP

AWS Global Infrastructure:
https://aws.amazon.com/about-aws/global-infrastructure/ 

AWS Services by Region:
https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/ 

Recommended course to prepare:
https://www.udemy.com/course/aws-certified-cloud-practitioner-new/ 

AWS has three pricing fundamentals, following the pay-as-you-go pricing model
1. Pay for compute time
2. Pay for data stored in AWS
3. Pay for data transfered out of AWS (data transfered in is free)

<img width="1072" alt="Screen Shot 2024-11-28 at 12 00 39 PM" src="https://github.com/user-attachments/assets/4f610cbc-a34a-4476-942c-d36123b1f28a">

IAM: Users & Groups

IAM (Identity and Access Management) is a global service. The root account created by default curing account creation shouldn't be used or shared. Instead, you should create users. A user represents one individual in your organiztion. Users can be grouped. Groups however cannot be grouped inside of other groups. Users don't have to belong to groups and users an belong to multiple groups.

<img width="1161" alt="Screen Shot 2024-12-01 at 9 39 10 PM" src="https://github.com/user-attachments/assets/4495fe16-5afe-4453-af2f-6a209abe3ea4">

IAM Policies consist of a Version, an Id, and one or more Statements. A statement includes an Sid (Statement Id), an Effect (Allow or Deny), a Principal which is the account/user/role the policy is being applied to, the list of Actions this policy allows or denies, and an optional Condition for when this policy is in effect.

<img width="299" alt="Screen Shot 2024-12-02 at 1 29 11 PM" src="https://github.com/user-attachments/assets/7b07d25c-042d-4f2e-bcd3-04747c9f94da">

Users can access AWS via the AWS Management Console (password protected and optional MFA) over the web browser, the AWS Command Line Interface (access ket protected) via a terminal, and the AWS Software Development Kit (access ket protected) for written code.

IAM Roles allow us to assign permissions to AWS services. For example, we may have a virtual server in EC2 retrieve data from an RDS database. The EC2 instance would need permissions via an IAM Role in order to query the database.

EC2 allows us to rent virtual machines. We can store data on virtual drives (Elastic Block Store) that attach to EC2. You can choose your instance to be Linux, Mac Os, or Windows.

EC2 Instance Types:
https://aws.amazon.com/ec2/instance-types/

From an exam perspective, the following few instance types are most likely to feature in the exam:
- General Purpose instances are great for a diversity of workloads such as webservers or code repositories. They balance compute, memory, and networking very well.
- Compute Optimized instances are great for compute-intensive tasks that require high performance processing such as batch processing workloads, media transcoding, dedicated gaming servers, etc.
- Memory Optimized instances are great for workloads that process large data sets in memory such as high performance databases, distributed web scale caches, etc.
- Storage Optimized instances are great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage. Use cases include databases, online transaction processing (OLTP) systems, data warehouse systems, distributed file systems, etc.

Security Groups control how traffic is allowed into and out of our EC2 instances. Security groups only contain *allow* rules and can be thought of as a firewall on EC2 instances. By default, all inbound traffic is blocked and all outbound traffic is authorized.

<img width="682" alt="Screen Shot 2024-12-09 at 2 50 59 PM" src="https://github.com/user-attachments/assets/cd9566cf-450b-4191-991d-96acd82c3dc3">

EC2 Instances Purchasing Options:
- On-Demand Instances: for short workloads, predicable pricing, pay by the second.
- Reserved Instances: 1 & 3 year contracts for long workloads. You can also have long-term instances with a flexible instance type with Convertible Reserved Instances.
- Savings Plan Instances: also for 1 & 3 year terms, however the commitment is to an amount used in dollars rather than the full timeframe.
- Spot Instances: for cheap & short workloads, less reliable. They are based on a bidding system for unused capacity within AWS EC2 and at any time the highest bidder wins capacity.
- Dedicated Instances: no other AWS customer can share your hardware.
- Capacity Reservations: reserve capacity in a specific Availability Zone for any duration.

<img width="653" alt="Screen Shot 2024-12-09 at 3 34 00 PM" src="https://github.com/user-attachments/assets/c583a0a7-10fb-41fd-a41e-e71507dea5ea"> 

An EBS (Elastic Block Store) is a network drive you can attach to your instances while they run. It allows your instances to persist data even after the instance is terminated. An EBS volume is bound to a particular Availability Zone. You can think of EBS Volumes as "network USB sticks". Because of this, they can be detached from one EC2 instance and reattached to another one fairly quickly.

An EBS Snapshot allow us to make a backup of our EBS volume at a point of time. This lets us make a copy of our EBS Volume that can then be used on a different instance in a different Availability Zone because without a copy, EBS Volumes are bound to specific Availability Zones. 

AMI (Amazon Machine Image) are a customization of an EC2 instance. By customizing our base image in this way, we can have a faster bootup and configuration time because the required specific software would be pre-packaged. AMIs are built for a specific region but can also be copied to different regions. You can launch EC2 instances from a AWS public AMI (Amazon provided), your own AMI (that you make and maintain yourself), and an AWS marketplace AMI (third-party made & maintained, possibly for a profit).

EC2 Image Builder is used to automate the creation of VMs or container images. It streamlines the creation, validation, and testing of EC2 AMIs. It can be run on a schedule of your liking. The service itself is free, you only pay for the underlying resources created and used.

EC2 Instance Stores is used for when you need a high-performance hardware disk. EC2 volumes serve a similar purpose but because they are "network USB sticks" their performance is limited as your instance is storing data across the network in a different machine. EC2 Instance Store on the other hand is a local store on the hardware of the EC2 instance itself. This provides very high throughput and I/O. The caveat is that if the EC2 instance is stopped or terminated, so is the machine's EC2 Instance Store. The same is true for hardware failures on the AWS side. Backups and replication are then your own responsibility if you want data to persist. EC2 Instance Store is good for a local buffer, cache, scratch data, or temporary content.   

EFS (Elastic File System) is an NFS (Network File System) that can be mounted across hundreds of EC2 instances at a time. Think of it as a shared file system. It only works with Linux EC2 instances and works across multiple Availability Zones. While more expensive than EBS volumes, you pay per use and the service is highly available, scaleable, and fault tolerant. 

EFS Infrequent Access (EFS-IA) is cost-optimized for files that aren't accessed everyday. It can be up to 92% cheaper than EFS Standard.

Amazon FSx is a fully managed share file system alterantive with offerings for Lustre, Microsoft's Windows File Server, and NetApp ONTAP


<img width="657" alt="Screen Shot 2024-12-09 at 5 41 42 PM" src="https://github.com/user-attachments/assets/b9b64074-dab5-4305-b8ed-3b3d5740921e">
