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

-----

SQS lets you send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. It is a fully-managed service used to decouple applications. It serves as a temporary message store so that a receivering service can receive data at a timeframe and manner that is acceptable to it, as opposed to just receiving a message whenever the sender sends it. It is the oldest AWS offering and one of the first services to appear in the cloud. It scales from 1 message to 10,000s per second. Requests are deleted after they are read.

Kinesis is a service for managing real-time Big Data streams. It collects, processes, and analyzes real-time streaming data at any scale.

SNS is a managed messaging service for communication, allowing messaging between decoupled microservices applications or directly to users with SMS. Event publishers only need to send a message to a single SNS topic for all of that topic's subscribers to receive it.

MQ is a managed message broker service for RabbitMQ and ActiveMQ. This is helpful for traditional applications running on-premise that may be using protocols like MQTT, AMQP, STOMP, Openwite, etc. that need to be migrated into AWS. Instead of changing the system to conform to cloud native protocols like SNS or SQS, they can be lifted and shifted into AWS and run similarly to how they were run on-prem. MQ does not scale similarly to the cloud-native alternatives and runs on EC2 servers.

--------
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

Security Token Service (STS) enables you to create temporary, limited-privledges credentials to access AWS resources. Therse short-term credentials are configured to expire at a time that you specify.

Cognito is a way to provide identity access into AWS resources for the users of your application. For example, a retail brand with millions of customers should be able to have their users access shopping image data that is hosted in S3. IAM Users should be reserved to the relevant staff.

Directory Service offers a fully-managed, native Microsoft Active Directory. It provides centralized security management. AWS's Managed Microsoft AD is the option to manage your own Active Directory within the AWS ecosystem. AD Connector is a proxy that redirects requests received in AWS out of AWS and into an on-premise AD. Simple AD is the fully-managed AD service option.

IAM Identity Center is the successor to AWS Single Sign-On. It provides one login for all AWS accounts in AWS Organizations.
