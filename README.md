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
