CURRENTLY THIS DOCUMENT IS A WORK IN PROGRESS

# AWS-CLF-C02-Study-Guide
This study guide will help you pass the AWS Certified Cloud Practitioner exam. Ideally, you should reference this guide while working through the following material:

 1. Stephane Maarek's <a href="https://www.udemy.com/course/aws-certified-cloud-practitioner-new/?couponCode=JUL_25_GET_STARTED">Ultimate AWS Certified Cloud Practitioner CLF-C02 2025</a> (permanent discount available through this link)
2. The FAQs for the most critical services, included in the recommended reading list below
3. Stephane Maarek's <a href="https://www.udemy.com/course/practice-exams-aws-certified-cloud-practitioner/?couponCode=JUL_25_GET_STARTED">6 Practice Exams | AWS Certified Cloud Practitioner CLF-C02</a> (permanent discount available through this link)
4. Andrew Brown's <a href="https://www.youtube.com/watch?v=NhDYbskXRgc">AWS Certified Cloud Practitioner Certification Course (CLF-C02) - Pass the Exam!</a> 

*Notes*:
If at any point you find yourself feeling uncertain of your progress and in need of more time, you can postpone your AWS exam date. Be sure to also keep up with the ongoing discussions in <a href="https://reddit.com/r/AWSCertifications/">r/AWSCertifications</a> as you will find relevant exam tips, studying material, and advice from other exam takers. Before experimenting with AWS, it's very important to be sure that you know what is <a href="https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc">free</a> and what isn't. Relevant Free Tier FAQs can be found <a href="https://aws.amazon.com/free/free-tier-faqs/">here</a>. 

## Table of Contents
1. <a href="#introduction">Introduction</a>
2. <a href="#exam-content-breakdown">Exam Content Breakdown</a>
3. <a href="#simple-storage-service-s3">Simple Storage Service (S3)</a>
4. <a href="#cloudfront">CloudFront</a>
5. <a href="#elastic-compute-coud-ec2">Elastic Compute Cloud (EC2)</a>



## Introduction

<a href="https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf">**The Official AWS Certified Cloud Practitioner (CLF-C02) Exam Guide**</a>

### Exam Content Breakdown:
*Domain 1: Cloud Concepts*

<ins>Task Statement 1.1: Define the benefits of the AWS Cloud.</ins>

Knowledge of:

• Value proposition of the AWS Cloud

Skills in:

• Understanding the economies of scale (for example, cost savings)

• Understanding the benefits of global infrastructure (for example, speed of
deployment, global reach)

• Understanding the advantages of high availability, elasticity, and agility

<ins>Task Statement 1.2: Identify design principles of the AWS Cloud.</ins>

Knowledge of:

• AWS Well-Architected Framework

Skills in:

• Understanding the pillars of the Well-Architected Framework (for example,
operational excellence, security, reliability, performance efficiency, cost
optimization, sustainability)

• Identifying differences between the pillars of the Well-Architected Framework

<ins>Task Statement 1.3: Understand the benefits of and strategies for migration to the AWS Cloud.</ins>

Knowledge of:

• Cloud adoption strategies

• Resources to support the cloud migration journey

Skills in:

• Understanding the benefits of the AWS Cloud Adoption Framework (AWS CAF) (for
example, reduced business risk; improved environmental, social, and governance
(ESG) performance; increased revenue; increased operational efficiency)

• Identifying appropriate migration strategies (for example, database replication, use
of AWS Snowball)

<ins>Task Statement 1.4: Understand concepts of cloud economics.</ins>

Knowledge of: 

Aspects of cloud economics

• Cost savings of moving to the cloud

Skills in:

• Understanding the role of fixed costs compared with variable costs

• Understanding costs that are associated with on-premises environments

• Understanding the differences between licensing strategies (for example, Bring Your
Own License [BYOL] model compared with included licenses)

• Understanding the concept of rightsizing

• Identifying benefits of automation (for example, provisioning and configuration
management with AWS CloudFormation)

• Identifying managed AWS services (for example, Amazon RDS, Amazon Elastic
Container Service [Amazon ECS], Amazon Elastic Kubernetes Service [Amazon EKS],
Amazon DynamoDB)

*Domain 2: Security and Compliance*

<ins>Task Statement 2.1: Understand the AWS shared responsibility model.</ins>

Knowledge of:

• AWS shared responsibility model

Skills in:

• Recognizing the components of the AWS shared responsibility model

• Describing the customer’s responsibilities on AWS

• Describing AWS responsibilities

• Describing responsibilities that the customer and AWS share

• Describing how AWS responsibilities and customer responsibilities can shift,
depending on the service used (for example, Amazon RDS, AWS Lambda, Amazon EC2)

<ins>Task Statement 2.2: Understand AWS Cloud security, governance, and compliance concepts.</ins>

Knowledge of:

• AWS compliance and governance concepts

• Benefits of cloud security (for example, encryption)

• Where to capture and locate logs that are associated with cloud security

Skills in:

• Identifying where to find AWS compliance information (for example, AWS Artifact)

• Understanding compliance needs among geographic locations or industries (for
example, AWS Compliance)

• Describing how customers secure resources on AWS (for example, Amazon
Inspector, AWS Security Hub, Amazon GuardDuty, AWS Shield)

• Identifying different encryption options (for example, encryption in transit,
encryption at rest)

• Recognizing services that aid in governance and compliance (for example,
monitoring with Amazon CloudWatch; auditing with AWS CloudTrail, AWS Audit
Manager, and AWS Config; reporting with access reports)

• Recognizing compliance requirements that vary among AWS services

<ins>Task Statement 2.3: Identify AWS access management capabilities.</ins>

Knowledge of:

• Identity and access management (for example, AWS Identity and Access
Management [IAM])

• Importance of protecting the AWS root user account

• Principle of least privilege

• AWS IAM Identity Center (AWS Single Sign-On)

Skills in:

• Understanding access keys, password policies, and credential storage (for example,
AWS Secrets Manager, AWS Systems Manager)

• Identifying authentication methods in AWS (for example, multi-factor authentication
[MFA], IAM Identity Center, cross-account IAM roles)

• Defining groups, users, custom policies, and managed policies in compliance with
the principle of least privilege

• Identifying tasks that only the account root user can perform

• Understanding which methods can achieve root user protection

• Understanding the types of identity management (for example, federated)

<ins>Task Statement 2.4: Identify components and resources for security.</ins>

Knowledge of:

• Security capabilities that AWS provides

• Security-related documentation that AWS provides

Skills in:

• Describing AWS security features and services (for example, security groups,
network ACLs, AWS WAF)

• Understanding that third-party security products are available from AWS
Marketplace

• Identifying where AWS security information is available (for example, AWS
Knowledge Center, AWS Security Center, AWS Security Blog)

• Understanding the use of AWS services for identifying security issues (for example,
AWS Trusted Advisor)

*Domain 3: Cloud Technology and Services*

<ins>Task Statement 3.1: Define methods of deploying and operating in the AWS Cloud.</ins>

Knowledge of:

• Different ways of provisioning and operating in the AWS Cloud

• Different ways to access AWS services

• Types of cloud deployment models

• Connectivity options 

Skills in:

• Deciding between options such as programmatic access (for example, APIs, SDKs,
CLI), the AWS Management Console, and infrastructure as code (IaC)

• Evaluating requirements to determine whether to use one-time operations or
repeatable processes

• Identifying different deployment models (for example, cloud, hybrid, on-premises)

• Identifying connectivity options (for example, AWS VPN, AWS Direct Connect, public
internet)

<ins>Task Statement 3.2: Define the AWS global infrastructure.</ins>

Knowledge of:

• AWS Regions, Availability Zones, and edge locations

• High availability

• Use of multiple Regions

• Benefits of edge locations

• AWS Wavelength Zones and AWS Local Zones

Skills in:

• Describing relationships among Regions, Availability Zones, and edge locations

• Describing how to achieve high availability by using multiple Availability Zones

• Recognizing that Availability Zones do not share single points of failure

• Describing when to use multiple Regions (for example, disaster recovery, business
continuity, low latency for end users, data sovereignty)

• Describing at a high level the benefits of edge locations (for example, Amazon
CloudFront, AWS Global Accelerator)

<ins>Task Statement 3.3: Identify AWS compute services.</ins>

Knowledge of:

• AWS compute services 

Skills in:

• Recognizing the appropriate use of different EC2 instance types (for example,
compute optimized, storage optimized)

• Recognizing the appropriate use of different container options (for example,
Amazon ECS, Amazon EKS)

• Recognizing the appropriate use of different serverless compute options (for
example, AWS Fargate, Lambda)

• Recognizing that auto scaling provides elasticity

• Identifying the purposes of load balancers

<ins>Task Statement 3.4: Identify AWS database services.</ins>

Knowledge of:

• AWS database services

• Database migration

Skills in:

• Deciding when to use EC2 hosted databases or AWS managed databases

• Identifying relational databases (for example, Amazon RDS, Amazon Aurora)

• Identifying NoSQL databases (for example, DynamoDB)

• Identifying memory-based databases

• Identifying database migration tools (for example AWS Database Migration Service
[AWS DMS], AWS Schema Conversion Tool [AWS SCT])

<ins>Task Statement 3.5: Identify AWS network services.</ins>

Knowledge of:

• AWS network services

Skills in:

• Identifying the components of a VPC (for example, subnets, gateways)

• Understanding security in a VPC (for example, network ACLs, security groups)

• Understanding the purpose of Amazon Route 53

• Identifying edge services (for example, CloudFront, Global Accelerator)

• Identifying network connectivity options to AWS (for example AWS VPN, Direct
Connect)

<ins>Task Statement 3.6: Identify AWS storage services.</ins>

Knowledge of:

• AWS storage services

Skills in:

• Identifying the uses for object storage

• Recognizing the differences in Amazon S3 storage classes

• Identifying block storage solutions (for example, Amazon Elastic Block Store
[Amazon EBS], instance store)

• Identifying file services (for example, Amazon Elastic File System [Amazon EFS],
Amazon FSx)

• Identifying cached file systems (for example, AWS Storage Gateway)

• Understanding use cases for lifecycle policies

• Understanding use cases for AWS Backup

<ins>Task Statement 3.7: Identify AWS artificial intelligence and machine learning (AI/ML) services
and analytics services.</ins>

Knowledge of:

• AWS AI/ML services

• AWS analytics services

Skills in:

• Understanding the different AI/ML services and the tasks that they accomplish (for
example, Amazon SageMaker, Amazon Lex, Amazon Kendra)

