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

Amazon's RDS stands for Relational Database Service. It uses SQL as its querying language and is managed by AWS. You can choose to have your RDS instance run MySQL, Postgres, MariaDB, Oracle, Microsoft SQL Server, IBM DB2, or Amazon's proprietary relational DB called Aurora.

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
