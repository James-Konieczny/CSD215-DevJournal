# AWS Global Infrastructure

- The AWS Global Infrastructure is designed and built to deliver a flexible, reliable, scalable, and securecloud computing environment with high-quality global network performance.
- AWS continually updates its global infrastructure footprint. Visit one of the following web pages for current infrastructure information:
- AWS Global Infrastructure Map: https://aws.amazon.com/about-aws/global-infrastructure/#AWS_Global_Infrastructure_Map
- Choose a circle on the map to view summary information about the Region represented by the circle.
- Regions and Availability Zones: https://aws.amazon.com/about-aws/global-infrastructure/regions_az/
- Choose a tab to view a map of the selected geography and a list of Regions, Edge locations, Local zones, and Regional Caches.

## AWS Regions
- A region is a geographical area
  - Data replication across regions is controlled by you (Most of the time though, you keep your data in one region)
  - communication between regions uses AWS backbone network infrastructure

- each region provides full redundancy and connectivity to the network
- a region typically consists of two or more availability zones

- US-EAST-1 is the region we'll be using most in the class

## Selecting a Region
- Determine the right region for your services, applications, and data based on these factors:
  - Data governance, legal requirements
  - Proximity to customers (latency)
  - Services available within the region
  - Costs (vary by region) 

## Availability Zones
- Each region has multiple availablility zones
- each availability zone is a fully isolated partition of AWS infrastructure
  - Availability Zones consist of discrete data centers
  - They are designed for fault isolation
  - They are interconnected with other Availability Zones by using high-speed private networking
  - You choose your Availability Zones.
  - AWS recommends replicating data and resources across Availability Zones for resiliency.

## AWS Data Centers
- AWS data centers are designed for security
- Data centers are where the data resides and data processing occurs.
- Each data center has redundant power, networking, and connectivity, and is housed in a separate facility.
- A data center typically has 50,000 to 80,000 physical servers.

## Points of Presence (PoP)
- AWS provides a global network of Points of Presence locations
- Consists of edge locations and a much smaller number of Regional edge caches
- Used with Amazon CloudFront
- A global Content Delivery Network (CDN), that delivers content to end users withreduced latency
- Regional edge caches used for content with infrequent access.

## AWS Infrastructure Features
- Elasticity and scalability
  - Elastic infrastructure; dynamic adaption of capacity
  - Scable infrastructure; adapts to accommodate growth
- Fault-tolerance
  - Continues operating properly in the presence of a failure
  - Built-in redundancy of components
- High availability
   - High level of operational performance
   - minimized downtime
   - no human intervention
 
### Key Points
- The AWS Global Infrastructureconsists of Regions and Availability Zones.
- Your choice of a Regionis typically based on compliance requirements or to reduce latency.
- Each Availability Zone is physically separate from other Availability Zones and has redundant power, networking, and connectivity.
- Edge locations, and Regionaledge caches improve performance by cachingcontent closer to users
- EXTRA: https://comparecloud.in/

# AWS Services and Service Category
- services such as networking, storage, compute services, and databases
- <img width="1166" height="655" alt="Screenshot 2026-01-15 101722" src="https://github.com/user-attachments/assets/8560a741-408a-4508-b723-2940b90824ea" />

## Storage Service Category
- **Amazon Simple Storage Service (Amazon S3)** is an object storage service that offers scalability, data availability, security, and performance. Use it to store and protect any amount of data for websites, mobile apps, backup and restore, archive, enterprise applications, Internet of Things (IoT) devices, and big data analytics.
- **Amazon Elastic Block Store (Amazon EBS)** is high-performance block storage that is designed for use with Amazon EC2 for both throughput and transaction intensive workloads. It is used for a broad range of workloads, such as relational and non-relational databases, enterprise applications, containerized applications, big data analytics engines, file systems, and media workflows.
- **Amazon Elastic File System (Amazon EFS)** provides a scalable, fully managed elastic Network File System (NFS) file system for use with AWS Cloud services and on-premises resources. It is built to scale on demand to petabytes, growing and shrinking automatically as you add and remove files. It reduces the need to provision and manage capacity to accommodate growth.
- **Amazon Simple Storage Service Glacier** is a secure, durable, and extremely low-cost Amazon S3 cloud storage class for data archiving and long-term backup. It is designed to deliver 11 9s of durability, and to provide comprehensive security and compliance capabilities to meet stringent regulatory requirements.
- <img width="1165" height="656" alt="Screenshot 2026-01-15 102215" src="https://github.com/user-attachments/assets/52abd2b4-95e2-4f65-a01c-5bc99afb98d3" />

## Compute Service Category
- **Amazon Elastic Compute Cloud (Amazon EC2)** provides resizable compute capacity as virtual machines in the cloud.
- **Amazon EC2 Auto Scaling** enables you to automatically add or remove EC2 instances according to conditions that you define.
- **Amazon Elastic Container Service (Amazon ECS)** is a highly scalable, high-performance container orchestration service that supports Docker containers.
- **Amazon Elastic Container Registry (Amazon ECR)** is a fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.
- **AWS Elastic Beanstalkis** a service for deploying and scaling web applications and services on familiar servers such as Apache and Microsoft Internet Information Services (IIS).
- **AWS Lambdaenables** you to run code without provisioning or managing servers. You pay only for the compute time that you consume. There is no charge when your code is not running.
- **Amazon Elastic Kubernetes Service (Amazon EKS)** makes it easy to deploy, manage, and scale containerized applications that use Kubernetes on AWS.
- **AWS Fargate** is a compute engine for Amazon ECS that allows you to run containers without having to manage servers or clusters
- <img width="1166" height="658" alt="Screenshot 2026-01-15 102354" src="https://github.com/user-attachments/assets/9716b306-26d4-46ba-aa29-7da194c3e87c" />