• Identifying the services for data analytics (for example, Amazon Athena, Amazon
Kinesis, AWS Glue, Amazon QuickSight)

<ins>Task Statement 3.8: Identify services from other in-scope AWS service categories.</ins>

Knowledge of:

• Application integration services of Amazon EventBridge, Amazon Simple Notification
Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS)

• Business application services of Amazon Connect and Amazon Simple Email Service
(Amazon SES)

• Customer engagement services of AWS Activate for Startups, AWS IQ, AWS
Managed Services (AMS), and AWS Support

• Developer tool services and capabilities of AWS AppConfig, AWS Cloud9, AWS
CloudShell, AWS CodeArtifact, AWS CodeBuild, AWS CodeCommit, AWS
CodeDeploy, AWS CodePipeline, AWS CodeStar, and AWS X-Ray

• End-user computing services of Amazon AppStream 2.0, Amazon WorkSpaces, and
Amazon WorkSpaces Web

• Frontend web and mobile services of AWS Amplify and AWS AppSync

• IoT services of AWS IoT Core and AWS IoT Greengrass

Skills in:

• Choosing the appropriate service to deliver messages and to send alerts and
notifications

• Choosing the appropriate service to meet business application needs

• Choosing the appropriate service for AWS customer support

• Choosing the appropriate option for business support assistance

• Identifying the tools to develop, deploy, and troubleshoot applications

• Identifying the services that can present the output of virtual machines (VMs) on
end-user machines

• Identifying the services that can create and deploy frontend and mobile services

• Identifying the services that manage IoT devices

*Domain 4: Billing, Pricing, and Support*

<ins>Task Statement 4.1: Compare AWS pricing models.</ins>

Knowledge of:

• Compute purchasing options (for example, On-Demand Instances, Reserved
Instances, Spot Instances, Savings Plans, Dedicated Hosts, Dedicated Instances,
Capacity Reservations)

• Data transfer charges

• Storage options and tiers

Skills in:

• Identifying and comparing when to use various compute purchasing options

• Describing Reserved Instance flexibility

• Describing Reserved Instance behavior in AWS Organizations

• Understanding incoming data transfer costs and outgoing data transfer costs (for
example, from one Region to another Region, within the same Region)

• Understanding different pricing options for various storage options and tiers

<ins>Task Statement 4.2: Understand resources for billing, budget, and cost management.</ins>

Knowledge of:

• Billing support and information

• Pricing information for AWS services

• AWS Organizations

• AWS cost allocation tags

Skills in:

• Understanding the appropriate uses and capabilities of AWS Budgets, AWS Cost
Explorer, and AWS Billing Conductor

• Understanding the appropriate uses and capabilities of AWS Pricing Calculator

• Understanding AWS Organizations consolidated billing and allocation of costs

• Understanding various types of cost allocation tags and their relation to billing
reports (for example, AWS Cost and Usage Report)

<ins>Task Statement 4.3: Identify AWS technical resources and AWS Support options.</ins>

Knowledge of:

• Resources and documentation available on official AWS websites 
AWS Support plans

• Role of the AWS Partner Network, including independent software vendors and
system integrators

• AWS Support Center

Skills in:

• Locating AWS whitepapers, blogs, and documentation on official AWS websites

• Identifying and locating AWS technical resources (for example AWS Prescriptive
Guidance, AWS Knowledge Center, AWS re:Post)

• Identifying AWS Support options for AWS customers (for example, customer service
and communities, AWS Developer Support, AWS Business Support, AWS Enterprise
On-Ramp Support, AWS Enterprise Support)

• Identifying the role of Trusted Advisor, AWS Health Dashboard, and the AWS Health
API to help manage and monitor environments for cost optimization

• Identifying the role of the AWS Trust and Safety team to report abuse of AWS
resources

• Understanding the role of AWS Partners (for example AWS Marketplace,
independent software vendors, system integrators)

• Identifying the benefits of being an AWS Partner (for example, partner training and
certification, partner events, partner volume discounts)

• Identifying the key services that AWS Marketplace offers (for example, cost
management, governance and entitlement)

• Identifying technical assistance options available at AWS (for example, AWS
Professional Services, AWS Solutions Architects)

## Identity Access Management (IAM)

IAM Simplified:

IAM Entities:

IAM Key Details:

IAM Security Tools:

IAM: Users & Groups

IAM (Identity and Access Management) is a global service. The root account created by default during account creation shouldn't be used or shared. Instead, you should create users. A user represents one individual in your organization. Users can be grouped. Groups however cannot be grouped inside of other groups. Users don't have to belong to groups. Also, a single user can belong to multiple groups.

<img width="1161" alt="Screen Shot 2024-12-01 at 9 39 10 PM" src="https://github.com/user-attachments/assets/4495fe16-5afe-4453-af2f-6a209abe3ea4">

IAM Policies consist of a Version, an Id, and one or more Statements. A statement includes an Sid (Statement Id), an Effect (Allow or Deny), a Principal which is the account/user/role the policy is being applied to, the list of Actions this policy allows or denies, and an optional Condition for when this policy is in effect.

<img width="299" alt="Screen Shot 2024-12-02 at 1 29 11 PM" src="https://github.com/user-attachments/assets/7b07d25c-042d-4f2e-bcd3-04747c9f94da">

Users can access AWS via the AWS Management Console (password protected and optional MFA) over the web browser, the AWS Command Line Interface (access ket protected) via a terminal, and the AWS Software Development Kit (access ket protected) for written code.

IAM Roles allow us to assign permissions to AWS services. For example, we may have a virtual server in EC2 retrieve data from an RDS database. The EC2 instance would need permissions via an IAM Role in order to query the database.

## Simple Storage Service (S3)

S3 Simplified:

S3 Key Details:

S3 Storage Classes:

S3 Encryption:

S3 Versioning:

S3 Lifecycle Management:

S3 Select:

## CloudFront

CloudFront Simplified:

CloudFront Key Details:


## Elastic Compute Cloud (EC2)

EC2 Simplified:

EC2 Key Details:

EC2 Instance Types:

EC2 Instance Pricing:

EC2 Security:

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

Scalability means that an application or system has the capability to handle greater loads by adapting. There are two kinds of scalability; horizontal scaling and vertical scaling i.e. scaling out vs. scaling up. 

Horizontal scaling means increasing the number of instances. For example, your application on AWS runs on a t2.micro EC2 instance but with more traffic it begins to get laggy. Scaling horizontally could mean spinning up three more t2.micro EC2 instances. Horizontal scalability is common for distributed systems like web applications. 

Vertical scaling means increasing the size of an instance. For example, your application on AWS runs on a t2.micro EC2 instance but with more traffic it begins to get laggy. Scaling vertically could mean transfering your application over to a t2.large EC2 instance. Vertical scalability is common for non-distributed systems like databases.  

High Availability usually goes hand in hand with horizontal scaling where your application is running in at least two Availability Zones.

Scalability is the ability to accomodate a larger load by making the hardware stronger (scale up) or by adding nodes (scale out).

Elasticity is once a system is scalable, there is the element 'auto-scaling' included so that the system can scale intelligently based on load.

Elastic Load Balancers (ELBs) are servers that forward internet traffic to multiple servers (EC2 instances) downstream.