## Database Service Category
- **Amazon Relational Database Service (Amazon RDS)** makes it easy to set up, operate, and scale a relational database in the cloud. It provides resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching, and backups.
- **Amazon Aurora** is a MySQL and PostgreSQL-compatible relational database. It is up to five times faster than standard MySQLdatabases and three times faster than standard PostgreSQL databases.
- **Amazon Redshift** enables you to run analytic queries against petabytes of data that is stored locally in Amazon Redshift, and directly against exabytes of data that are stored in Amazon S3. It delivers fast performance at any scale.
- **Amazon DynamoDB** is a key-value and document database that delivers single-digit millisecond performance at any scale, with built-in security, backup and restore, and in-memory caching
- <img width="1164" height="653" alt="Screenshot 2026-01-15 102520" src="https://github.com/user-attachments/assets/137e7cf9-74e3-482a-9f13-290323e3f435" />

## Networking and Content Delivery Service Category
- **Amazon Virtual Private Cloud (Amazon VPC)** enables you to provision logically isolated sections of the AWS Cloud.
- **Elastic Load Balancing** automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions.
- **Amazon CloudFront** is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and application programming interfaces (APIs) to customers globally, with low latency and high transfer speeds.
- **AWS Transit Gateway** is a service that enables customers to connect their Amazon Virtual Private Clouds (VPCs) and their on-premises networks to a single gateway.
- **Amazon Route 53** is a scalable cloud Domain Name System (DNS) web service designed to give you a reliable way to route end users to internet applications. It translates names (like www.example.com) into the numeric IP addresses (like 192.0.2.1) that computers use to connect to each other.
- **AWS Direct Connect** provides a way to establish a dedicated private network connection from your data center or office to AWS, which can reduce network costs and increase bandwidth throughput.
- **AWS VPN** provides a secure private tunnel from your network or device to the AWS global network
- <img width="1165" height="656" alt="Screenshot 2026-01-15 104459" src="https://github.com/user-attachments/assets/6eb49275-5175-4daa-99ab-e109388c796a" />


## Security, Identity, and Compliance Service Category
- **AWS Identity and Access Management (IAM)** enables you to manage access to AWS services and resources securely. By using IAM, you can create and manage AWS users and groups. You can use IAM permissions to allow and deny user and group access to AWS resources.
- **AWS Organizations** allows you to restrict what services and actions are allowed in your accounts.
- **Amazon Cognito** lets you add user sign-up, sign-in, and access control to your web and mobile apps.
- **AWS Artifact** provides on-demand access to AWS security and compliance reports and select online agreements.
- **AWS Key Management Service (AWS KMS)** enables you to create and manage keys. You can use AWS KMS to control the use of encryption across a wide range of AWS services and in your applications.
- **AWS Shield** is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS
- <img width="1168" height="656" alt="Screenshot 2026-01-15 103200" src="https://github.com/user-attachments/assets/2b95a843-a4c7-4a61-b125-58944bb38919" />

## AWS Cost Management Service Category
- **The AWS Cost** and Usage Report contains the most comprehensive set of AWS cost and usage data available, including additional metadata about AWS services, pricing, and reservations.
- **AWS Budgets** enables you to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.
- **AWS Cost Explorer** has an easy-to-use interface that enables you to visualize, understand, and manage your AWS costs and usage over time
- <img width="1166" height="659" alt="Screenshot 2026-01-15 103327" src="https://github.com/user-attachments/assets/c7d3e4f9-2a96-4238-9f76-ae8a38b3e144" />

## Management and Gorvernance Service Category
- **The AWS Management Console** provides a web-based user interface for accessing your AWS account.
- **AWS Config** provides a service that helps you track resource inventory and changes.
- **Amazon CloudWatch** allows you to monitor resources and applications.
- **AWS Auto Scaling** provides features that allow you to scale multiple resources to meet demand.
- **AWS Command Line Interface** provides a unified tool to manage AWS services.
- **AWS Trusted Advisor** helps you optimize performance and security.
- **AWS Well-Architected Tool** provides help in reviewing and improving your workloads.
- **AWS CloudTrail** tracks user activity and API usage
- <img width="1166" height="658" alt="Screenshot 2026-01-15 103456" src="https://github.com/user-attachments/assets/3c16d16f-2cdc-4395-94ba-aa344b924146" />

# AWS Management Console Clickthrough Activity Questions + Answers
- Question #1: Under which service category does the IAM service appear?
   - Answer: Security, Identity, & Compliance.
- Question #2: Under which service category does the AmazonVPCservice appear?
  - Answer: Networking & Content Delivery
- Question #3: Does the subnet that you selected exist at the level of the Region or the level of the Availability Zone?
   - Answer: Subnets exist at the level of the Availability Zone.
- Question #4: Does the VPC exist at the level of the Region or the level of the Availability Zone?
   - Answer: VPCs exist at the Region level.
- Question #5: Which of the following services are global instead of Regional? Check Amazon EC2, IAM, Lambda, and Route 53.
   - Answer: IAM and Route 53 are global. Amazon EC2 and Lambda are Regional.