![image](https://github.com/user-attachments/assets/f75ac73f-b642-4322-a49a-de5e4f412c3b)

Why use a load balancer?

1. Spread load across multiple downstream instances
2. Expose a single point of access (DNS) to your application
3. Seamlessly handle failures of downstream instances
4. Do regular health checks to your instances
5. Provide SSL termination (HTTPS) for your websites
6. High Availability across zones

An ELB is a managed load balancer. This means AWS guarantees that the load balancer is up and working, upgraded regularly, and highly available. It is possible to set up your own load balancer on EC2 but its a lot more effort in managing it on your own.

There are four kinds of load balancers on AWS:
1. Application Load Balancer (HTTP/HTTPS) - Layer 7
2. Network Load Balancer (TCP) - Layer 4 and is the AWS ultra-high performance LB
3. Gateway Load Balancer - Layer 3 and routes traffic to firewalls for inspection
4. Classic Load Balancer - Layer 4 & 7 and was retired in 2023. Likely not to feature on the exam.

<img width="742" alt="Screen Shot 2024-12-12 at 1 52 28 PM" src="https://github.com/user-attachments/assets/798c8e31-117b-4661-86ae-8db12954181e" />

Auto Scaling Groups allow you to automatically scale out and in in order to either add or remove servers based on your application's current load. You can prefigure a maximum and minimum number of instances to have running, replace unhealthy instances with healthy instances, and have all new instances automatically register with any load balancer you might be using.

![image](https://github.com/user-attachments/assets/e17462cd-8e3b-40f5-b9e8-10f379015838)

Some of the most common Auto Scaling Group strategies include Dynamic Scaling, Predictive Scaling, and Scheduled Scaling:

1. Dynamic scaling scales the capacity of your Auto Scaling group as traffic changes occur.

2. Predictive scaling works by analyzing historical load data to detect daily or weekly patterns in traffic flows. It uses this information to forecast future capacity needs so Amazon EC2 Auto Scaling can proactively increase the capacity of your Auto Scaling group to match the anticipated load.

3. With scheduled scaling, you can set up automatic scaling for your application based on predictable load changes. You create scheduled actions that increase or decrease your group's desired capacity at specific times.

Amazon S3 is infinity scaling storage. It is used for archives, backups, disaster recovery, media and application hosting, data lakes, hosting static websites, etc.

S3 stores files in 'buckets'. Once a file is in a bucket, it is referred to as an 'object'. 

S3 buckets must have a globally unique name across all regions and all AWS accounts. The name cannot have uppercases or underscores and it must be between 3 to 63 characters long.

Even though the S3 bucket name must exist globally, the bucket itself is defined to a region.

S3 objects have a key and the key is the full path to the object inside of the bucket.
![image](https://github.com/user-attachments/assets/549cefae-c2b4-404b-9618-489b003bffa2)

The 'value' for the object's key-value pair is the content of the file itself. The max object size is 5TB. All objects have corresponding metadata (including a Version ID in case you reupload the same file multiple times) and you can use tags to organize the objects that live inside your bucket.

S3 Security is both user-based and resource-based. 

User-based security includes IAM policies that can determine what kind of API calls and access a given user can have for your bucket. 

<img width="679" alt="Screen Shot 2024-12-13 at 3 00 43 PM" src="https://github.com/user-attachments/assets/27317741-ad42-4bb3-ba01-b1bec3823edf" />


Resource-based security includes Bucket Policies are rules applied at a universal bucket-wide level and Object Access Control Lists (ACL) for more precise rules.

<img width="646" alt="Screen Shot 2024-12-13 at 3 00 12 PM" src="https://github.com/user-attachments/assets/081f5e04-5dc3-4bf8-aba7-d77615a48344" />


Bucket Policies are JSON based. Example below:

<img width="789" alt="Screen Shot 2024-12-13 at 2 58 18 PM" src="https://github.com/user-attachments/assets/02db967e-ca5c-4d51-8d9f-faf13472ac57" />

For AWS services to get access to S3, they will need an IAM Role

<img width="672" alt="Screen Shot 2024-12-13 at 3 01 44 PM" src="https://github.com/user-attachments/assets/adf8a483-d549-43d2-8247-e598b852f1c2" />

You can version your files in S3 which is helpful for backups. Versioning is enabled at the bucket level. It is best practice to version your buckets to protect against unintended deletes and its easy to roll back to a previous version. 

You can also have your S3 bucket replicate it's contents to another bucket such as replicating from one bucket in the US (us-east-1) to Europe (eu-west-2). Uses cases include lowering latency for users to access content, adhering to local compliance laws, disaster recovery, etc. To replicate your bucket's content, you must have versioning enabled.

The main storage classes are below:
![image](https://github.com/user-attachments/assets/8531aed8-5292-4840-88fd-68b625d2a435)

**S3 Standard** offers high durability, availability, and performance object storage for frequently accessed data. Because it delivers low latency and high throughput, S3 Standard is appropriate for a wide variety of use cases, including cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics. 

**S3 Standard-Infrequent Access (S3 Standard-IA)** is for data that is accessed less frequently, but requires rapid access when needed. S3 Standard-IA offers the high durability, high throughput, and low latency of S3 Standard, with a low per GB storage price and per GB retrieval charge. This combination of low cost and high performance make S3 Standard-IA ideal for long-term storage, backups, and as a data store for disaster recovery files. 

**S3 One Zone-Infrequent Access (S3 One Zone-IA)** is for data that is accessed less frequently, but requires rapid access when needed. Unlike other S3 Storage Classes which store data in a minimum of three Availability Zones (AZs), S3 One Zone-IA stores data in a single AZ and costs 20% less than S3 Standard-IA. S3 One Zone-IA is ideal for customers who want a lower-cost option for infrequently accessed data but do not require the availability and resilience of S3 Standard or S3 Standard-IA. It’s a good choice for storing secondary backup copies of on-premises data or easily re-creatable data.

**S3 Intelligent-Tiering** is the first cloud storage that automatically reduces your storage costs on a granular object level by automatically moving data to the most cost-effective access tier based on access frequency, without performance impact, retrieval fees, or operational overhead. You can use S3 Intelligent-Tiering as the default storage class for virtually any workload, especially data lakes, data analytics, new applications, and user-generated content.

**S3 Glacier** is purpose-built for data archiving, and are designed to provide you with the highest performance, the most retrieval flexibility, and the lowest cost archive storage in the cloud. You can choose from three archive storage classes optimized for different access patterns and storage duration:

1. **S3 Glacier Instant Retrieval**: For archive data that needs immediate access, such as medical images, news media assets, or genomics data, etc. It is an archive storage class that delivers low cost storage with milliseconds retrieval.
2. **S3 Glacier Flexible Retrieval**: For archive data that does not require immediate access but needs the flexibility to retrieve large sets of data at no cost, such as backup or disaster recovery use cases. It can perform the retrieval in minutes or you can select the free bulk retrievals in 5—12 hours.
3. **3 Glacier Deep Archive**: To save even more on long-lived archive storage such as compliance archives and digital media preservation. It is the lowest cost storage in the cloud with data retrieval from 12—48 hours.

By default, S3 does server-side encryption. This means S3 does the encryption once it receives the uploaded object. However, you can also perform client-side encryption where you encrypt the file prior to uploading into S3. 

IAM Access Analyzer for S3 ensures only the intended people have access to your S3 bucket. It evaluates S3 bucket policies, S3 Access Control Lists (ACLs) and IAM policies.

<img width="1202" alt="Screen Shot 2024-12-14 at 12 22 49 PM" src="https://github.com/user-attachments/assets/29af14b9-66aa-4fb6-b621-35b0417c2462" />

The AWS Snow Family (comprised of AWS Snowcone, Snowball, and AWS Snowmobile) are a collection of physical devices that are used to physically transport up to exabytes of data in to and out of AWS. Snow Family devices are owned and managed by AWS and integrate with AWS security, monitoring, storage management, and computing capabilities. If you need to upload data into AWS but cannot do so over the internet due to a lack consistent network connectivity, security concerns, etc. you can have a Snow device come to you and after you load your data into the device, you ship it back to an AWS data center.

<img width="836" alt="Screen Shot 2024-12-14 at 12 27 36 PM" src="https://github.com/user-attachments/assets/05b55fc5-ae77-4715-ad1b-c0edc9d4603e" />

As a general rule of thumb, if it would take you more than a week to transfer your data into AWS you should use a Snow device!

For hybrid cloud architectures (where part of your infrastructure is in AWS and other parts remain on-premise) that require S3 storage, you need to use **Storage Gateway** as a means to access S3. 

Many database technologies can be run on EC2, but you must handle setting up database resiliency, backups, patching, high availability, fault tolerance, scaling, etc. yourself.

Amazon RDS stands for Relational Database Service. It uses SQL as its querying language and is managed by AWS. You can choose to have your RDS instance run MySQL, Postgres, MariaDB, Oracle, Microsoft SQL Server, IBM DB2, or Amazon's proprietary relational DB called Aurora.

As a managed service, AWS is responsible for automated provisioning and OS patching, continuous backups and restores to specific points of time, monitoring dashboards, and read replicas for improved DB read performance, maintenance windows for upgrades, scaling capabilities, and Multi-AZ setup for disaster recovery.

However, you cannot SSH into the underlying DB server where your DB instance is running.

As briefly mentioned above, Amazon Aurora is Amazon's proprietary (not open-sourced) relational DB. It can run both MySQL and Postgres yet has a 5x performance improvement over MySQL on RDS and 3x performance improvement over Postgres on RDS. Aurora storage automatically grows in increments of 10GB up to 128 TB.

Amazon Aurora Serverless is an on-demand, autoscaling configuration for Amazon Aurora. It automatically starts up, shuts down, and scales capacity up or down based on your application's needs. This way, you can run your database in the cloud without managing any database instances. Good use cases include infrequent, intermittent, and unpredictable workloads.

Read Replica Deployments allow you to scale the read workload of your DB. They work by creating copies of your main db that are updated to constantly match whatever is in your main db. These copies are then what users interact with when querying for information on your application's backend. You can create up to 15 Read Replicas depending on the amount of traffic your application receives. When it comes to DB writes, the writes only go to the main DB and that change is then propogated out to the Read Replicas.

Multi-AZ Deployments is for failovers in case there is a physical outage at an Amazon AZ. It works by creating the backup failover DB in a different AZ that exists purely just as insurance in the event of a problem occuring with your main DB. Data is only ever written or read from the main DB until a failover occurs where the backup DB becomes the new main DB. You can only have one other AZ to failover to.

Multi-Region Deployments are the same as Multi-AZ Deployments, except the failover exists at the level of regions instead of AZ. This mitigates the chance of a crisis further, but is more expensive than having a Multi-AZ failover strategy. 

ElastiCache provides managed Memcached and Redis caches. Caches are in-memory data stores with low latency. They are typically used in tandem with other databases like RDS. This is because the main purpose is to help reduce load off of independent database applications for read intensive workloads. 

DyanmoDB is a fully managed and highly available NoSQL database service with replication across 3 AZs. It scales to massive workloads and can perform millions of requests per second, can have trillions of rows, and 100s of TB of storage. It has single-digit millisecond latency and is integrated with IAM for security, authorization, and administration.

DynamoDB Accelerator (DAX) is a fully managed in-memory cache for DynamoDB. DAX is a superior memory store cache for DynamoDB as compared to ElastiCache. DAX is a 10x performance improvement, offering microsecond latency compared to the normal single digit milisecond latency.

DynamoDB Global Tables is a fully managed, serverless, multi-Region, and multi-active database. Global tables provide you 99.999% availability, increased application resiliency, and improved business continuity. A DynamoDB global table is comprised of multiple replica tables. When data is written to any replica table, DynamoDB automatically replicates that data to all other replica tables in the global table. If your application processing is interrupted in one Region, there is no need for a database failover, as global tables’ multi-active architecture allows customers to read and write to any replica table. 

Redshift is an Online Analytical Processing (OLAP) database which is used for analytics and data warehousing. This is opposed to Online Transactional Processing (OLTP) databases which are typically used as application backends. Redshift is based on PostgreSQL. It has 10x better performance compared to other warehouses and scales to petabytes of data. It has columnar storage of data instead of rows and can perform Massive Parallel Query Execution. It has a SQL interface to perform queries and integrates with business intelligence tools such as Amazon QuickSight and Tableau.

Redshift Serverless makes it convenient for you to run and scale analytics without having to provision and manage an on-premises data warehouse. Redshift Serverless automatically provisions and scales data warehouse capacity to deliver fast performance for demanding and unpredictable workloads. You pay only for the capacity that you use.  

Elastic MapReduce (EMR) helps create Hadoop clusters for Big Data for analysis and processing. When using EMR, you can create a cluster made of hundreds of EC2 instances. Also supports other Hadoop-related technologies such as Apache Spark, HBase, Presto, Flink, etc. and EMR takes care of all of the relevant provisioning and configuration.

Athena is a serverless querying service to perform analytics against objects stored in S3 buckets. It uses standard SQL language to query the files. The S3 objects can be formatted in different ways such as CSV, JSON, ORC, Parquet, etc.

QuickSight is a serverless Machine Learning-based business intelligence tool to create interactive dashboards to visually represent data.

DocumentDB is an AWS-implementation of MongoDB. It is a NoSQL database that is fully managed, highly available, with data replication across three AZs. DocumentDB storage automatically grows in increments of 10GBs. Automatically scales to workloads with millions of requests per second.

Neptune is a fully managed graph database. popular graph dataset examples include social networks (Instagram, Facebook, Tiktok, etc.) or knowledge graphs (Wikipedia). Neptune is highly available across 3 AZs with up to 15 read replicas. Can store up to billions of relations and query the graph with millisecond latency. 

Timestream is a fully managed serverless time series database. It has built-in time-series analytics functions, helping you identify trends and patterns in near real time. It can automatically scale up or down to adjust capacity. It stores and analyzes trillions of events per day and is 1,000 times faster & 1/10th of the cost of relational databases.

Managed Blockchain makes it possible to build applications where multiple parties can execute transactions without the need for a trusted, central, authority. Managed Blockchain makes it possible to join public blockchain networks and to create your own scaleable private network. It is currently compatable with the Hyperledger Fabric and Ethereum frameworks.

Glue is a managed extract, transform, and load (ETL) service. It is useful to prepare and transform data in preparation for analytics. It is fully serverless.

Database Migration Service is a quick and secure database migration tool. It is resilient and self-healing. During the migration of data from a source database to a target database, the source database remains available and useable. It supports homogenous migrations (i.e. an on-premise Oracle instance to an AWS Oracle instance) as well as heterogenous migrations (an on-premise Microsoft SQL Server instance to an AWS Oracle instance).

Docker is a software development platform to deploy applications. These apps are packaged into containers that can run on any OS. Apps run the same, regardless of where they're run, without compatibility issues, with predictable behavior and being easier to maintain/deploy. You can scale containers up and down very quickly. Docker images are stored in Docker Repositories like the public Docker Hub (https://hub.docker.com/) or the private Amazon service Elastic Container Registry (ECR).

Elastic Container Service (ECS) is used to launch Docker containers on AWS. While AWS manages the starting and stopping of containers, you must provision & maintain the infrastructure w/ ECS. Most ECS infrastructure is a groupping of EC2 instances running underneath. However, ECS pairs with Application Load Balancing in order to better distribute load across EC2 instances though the ECS service is smart enough to know where to put newly created Docker containers acroos your EC2 instances.

Fargate is also used to launch Docker containers on AWS, but is a fully-managed serverless service. You don't need to provision the infrastructure. AWS will just run the Dockers that you need to run based on the RAM / CPU that your application requires.

Elastic Container Registry (ECR) is a private Docker registry in AWS. It is where you store the Docker images that will be run by either ECS or Fargate. 

Elastic Kubernetes Service (EKS) allows you to launch managed Kubernetes clusters on AWS. Kubernetes is an open-source system for the management, deployment, and scaling of containerized apps like Docker. Containers can be hosted on EC2 for servers underneath or Fargate for serverless. Kubernetes itself is cloud agnostic and can be run on other clouds or on-premise like any other open-source technology.

Lambda is a serverless allows you to run code without provisioning or managing servers. They are virtual functions of code that you write and publish to Lambda that then execute on-demand based on events that you specify. It removes the need to continuously have servers up and running for compute functionality. Scaling with Lambda is automated. It is easily integrated with the AWS monitoring Solution CloudWatch and the code for Lambda can be written in multiple languages. You can also run container images on Lambda though it is better to run Docker images on ECS/Fargate.

API Gateway is the tool you'd use to build a serverless API in AWS. It is a fully-managed service for developers to easily create, publish, maintain, and monitor secure APIs for other services to access. It is fully scalable and both RESTful and WebSocket APIs can be built using it.

Batch is a fully-managed batch processing service. It allows you to run 100,000s of computing batch jobs efficiently and easily. Batch jobs are jobs that have a start and an end as opposed to jobs that must be running continuously. Batch provisions the right amount of compute and memory that you need either on EC2 regular instances or spot instances. You schedule the batch job with Batch and the service does the rest.

Lightsail is a simplified and one-stop shop implementation of the most important AWS services for those wanting to use the cloud, but have little cloud knowledge or experience. As a product, it is basically a combination of virtual servers, storage, databases, and networking. Lightsail can provide monitoring and alert notifications. Because it has limited integrations with the rest of AWS, there is no auto-scaling.

CloudFormation is a declarative way of outlining your AWS infrastructure, for any resource. This is known as "Infrastructure as Code" and it ensures that no resources are created manually which is helpful in controlling the way resources are made or deleted. All resource changes are reviewed through code. 

Cloud Development Kit (CDK) makes it possible to define your cloud infrastructure using a familiar programming language. The code is then compiled into a CloudFormation template to be run as Infrastructure as Code. This makes it possible to deploy application runtime code and the underlying infrastructure code together.

Elastic Beanstalk is a developer-oriented deployment tool for easily standing up an application on the AWS infrastructure. It makes use of the various AWS services required for a healthy and scalable application (RDS, EC2, Application Load Balancers, Auto-Scaling Groups etc.) but all in one view that is easiers for devs to refer to. Beanstalk is a platform as a service. Beanstalk is a free and managed service, but you must pay for the underlying resources provisioned. All you need to care about is writing the code and Beanstalk will do the rest.

CodeDeploy is another way to deploy code automatically. It is a deployment service that automates application deployments to Amazon EC2 instances, on-premises instances, serverless Lambda functions, or Amazon ECS services. 

CodeBuild is a fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy.

CodePipeline is an orchestration tool to manage the different steps for code being pushed into production. It is the CICD tool for AWS. 

<img width="1153" alt="Screen Shot 2025-01-14 at 10 09 24 PM" src="https://github.com/user-attachments/assets/1a2fb066-3501-4673-bfa1-3e82dd203c91" />

CodeArtifact is a managed artifact repository service that lets you securely store, publish, and share software packages often known as artifacts. Artifacts are a collection of files that define an application’s architecture, design, and functionality. It also includes dependencies, library resources, and packages that are required during the software-creating phase of an application. 

Systems Manager (SSM) helps you manage your EC2 and On-Premise systems at scale. It is a hybrid AWS service. It is a secure end-to-end management solution for resources on AWS and elsewhere in a single location.

Route53 is a managed Domain Name System (DNS). DNS is a collection of rules and records which help clients understand how to reach a server through URLs. Route53 is highly available and it enables custom DNS routing policies to reduce latency. The most common routing policies are the Simple Routing Policy, Weighted Routing Policy, Latency Routing Policy, and Failover Routing Policy.

CloudFront is a Content Delivery Network (CDN) that improves user performance of your application by caching content near to where your users are. This is done through AWS having 216+ edge locations (points of presence) in their global network. CloudFront has DDOS protection and integrates with Shield and Firewall.

S3 Transfer Acceleration can accelerate long-distance transfers to and from your Amazon S3 buckets. It is a bucket-level feature that enables fast, easy, and secure transfers of files over long distances. The longer the distance between your client application (mobile, web application, or upload tool) and the target S3 bucket, the more S3 Transfer Acceleration can help. 

Global Accelerator is a global networking service that simplifies traffic management and improves performance by up to 60%. It works by leveraging the internal AWS network so tha you have access to endpoints in multiple AWS Regions. 

<img width="1205" alt="Screen Shot 2025-01-16 at 12 13 15 PM" src="https://github.com/user-attachments/assets/d63e2dc1-5644-4edc-b763-e1f85bd2eac9" />

Outposts simplifies managing of different infrastructure systems in a hybrid cloud arrangement where resources live both in AWS and on-premise. It does so by offering physical server racks that offer the same infrastructure, APIs, services, etc. as exists in AWS. AWS employees with bring the servers to your company location to help install the systems. You become responsible for the security of your server once it lives outside of AWS.

WaveLength is embedded AWS capability within various telecommunication providers' datacenters to better support 5G technology for AWS services.

LocalZones places AWS compute, storage, databases, and other services closer to end users to run latency-sensitive applications. It extends your VPC to more physical locations.

*CloudWatch*

- CloudWatch Metrics provides metrics for every service in AWS. A metric is a variable to monitor in order to have relevant insights into the ongoing performance of your services. Metrics have timestamps as part of the data it provides. Using CloudWatch, you can create dashboards in order to get a visual representation of your statistics.
- CloudWatch Alarms provide alarms that can be triggered to send you a notification based on certain metrics such as failures. Automated actions based on CloudWatch Alarms include self-mitigation efforts such as scaling servers when needed, informing human stakeholders through SNS topic publications, or automated EC2 actions such as stopping, starting, or restaring a server.
- CloudWatch Logs collect log files. It collects logs from various services and houses them in a central location for viewing. The retention period of logs is adjustable.

EventBridge (CloudWatch Events) is a serverless event bus that ingests data from your own apps, SaaS apps, and AWS services and routes that data to targets. You can also use EventBrdge to schedule events like Cron jobs.

CloudTrail provides governance, compliance, and audting to your AWS account. It is enabled by defaut and it provides a digital trail of records for actions taken within AWS for both users and services.  It does this by retaining the history of all AWS accounts and service activity. It is common to integrate this service with CloudWatch Logs or S3 for storage. If something suspicious is happening or resources are being deleted, it is helpful to check CloudTrail first.

X-Ray provides visual tracing of our application's network of services and their performance.

CodeGuru provides automated code reviews and app performance recommendations. This is done through the CodeGuru Reviewer and CodeGuru Profiler respectively.

Health Dashboard provides a service history of all of your active services in active regions. It shows historical information for each day. Health Dashboard provides alerts and remediation guidance when AWS is experiencing issues that may impact you.

Virtual Private Cloud (VPC) is a private network to deploy your resources in. A VPC is linked to a specific region. This virtual network closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS. Within a VPC, you can have subnets which allow you to partition your network with the VPC. Subnets can be public (accessible from the internet) and private.

Internet Gateways help our VPC's instances connect with the Internet. Public subnets have a route to the Internet Gateway.

NAT Gateways (AWS-managed) and NAT instances (self-managed) allow your instances in Private Networks obtain access to the Internet for use cases such as OS updates while keeping your instances inaccessible.

Network Access Control Lists (NACLs) is a firewall that controls traffic to and from a VPC subnet. It has both ALLOW and DENY rules. They are attached at the subnet level and the rules only include IP address.

Security Groups are a firewall that controls traffic to and from an EC2 Instances. It only has ALLOW rules. The rules include IP addresses and other security groups.

<img width="1129" alt="Image" src="https://github.com/user-attachments/assets/c9a6b21f-9887-4bfd-b588-582b2a88545b" /> 

VPC Flow Logs log all IP traffic going in and out of your VPC. It helps monitor and troubleshoot connectivity issues. VPC Flow Logs can be shipped to S3, CloudWatch Logs, Data Firehose.

VPC Peering connects two or more different VPCs so that they can behave as if they were one giant network. For this to work, the IP range of both VPCs cannot overlap. VPC connections are not transitive, meaning if VPC A and VPC B are peering and you then decide to peer VPC B with VPC C, then VPC A *cannot* peer with VPC A unless you explicitly say so as well.

VPC Endpoints allow you to connect with AWS services over a private network instead of the public internet. This gives your VPC enhanced security and lower latency when accessing the most common of AWS resources.

PrivateLink is the most secure & scalable way to expose a service to 1000s of VPCs. It does not require VPC peering, InternetGateway, NAT, route tables, etc.

Site-to-Site VPN connects an on-premise VPN to AWS. The connection is automatically encrypted and the communication is over the public internet. The on-premise network must use a CustomerGateway (GGW) to connect into AWS and on the AWS you'll need a Virtual PrivateGateway (VGW).

DirectConnect (DX) establishes a physical connection between your on-premise data center and AWS with private communication that is secure and fast. Because this requires setting up a private physical network, it usually takes around a month to complete the setup.

Client VPN connects a user from their computer, using OpenVPN, to your private network in AWS and on-premise. It allows you to connect to your services using a private IP just as if you were inside of the private VPC.

Transit Gateway is for transitive peering across thousands of VPCs and your on-premise infrastructure in a hub-and-spoke (star) connection. One single gateway provides the connectivity.

<img width="965" alt="Image" src="https://github.com/user-attachments/assets/9427f4f6-6634-4b47-afb4-40878049246c" />


Shield is a way to defend against Distributed Denial-of-Service (DDoS) attacks. Shield Advanced (os opposed to Shield Standard) offers 24/7 premium DDoS attack protection.

Web Application Firewall (WAF) filters inbound requests into your AWS environment based on rules that you specify based on IP address, HTTP Header, HTTP Body, or URI string. These lists of rules are called Web Access Control Lists (web ACLS). WAF protects your applications from common web exploits on layer 7 such as SQL Injection and Cross-Site Scripting (XSS). It is deployed to Application Load Balancer, API Gateway, and CloudFront.

Network Firewall is how you protect your entire VPC, from Layer 3 to Layer 7.

Firewall Manager lets you manage all of your security rules in all of the accounts of your AWS organization in a central place. It's rules are applied to new resources and accounts as they are created.

AWS customers are welcome to attempt security assessments and penetration testing against their AWS resources on the following services: EC2, Nat Gateways, Elastic Load Balancers, RDS, CloudFront, Aurora, Lambda, API Gateway, Lightsail, and Elastic Beanstalk.

AWS has data encryption at rest and data encryption in transit. Data at rest include the data sitting in your databases, hard disks, S3 buckets, etc. Data in transit is data being moved from one place or another like with uploads, downloads, messaging between servers, etc.

Key Management Service (KMS) is a service where AWS manages your encryption keys. You can opt into encrypting your data with KMS for EBS Volumes, S3, Redshift, RDS, and EFS. Other services are automatically encrypted on your behalf such as Storage Gateway, S3 Glacier, and CloudTrail Logs.  

Cloud HSM is another service that provides encryption. AWS provides the encryption tooling, but you are responsible for managing the keys

Certificate Manager lets you easily provision, manage, and deploy SSL/TLS certificates which provide in-flight encryption for websites.

Secrets Manager is a secret store with the capability to rotate secrets every X many days. It is mostly meant for RDS, but works for a variety of services.

Artifact is a portal that gives AWS customers access to AWS compliance documentation and AWS agreements. It is to help support internal auditing and compliance.

GuardDuty provides intelligent threat discovery to your AWS account. It uses machine learning algorithms to detect anomalies in your 3rd party data. It analyzes VPC Flow Logs, CloudTrail Logs, DNS Logs, S3 Logs, EBS Volumes, Lambda Network Activity, RDS/Aurora Login Activity, EKS Audit Logs, etc.

Inspector is an automated security assessment service. It leverages the Systems Manager (SSM) agent on services like EC2 to perform it's tests. It analyzes against unintended network accessibility and known vulnerabilities against the OS. Inspector can also analyze container images being pushed into ECR and against lambda functions for software vulnerabilities and suspicious code dependencies. It sends its findings to Amazon EventBridge.

Config helps with auditing and recording compliance with your AWS resources by recording your configurations and changes over time. It can work with S3 to have these records stored, perhaps also even analyzed with Athena.

Macie is a fully managed data security and data privacy service that uses ML pattern matching to discover and protect your sensitive data in AWS. Sensitive data in S3, such as Personally Identifiable Information (PII), will be detected by Macie and it will then alert you of the discoveries.

Security Hub is a central security tool that is used to manage various security tools across multiple aws accounts and automate security checks. It has integrated dasshboards highlighting current security and compliance statuses and automatically aggregates alerts.

Detective analyzes, investigates, and quickly indetifies *the root cause* of security issues or suspicious activity using ML. It produces visualizations with details and context so you can address the main concern.

Abuse is where you can report suspicious behavior occuring on AWS resources such as spam, port scanning, DDOS attacks, hosting illegal content, intrusion attempts, distributing malware, etc.  

IAM Access Analyzer finds out which resources are shared externally to mitigate against security risks from external sources.

----

**Rekognition** is used to find objects, people, text, scenes in images and videos using Machine Learning. It can do facial analysis and facial search to do user verification and people counting.

**Transcribe** automatically converts speech into text. While using it, you can automatically remove Personally Identifiable Information (PII) using Redaction.

**Polly** is the opposite of Transcribe. It converts text into speech.

**Translate** is a language translation service. It allows you to localize content such as webites for international users and easily translates large volumes of text accurately and effciently.

**Lex** is the technology that powers Amazon Alexa. It provides automatic speech recognition to convert speech into text.

**Connect** is a virtual cloud-based call center that can receive calls, create contact flows, and integrate with other CRM systems or other AWS services.

**Comprehend** is a fully managed service for Natural Language Processing (NLP). It uses machine learning to try and discern meaning and insights in bodies of text. 

**SageMaker** is a fully managed service for developers and data scientists to build Machine Learning models. It is a one-stop shop for everything you need to develop your own ML tooling.

**Forecast** is a fully managed service to deliver highly accurate forecasts. Use cases include product demand planning, financial planning, resoruce planning, etc.

**Kendra** is a fully managed document search service powered by ML. It extracts relevant information and answers from a document (text, pdf, HTML, PowerPoint, FAQs, etc). 

**Personalize** is a fully managed ML-service to build apps with real time personalized recommendations. For example, a user on your site has bought a lot of gardening tools and you want to suggest recommendations for them to buy that are relevant to their previous purchases.

**Textract** automatically extracts text, handwriting, and data from any scanned documents using AI and ML. For example, with a driver's license Textract can pull out all the relevant information and store it in JSON.  

-----

Organizations is a global service that allows you to manage multiple AWS accounts. The main account is called the master account and the accounts linked to it are called children accounts. It consoldiates billing across all of your accounts and there a re pricing benefits from aggregated usage. Service Control Policies (SCPs) allow you to whitelist or blacklist IAM actions on users with roles in children accounts. Consolidated Billing for Organizations combines usage across all of your accounts to share pricing and more easily attain discounting from operating at scale. It provides a single bill to be covered.

Control Tower it is an easy to setup and govern a secure and compliant multi-account AWS environment based on historical best practices. It automates the setup of your AWS Organizations in a few clicks, detect policy violations and remediates them, monitors compliance through dashboards, and implement Service Control Poliies (SCP) across your different organizations.

Resource Access Manager (RAM) allows you to share resources in one account with another account as long as they are within the same organization in order to reduce resource duplication.

Service Catalog is a self-service portal where admins can set high guardrails by predefining which resources are available for new or temporary users to use. It does so by running CloudFormation templates. This ensures that every new resource is properly configured, properly tag, and perfectly compliant with the standard set by the admins.

Savings Plan is a service that helps you commit a certain amount of money per hour for 1 or 3 years. You can create a Machine Learning Savings Plan, an EC2 Savings Plan, and the more general Compute Savings Plan which also applies to EC2 as well as Lambda and Fargate.

Compute Optimizer helps reduce costs and improve your compute resources' performance by analyzing your current workloads and recommendating optimal usage based on your needs. It will inform you what resource is under-utilized and what resource is over-provisioned to save you money and make each service perform as best as it can for you.

<img width="368" alt="Image" src="https://github.com/user-attachments/assets/a0f2a336-d524-4a0c-b43d-4aaf69ccc9bc" />

Pricing Calculator estimates the cost of your architecture. 

Billing Dashboard shows you the projected cost for the month and is helpful for a quick overview on the current price.

Cost Allocation Tags allows us to track costs on a detailed level and group them together.

Cost and Usage Reports are helpful for analyzing your AWS bill at the most granular level.

Cost Explorer helps you forecast AWS usage up to 12 months ahead based on previous usage.

Cost Anomaly Detector uses ML to continually monitor your cost and usage to detect any unusual spends. It learns from your unique and historic spending patterns.

Servique Quotas inform you when you are close to reaching a set threshold for a service.

Trusted Advsior gives you a high level assessment on your account. It provides recommendations to your account based on its performance, cost-optimization, security, fault tolerance, service limits, and operational excellence.

![Image](https://github.com/user-attachments/assets/7335b9a6-062a-4d9f-9928-349c6f33c12b)

<img width="1323" alt="Image" src="https://github.com/user-attachments/assets/ff5198fe-c299-4c37-9941-9ce2867de65b" />

-----

Security Token Service (STS) enables you to create temporary, limited-privledges credentials to access AWS resources. Therse short-term credentials are configured to expire at a time that you specify.

Cognito is a way to provide identity access into AWS resources for the users of your application. For example, a retail brand with millions of customers should be able to have their users access shopping image data that is hosted in S3. IAM Users should be reserved to the relevant staff.

Directory Service offers a fully-managed, native Microsoft Active Directory. It provides centralized security management. AWS's Managed Microsoft AD is the option to manage your own Active Directory within the AWS ecosystem. AD Connector is a proxy that redirects requests received in AWS out of AWS and into an on-premise AD. Simple AD is the fully-managed AD service option.

IAM Identity Center is the successor to AWS Single Sign-On. It provides one login for all AWS accounts in AWS Organizations.


-----

SQS lets you send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. It is a fully-managed service used to decouple applications. It serves as a temporary message store so that a receivering service can receive data at a timeframe and manner that is acceptable to it, as opposed to just receiving a message whenever the sender sends it. It is the oldest AWS offering and one of the first services to appear in the cloud. It scales from 1 message to 10,000s per second. Requests are deleted after they are read.

Kinesis is a service for managing real-time Big Data streams. It collects, processes, and analyzes real-time streaming data at any scale.

SNS is a managed messaging service for communication, allowing messaging between decoupled microservices applications or directly to users with SMS. Event publishers only need to send a message to a single SNS topic for all of that topic's subscribers to receive it.

MQ is a managed message broker service for RabbitMQ and ActiveMQ. This is helpful for traditional applications running on-premise that may be using protocols like MQTT, AMQP, STOMP, Openwite, etc. that need to be migrated into AWS. Instead of changing the system to conform to cloud native protocols like SNS or SQS, they can be lifted and shifted into AWS and run similarly to how they were run on-prem. MQ does not scale similarly to the cloud-native alternatives and runs on EC2 servers.

--------

You can use the AWS Health Dashboard – Service health to view the health of all AWS services. It is the single place to learn about the availability and operations of AWS services. This page shows reported service events and disruptions for services across AWS Regions. The AWS Health Dashboard – Service health offers the possibility to subscribe to an RSS feed to be notified of interruptions to each service.

An Amazon Machine Image (AMI) provides the information required to launch an instance. You must specify an Amazon Machine Image (AMI) when you launch an instance. You can launch multiple instances from a single AMI when you need multiple instances with the same configuration. The Amazon Machine Image (AMI) must be in the same region as that of the Amazon EC2 instance to be launched. If the Amazon Machine Image (AMI) exists in a different region, you can copy that Amazon Machine Image (AMI) to the region where you want to launch the EC2 instance.

The Acceptable Use Policy describes prohibited uses of the web services offered by Amazon Web Services, Inc. and its affiliates (the “Services”) and the website located at http://aws.amazon.com (the “AWS Site”). This policy is present at https://aws.amazon.com/aup/ and is updated on a need basis by AWS.

You can use AWS X-Ray to analyze and debug serverless and distributed applications such as those built using a microservices architecture. With X-Ray, you can understand how your application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors.
![Image](https://github.com/user-attachments/assets/7a19ec52-72af-4b9c-89fc-d515fb5c081e)

AWS Trusted Advisor is an online tool that provides you real-time guidance to help you provision your resources following *AWS best practices* on cost optimization, security, fault tolerance, service limits and performance improvement. Whether establishing new workflows, developing applications, or as part of ongoing improvement, recommendations provided by Trusted Advisor regularly help keep your solutions provisioned optimally. 

A virtual Multi-Factor Authentication (MFA) device is a software app that runs on a phone or other device and emulates a physical device. The device generates a six-digit numeric code based upon a time-synchronized one-time password algorithm. The user must type a valid code from the device on a second webpage during sign-in.  Google Authenticator is an example of a Virtual Multi-Factor Authentication (MFA) device.

A Universal 2nd Factor (U2F) security key is a device that you plug into a USB port on your computer. When you enable a U2F security key, you sign in by entering your credentials and then tapping the device instead of manually entering a code. A Yubi Key is an ecample of a U2F security key.

You can use Amazon CloudWatch Logs to monitor, store, and access your log files from Amazon Elastic Compute Cloud (Amazon EC2) instances, AWS CloudTrail, Route 53, and other sources such as on-premises servers.

Amazon CloudWatch Logs enables you to centralize the logs from all of your systems, applications, and AWS services that you use, in a single, highly scalable service. You can then easily view them, search them for specific error codes or patterns, filter them based on specific fields, or archive them securely for future analysis.

DynamoDB global tables replicate data automatically across your choice of AWS Regions and automatically scale capacity to accommodate your workloads. With global tables, your globally distributed applications can access data locally in the selected regions to get single-digit millisecond read and write performance. DynamoDB offers active-active cross-region support that is needed for the company.

AWS customer can buy software that has been bundled into customized Amazon Machine Image (AMIs) by the AWS Marketplace sellers

AWS Marketplace is a digital catalog with thousands of software listings from independent software vendors that make it easy to find, test, buy, and deploy software that runs on AWS. The AWS Marketplace enables qualified partners to market and sell their software to AWS Customers.

AWS Marketplace offers two ways for sellers to deliver software to customers: Amazon Machine Image (AMI) and Software as a Service (SaaS).

1. Amazon Machine Image (AMI): Offering an AMI is the preferred option for listing products in AWS Marketplace. Partners have the option for free or paid products. Partners can offer paid products charged by the hour or month. Bring-Your-Own-License (BYOL) is also available and enables customers with existing software licenses to easily migrate to AWS.

2. Software as a Service (SaaS): If you offer a SaaS solution running on AWS (and are unable to build your product into an AMI) the SaaS listing offers our partners a way to market their software to customers.

OpsWorks is a configuration management service that provides managed instances of Chef and Puppet. Chef and Puppet are automation platforms that allow you to use code to automate the configurations of your servers.

Systems Manager allows you to centralize operational data from multiple AWS services and automate tasks across your AWS resources in order to get operational insights. You can create logical groups of resources such as applications, different layers of an application stack, or production versus development environments.

With AWS Systems Manager, you can select a resource group and view its recent API activity, resource configuration changes, related notifications, operational alerts, software inventory, and patch compliance status. You can also take action on each resource group depending on your operational needs. AWS Systems Manager provides a central place to view and manage your AWS resources, so you can have complete visibility and control over your operations.

![Image](https://github.com/user-attachments/assets/216a9945-1ab8-4277-8c5f-b837b80b6de0)

It is helpful for patching automation for improved compliance across your fleet of EC2 and on-premise servers.

Systems Manager Session Manager is a fully-managed service that provides you with an interactive browser-based shell and CLI experience. It helps provide secure and auditable instance management without the need to open inbound ports, maintain bastion hosts, and manage SSH keys. AWS Systems Manager Session Manager helps to enable compliance with corporate policies that require controlled access to instances, increase security and auditability of access to the instances while providing simplicity and cross-platform instance access to end-users.

Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for exposure, vulnerabilities, and deviations from best practices. After performing an assessment, Amazon Inspector produces a detailed list of security findings prioritized by level of severity. 

Compute Optimizer helps you identify the optimal AWS resource configurations, such as Amazon EC2 instance types, Amazon EBS volume configurations, and AWS Lambda function memory sizes, using machine learning to analyze historical utilization metrics. AWS Compute Optimizer delivers recommendations for selected types of EC2 instances, EC2 Auto Scaling groups, Amazon EBS volumes, and AWS Lambda functions.

Partner Solutions (formerly Quick Starts) are automated reference deployments built by AWS solutions architects to help you deploy popular technologies according to AWS best practices. You can reduce hundreds of manual procedures to a few steps and start using your environment within minutes. Each Partner Solution launches, configures, and runs the AWS compute, network, storage, and other services required to deploy a specific workload on AWS, using AWS best practices for security and availability.

The AWS Partner Network (APN) is the global partner program for technology and consulting businesses that leverage Amazon Web Services to build solutions and services for customers.

1. APN Consulting Partners are professional services firms that help customers of all types and sizes design, architect, build, migrate, and manage their workloads and applications on AWS, accelerating their migration to AWS cloud.
  
2. APN Technology Partners provide hardware, connectivity services, or software solutions that are either hosted on or integrated with, the AWS Cloud.

Why AWS?
![Image](https://github.com/user-attachments/assets/23bca884-4277-46fc-9ccd-26669f4a6e56)

Site-to-Site VPN creates a secure connection between your data center or branch office and your AWS cloud resources. This connection goes over the public internet. Site to Site VPN cannot be used to interconnect VPCs.

Direct Connect creates a dedicated private connection from a remote network to your VPC. This is a private connection and does not use the public internet. Takes at least a month to establish this connection. 

Use AWS Organizations to manage AWS accounts of all units and then share the reserved EC2 instances amongst all units. Organizations helps you to centrally manage billing; control access, compliance, and security; and share resources across your AWS accounts. Using AWS Organizations, you can automate account creation, create groups of accounts to reflect your business needs, and apply policies for these groups for governance. You can also simplify billing by setting up a single payment method for all of your AWS accounts. AWS Organizations is available to all AWS customers at no additional charge.

IAM Identity Center is the successor to AWS Single Sign-On (AWS SSO). It is built on top of AWS Identity and Access Management (IAM) to simplify access management to multiple AWS accounts, AWS applications, and other SAML-enabled cloud applications. In IAM Identity Center, you create or connect, your workforce users for use across AWS. 

![Image](https://github.com/user-attachments/assets/63fa7eda-524c-4a01-9b35-9eb36ac04236)

Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily. With Amazon Cognito, you also have the option to authenticate users through social identity providers such as Facebook, Twitter, or Amazon, with SAML identity solutions, or by using your own identity system. It is an identity management solution for customers/developers building B2C or B2B apps for their customers.

Cost Explorer has an easy-to-use interface that lets you visualize, understand, and manage your AWS costs and usage over time. AWS Cost Explorer includes a default report that helps you visualize the costs and usage associated with your top five cost-accruing AWS services, and gives you a detailed breakdown of all services in the table view. The reports let you adjust the time range to view historical data going back up to twelve months to gain an understanding of your cost trends.

EventBridge is a service that provides real-time access to changes in data in AWS services, your own applications, and software as a service (SaaS) applications without writing code. Amazon EventBridge Scheduler is a serverless task scheduler that simplifies creating, executing, and managing millions of schedules across AWS services without provisioning or managing underlying infrastructure.

![Image](https://github.com/user-attachments/assets/1a6e64fa-2a87-4e17-bc8b-40b3fd0d33b6)

You can assign metadata to your AWS resources in the form of tags. Each tag is a label consisting of a user-defined key and value. Tags can help you manage, identify, organize, search for, and filter resources. You can create tags to categorize resources by purpose, owner, environment, or other criteria.

Local Zones allow you to use select AWS services, like compute and storage services, closer to more end-users, providing them very low latency access to the applications running locally. AWS Local Zones are also connected to the parent region via Amazon’s redundant and very high bandwidth private network, giving applications running in AWS Local Zones fast, secure, and seamless access to the rest of AWS services.

You should use AWS Local Zones to deploy workloads closer to your end-users for low-latency requirements. AWS Local Zones have their connection to the internet and support AWS Direct Connect, so resources created in the Local Zone can serve local end-users with very low-latency communications.

CloudHSM is a cloud-based Hardware Security Module (HSM) that enables you to easily generate and use your encryption keys on the AWS Cloud. It is a fully-managed service that automates time-consuming administrative tasks for you, such as hardware provisioning, software patching, high-availability, and backups.

CodeDeploy is a service that automates code deployments to any instance, including Amazon EC2 instances and instances running on-premises. AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid downtime during deployment, and handles the complexity of updating your applications. You can use AWS CodeDeploy to automate deployments, eliminating the need for error-prone manual operations, and the service scales with your infrastructure so you can easily deploy to one instance or thousands.

CodePipeline is a continuous delivery service that enables you to model, visualize, and automate the steps required to release your software. With AWS CodePipeline, you model the full release process for building your code, deploying to pre-production environments, testing your application and releasing it to production.

All Amazon S3 buckets have encryption configured by default, and objects are automatically encrypted by using server-side encryption with Amazon S3 managed keys (SSE-S3). This encryption setting applies to all objects in your Amazon S3 buckets.

Storage Gateway is a hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage. All data transferred between the gateway and AWS storage is encrypted using SSL (for all three types of gateways - File, Volume and Tape Gateways).

The following AWS services support reservations to optimize costs:

1. Amazon EC2 Reserved Instances (RI): You can use Amazon EC2 Reserved Instances (RI) to reserve capacity and receive a discount on your instance usage compared to running On-Demand instances.

2. Amazon DynamoDB Reserved Capacity: If you can predict your need for Amazon DynamoDB read-and-write throughput, Reserved Capacity offers significant savings over the normal price of DynamoDB provisioned throughput capacity.

3. Amazon ElastiCache Reserved Nodes: Amazon ElastiCache Reserved Nodes give you the option to make a low, one-time payment for each cache node you want to reserve and, in turn, receive a significant discount on the hourly charge for that node.

4. Amazon RDS RIs: Like Amazon EC2 RIs, Amazon RDS RIs can be purchased using No Upfront, Partial Upfront, or All Upfront terms. All Reserved Instance types are available for Aurora, MySQL, MariaDB, PostgreSQL, Oracle, and SQL Server database engines.

5. Amazon Redshift Reserved Nodes: If you intend to keep an Amazon Redshift cluster running continuously for a prolonged period, you should consider purchasing reserved-node offerings. These offerings provide significant savings over on-demand pricing, but they require you to reserve compute nodes and commit to paying for those nodes for either a 1- or 3-year duration.

AWS Enterprise Support provides customers with concierge-like service where the main focus is helping the customer achieve their outcomes and find success in the cloud. With Enterprise Support, you get 24x7 technical support from high-quality engineers, tools and technology to automatically manage the health of your environment, consultative architectural guidance delivered in the context of your applications and use-cases, and a designated Technical Account Manager (TAM) to coordinate access to proactive/preventative programs and AWS subject matter experts. You get access to guidance, configuration, and troubleshooting of AWS interoperability with many common operating systems, platforms, and application stack components.

You should use AWS Business Support if you have production workloads on AWS and want 24x7 phone, email and chat access to technical support and architectural guidance in the context of your specific use-cases. You get full access to AWS Trusted Advisor Best Practice Checks. You get access to guidance, configuration, and troubleshooting of AWS interoperability with many common operating systems, platforms, and application stack components.

The AWS Basic Support plan only provides Customer Service & Communities - 24x7 access to customer service, documentation, whitepapers, and support forums. AWS Trusted Advisor - Access to the core Trusted Advisor checks and guidance to provision your resources following best practices to increase performance and improve security. AWS Health - Your Account Health Dashboard : A personalized view of the health of your AWS services, and alerts when your resources are impacted.

You should use the AWS Developer Support plan if you are testing or doing early development on AWS and want the ability to get email-based technical support during business hours as well as general architectural guidance as you build and test. This plan provides access to just the core Trusted Advisor checks from the Service Quota and basic Security checks.

There are three fundamental drivers of cost with AWS: compute, storage, and outbound data transfer. In most cases, there is no charge for inbound data transfer or data transfer between other AWS services within the same region. Outbound data transfer is aggregated across services and then charged at the outbound data transfer rate. Per AWS pricing, data transfer between S3 and EC2 instances within the same region is not charged, so there would be no data transfer charge for moving 500 GB of data from an EC2 instance to an S3 bucket in the same region.

AWS Credits are applied in the following order:
1. Soonest expiring
2. Least number of applicable products
3. Oldest credit

An instance store provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. This is a good option when you need storage with very low latency, but you don't need the data to persist when the instance terminates or you can take advantage of fault-tolerant architectures. For this use-case, the computation application itself has a fault tolerant architecture, so it can automatically handle any failures of Instance Store volumes.

Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. It is built to scale on-demand to petabytes without disrupting applications, growing and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth. The service is designed to be highly scalable, highly available, and highly durable. Amazon EFS file systems store data and metadata across multiple Availability Zones (AZ) in an AWS Region. EFS file system can be mounted on instances across multiple Availability Zones (AZ).

Amazon Elastic Block Store (EBS) is an easy to use, high-performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction-intensive workloads at any scale. Designed for mission-critical systems, EBS volumes are replicated within an Availability Zone (AZ) and can easily scale to petabytes of data. You can attach an available EBS volume to one instance that is in the same Availability Zone (AZ) as the volume.

AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. Config continuously monitors and records your AWS resource configurations and allows you to automate the evaluation of recorded configurations against desired configurations.

![Image](https://github.com/user-attachments/assets/79df811f-6460-41bd-8e17-b50e06de4546)

AWS Artifact is your go-to, central resource for compliance-related information that matters to your organization. It provides on-demand access to AWS security and compliance reports and select online agreements. Reports available in AWS Artifact include our Service Organization Control (SOC) reports, Payment Card Industry (PCI) reports, and certifications from accreditation bodies across geographies and compliance verticals that validate the implementation and operating effectiveness of AWS security controls. Different types of agreements are available in AWS Artifact Agreements to address the needs of customers subject to specific regulations. For example, the Business Associate Addendum (BAA) is available for customers that need to comply with the Health Insurance Portability and Accountability Act (HIPAA). It is not a service, it's a no-cost, self-service portal for on-demand access to AWS compliance reports.

You can remove an account from your organization only if the account has the information that is required for it to operate as a standalone account. For each account that you want to make standalone, you must accept the AWS Customer Agreement, choose a support plan, provide and verify the required contact information, and provide a current payment method. AWS uses the payment method to charge for any billable (not AWS Free Tier) AWS activity that occurs while the account isn't attached to an organization.

The AWS Professional Services organization is a global team of experts that can help you realize your desired business outcomes when using the AWS Cloud. AWS Professional Services consultants can supplement your team with specialized skills and experience that can help you achieve quick results. Therefore, leveraging AWS Professional Services can accelerate the infrastructure migration for the startup.

The AWS Partner Network (APN) is the global partner program for technology and consulting businesses that leverage Amazon Web Services to build solutions and services for customers. The startup can work with experts from APN to build a custom solution for this infrastructure migration.

AWS has the concept of a Region, which is a physical location around the world where AWS clusters its data centers. AWS calls each group of logical data centers an Availability Zone (AZ). Each AWS Region consists of a minimum of three, isolated, and physically separate AZs within a geographic area. Each AZ has independent power, cooling, and physical security and is connected via redundant, ultra-low-latency networks.

An Availability Zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region. All AZs in an AWS Region are interconnected with high-bandwidth, low-latency networking, over fully redundant, dedicated metro fiber providing high-throughput, low-latency networking between AZs.

EC2 Dedicated Hosts allow you to use your eligible software licenses from vendors such as Microsoft and Oracle on Amazon EC2. An Amazon EC2 Dedicated Host is a physical server fully dedicated for your use, so you can help address corporate compliance requirements.

![Image](https://github.com/user-attachments/assets/2f45ac9c-5c3d-4c14-96aa-27852760281f)

AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are forwarded to an Amazon API Gateway API, Amazon CloudFront or an Application Load Balancer. HTTP and HTTPS requests are part of the Application layer, which is layer 7.

Reserved Instance Pricing Comparison:
![Image](https://github.com/user-attachments/assets/b28a39a7-f3b3-4287-b1df-0284252bed15)

The act of encrypting data before sending it to Amazon S3 is termed as client-side encryption. The AWS encryption SDK is a client-side encryption library that is separate from the language–specific SDKs. You can use this encryption library to more easily implement encryption best practices in Amazon S3. Unlike the Amazon S3 encryption clients in the language–specific AWS SDKs, the AWS encryption SDK is not tied to Amazon S3 and can be used to encrypt or decrypt data to be stored anywhere.

AWS Shield Standard is activated for all AWS customers, by default. For higher levels of protection against attacks, you can subscribe to AWS Shield Advanced. With Shield Advanced, you also have exclusive access to advanced, real-time metrics and reports for extensive visibility into attacks on your AWS resources. With the assistance of the DRT (DDoS response team), AWS Shield Advanced includes intelligent DDoS attack detection and mitigation for not only for network layer (layer 3) and transport layer (layer 4) attacks but also for application layer (layer 7) attacks.

AWS Shield Advanced provides expanded DDoS attack protection for web applications running on the following resources: Amazon Elastic Compute Cloud, Elastic Load Balancing (ELB), Amazon CloudFront, Amazon Route 53, AWS Global Accelerator.

AWS Budgets gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount. You can also use AWS Budgets to set reservation utilization or coverage targets and receive alerts when your utilization drops below the threshold you define. Reservation alerts are supported for Amazon EC2, Amazon RDS, Amazon Redshift, Amazon ElastiCache, and Amazon Elasticsearch reservations.

AWS hosts Amazon CloudFront and Amazon Route 53 services on a distributed network of proxy servers in data centers throughout the world called edge locations. Using the global Amazon network of edge locations for application delivery and DNS service plays an important part in building a comprehensive defense against DDoS attacks for your dynamic web applications.

IAM enables security best practices by allowing you to grant unique security credentials to users and groups to specify which AWS service APIs and resources they can access. These features make IAM an important service for the overall security of AWS resources in your account. IAM is secure by default; users have no access to AWS resources until permissions are explicitly granted.

GuardDuty is a threat detection service that monitors malicious activity and unauthorized behavior to protect your AWS account. Amazon GuardDuty analyzes billions of events across your AWS accounts from AWS CloudTrail (AWS user and API activity in your accounts), Amazon VPC Flow Logs (network traffic data), and DNS Logs (name query patterns). 

AWS Storage Gateway is a hybrid cloud storage service that connects your existing on-premises environments with the AWS Cloud. Customers use Storage Gateway to simplify storage management and reduce costs for key hybrid cloud storage use cases. These include moving tape backups to the cloud, reducing on-premises storage with cloud-backed file shares, providing low latency access to data in AWS for on-premises applications, as well as various migration, archiving, processing, and disaster recovery use cases. AWS Storage Gateway service provides three different types of gateways – Tape Gateway, File Gateway, and Volume Gateway – that seamlessly connect on-premises applications to cloud storage, caching data locally for low-latency access.

AWS services can be accessed in three different ways:

1. **AWS Management Console**: This is a simple web interface for accessing AWS services.
2. **AWS Command Line Interface (AWS CLI)**: You can access AWS services from the command line and automate service management with scripts.
3. **AWS Software Development Kit (SDK)**: You can also access via AWS SDK that provides language-specific abstracted APIs for AWS services.

An Amazon Virtual Private Cloud (Amazon VPC) spans all of the Availability Zones (AZ) in the Region whereas a subnet spans only one Availability Zone (AZ) in the Region

Amazon Virtual Private Cloud (Amazon VPC) is a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. An Amazon Virtual Private Cloud (Amazon VPC) spans all of the Availability Zones (AZ) in the Region.

A subnet is a range of IP addresses within your Amazon Virtual Private Cloud (Amazon VPC). A subnet spans only one Availability Zone (AZ) in the Region.

A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. Security groups act at the instance level, not at the subnet level. Security groups are stateful — if you send a request from your instance, the response traffic for that request is allowed to flow in regardless of inbound security group rules. A security group evaluates all rules before deciding whether to allow traffic.

A network access control list (network ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets (i.e. it works at subnet level). A network access control list (network ACL) contains a numbered list of rules. A network access control list (network ACL) evaluates the rules in order, starting with the lowest numbered rule, to determine whether traffic is allowed in or out of any subnet associated with the network ACL. 

Shield Advanced offers some cost protection against spikes in your AWS bill that could result from a DDoS attack. This cost protection is provided for your Elastic Load Balancing load balancers, Amazon CloudFront distributions, Amazon Route 53 hosted zones, Amazon Elastic Compute Cloud instances, and your AWS Global Accelerator accelerators. AWS Shield Advanced is a paid service for all customers, irrespective of the Support plan.

Most policies are stored in AWS as JSON documents. Identity-based policies and policies used to set permissions boundaries are JSON policy documents that you attach to a user or role. Resource-based policies are JSON policy documents that you attach to a resource.

A JSON policy document includes these elements:

  Optional policy-wide information at the top of the document
  One or more individual statements

Each statement includes information about a single permission. The information in a statement is contained within a series of elements.

  1. Version – Specify the version of the policy language that you want to use. As a best practice, use the latest 2012-10-17 version.

  2. Statement – Use this main policy element as a container for the following elements. You can include more than one statement in a policy.
        a. Sid (Optional) – Include an optional statement ID to differentiate between your statements.
        b. Effect – Use Allow or Deny to indicate whether the policy allows or denies access.
        c. Principal (Required in only some circumstances) – If you create a resource-based policy, you must indicate the account, user, role, or federated user to which you would like to allow or deny access. If you are creating an IAM permissions policy to attach to a user or role, you cannot include this element. The principal is implied as that user or role.
        d. Action – Include a list of actions that the policy allows or denies.
        e. Resource (Required in only some circumstances) – If you create an IAM permissions policy, you must specify a list of resources to which the actions apply. If you create a resource-based policy, this element is optional. If you do not include this element, then the resource to which the action applies is the resource to which the policy is attached.
        f. Condition (Optional) – Specify the circumstances under which the policy grants permission.

For each resource, each tag key must be unique, and each tag key can have only one value. A Cost Allocation Tag is a label that you or AWS assigns to an AWS resource. Each tag consists of a key and a value. For each resource, each tag key must be unique, and each tag key can have only one value. You can use tags to organize your resources, and cost allocation tags to track your AWS costs on a detailed level.

You must activate both AWS generated tags and user-defined tags separately before they can appear in Cost Explorer or on a cost allocation report. AWS provides two types of cost allocation tags, an AWS generated tags and user-defined tags. AWS defines, creates, and applies the AWS generated tags for you, and you define, create, and apply user-defined tags. You must activate both types of tags separately before they can appear in Cost Explorer or on a cost allocation report.

AWS Cost & Usage Report (AWS CUR) contains the most comprehensive set of cost and usage data available. You can receive reports that break down your costs by the hour or month, by product or product resource, or by tags that you define yourself.

AWS Knowledge Center contains the most frequent & common questions and requests and AWS provided solutions for the same. This should be the starting point of checking for a solution or troubleshooting an issue with AWS services. The URL for Knowledge Center is https://aws.amazon.com/premiumsupport/knowledge-center/.

The rightsizing recommendations feature in AWS Cost Explorer helps you identify cost-saving opportunities by downsizing or terminating Amazon services that are not being actively used or are under-utilized. 

TrustedAdvisor:
![Image](https://github.com/user-attachments/assets/d48ad69a-7ed9-48e0-a5d7-200994821f6d)

AWS Migration Evaluator (Formerly TSO Logic) is a complimentary service to create data-driven business cases for AWS Cloud planning and migration. AWS Migration Evaluator quickly provides a business case to make sound AWS planning and migration decisions. With AWS Migration Evaluator, your organization can build a data-driven business case for AWS, gets access to AWS expertise, visibility into the costs associated with multiple migration strategies, and insights on how reusing existing software licensing reduces costs further.

You can monitor your estimated AWS charges by using Amazon CloudWatch. Billing metric data, regardless of where it is generated, is stored in the US East (N. Virginia) Region and represents worldwide charges. This data includes the estimated charges for every service in AWS that you use, in addition to the estimated overall total of your AWS charges.

Reserved instances (RI) provide you with significant savings (up to 72%) on your Amazon Elastic Compute Cloud (Amazon EC2) costs compared to on-demand instance pricing. Spot instances go up to 90%.

AWS Budgets enable you to plan your service usage, service costs, and instance reservations. AWS Budgets information is updated up to three times a day. Updates typically occur between 8 to 12 hours after the previous update. Budgets track your unblended costs, subscriptions, refunds, and RIs. There are four different budget types you can create under AWS Budgets - Cost budget, Usage budget, Reservation budget and Savings Plans budget.

Amazon EFS is a regional service storing data within and across multiple Availability Zones (AZs) for high availability and durability. Amazon EC2 instances can access your file system across AZs, regions, and VPCs, while on-premises servers can access using AWS Direct Connect or AWS VPN. 

Amazon Elastic File System (Amazon EFS) - Infrequent Access storage class is cost-optimized for files accessed less frequently. Data stored on the Amazon Elastic File System (Amazon EFS) - Infrequent Access storage class costs less than Standard and you will pay a fee each time you read from or write to a file.

AWS Site-to-Site VPN enables you to securely connect your on-premises network or branch office site to your Amazon Virtual Private Cloud (Amazon VPC). VPN Connections are a good solution if you have an immediate need, and have low to modest bandwidth requirements. This connection goes over the public internet. Virtual private gateway (VGW) / Transit Gateway and Customer Gateway are the components of an AWS Site-to-Site VPN. A virtual private gateway (VGW) is the VPN concentrator on the Amazon side of the AWS Site-to-Site VPN connection. A customer gateway is a resource in AWS that provides information to AWS about your Customer gateway device.

Amazon EBS Snapshots are a point in time copy of your block data. For the first snapshot of a volume, Amazon EBS saves a full copy of your data to Amazon S3. Amazon EBS Snapshots are stored incrementally, which means you are billed only for the changed blocks stored.

All Amazon S3 buckets have encryption configured by default, and objects are automatically encrypted by using server-side encryption with Amazon S3 managed keys (SSE-S3). This encryption setting applies to all objects in your Amazon S3 buckets.

AWS Storage Gateway is a hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage. All data transferred between the gateway and AWS storage is encrypted using SSL (for all three types of gateways - File, Volume and Tape Gateways).

Cloud Foundations provides a guided path to help customers deploy, configure, and secure their new workloads while ensuring they are ready for on-going operations in the cloud. Cloud Foundations helps customers navigate through the decisions they need to make through curated AWS Services, AWS Solutions, Partner Solutions, and Guidance.

EC2 Image Builder is an automated pipeline for the creation, maintenance, validation, sharing, and deployment of Linux or Windows images for use on AWS and on-premises.

EBS Volumes are tied to only one availability zone.

The AWS Glue Data Catalog is a central repository to store structural and operational metadata for all your data assets. For a given data set, you can store its table definition, physical location, add business relevant attributes, as well as track how this data has changed over time.

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. Kinesis offers four services: Data Firehose, Data Analytics, Data Streams, Video Streams.

AWS IAM Identity Center is an AWS service that makes it easy to centrally manage access to multiple AWS accounts and business applications and provide users with single sign-on access to all their assigned accounts and applications from one place.

WS Backup is a centralized backup service that makes it easy and cost-effective for you to backup your application data across AWS services in the AWS Cloud. CloudEndure Disaster Recovery minimizes downtime and data loss by providing fast, reliable recovery into AWS of your physical, virtual, and cloud-based servers.

An Availability Zone (AZ) is one or more data centers in the same geographic location.

AWS Global Accelerator is a good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP, as well as for HTTP use cases that specifically require static IP addresses or deterministic, fast regional failover. It provides static IP addresses that provide a fixed entry point to your applications and eliminate the complexity of managing specific IP addresses for different AWS Regions and Availability Zones (AZs).

A VPC interface endpoint is an elastic network interface (ENI) with a private IP address from the IP address range of your subnet that serves as an entry point for traffic destined to a supported service. Interface endpoints are powered by AWS PrivateLink, a technology that enables you to privately access services by using private IP addresses. Only Amazon S3 and Amazon DynamoDB support VPC gateway endpoint. All other services use a VPC interface endpoint 

You pay for all bandwidth into and out of Amazon S3, except for the following: (1) Data transferred in from the internet, (2) Data transferred out to an Amazon Elastic Compute Cloud (Amazon EC2) instance, when the instance is in the same AWS Region as the S3 bucket, (3) Data transferred out to Amazon CloudFront (CloudFront).

 S3 Replication

Replication enables automatic, asynchronous copying of objects across Amazon S3 buckets. Buckets that are configured for object replication can be owned by the same AWS account or by different accounts. You can copy objects between different AWS Regions or within the same Region. You can use replication to make copies of your objects that retain all metadata, such as the original object creation time and version IDs. This capability is important if you need to ensure that your replica is identical to the source object.

# Misc

AWS Global Infrastructure:
https://aws.amazon.com/about-aws/global-infrastructure/ 

AWS Services by Region:
https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/ 


AWS has three pricing fundamentals, following the pay-as-you-go pricing model
1. Pay for compute time
2. Pay for data stored in AWS
3. Pay for data transfered out of AWS (data transfered in is free)

<img width="1072" alt="Screen Shot 2024-11-28 at 12 00 39 PM" src="https://github.com/user-attachments/assets/4f610cbc-a34a-4476-942c-d36123b1f28a">
