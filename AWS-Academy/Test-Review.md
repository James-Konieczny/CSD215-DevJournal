# Cloud Computing Basics
**What is Cloud Computing?**  
On-demand delivery of IT resources over the internet with pay-as-you-go pricing.

**Cloud Model**  
- IaaS – Infrastructure as a Service (EC2, VPC)
- PaaS – Platform as a Service (Elastic Beanstalk)
- SaaS – Software as a Service (Gmail, Salesforce)  
  
**Deployment Models**
- Public Cloud (AWS)
- Private Cloud
- Hybrid Cloud

# AWS Global Infrastructure
- Region – Geographic area (e.g., us-east-1)
- Availability Zone (AZ) – One or more data centers in a region
- Edge Locations – Used by CloudFront for CDN  
High availability = deploy across multiple AZs.

# Pricing Basics
**AWS Pricing Models**  
- On-Demand – Pay per use
- Reserved Instances (RI) – 1–3 year commitment, cheaper
- Savings Plans – Flexible commitment model
- Spot Instances – Cheap, but can be terminated anytime
- Free Tier – Limited free usage

**Key Concept:**  
You pay for:
- Compute time
- Storage used
- Data transfer (especially OUT of AWS)

# Compute Services
 **Amazon EC2**  
Virtual machines in the cloud.
- AMI = Amazon Machine Image (OS template)
- Instance Types = CPU, memory optimized
- Security Groups = Virtual firewalls
- EBS = Attached disk storage
- Auto Scaling = Automatically adjust instances
- ELB = Load balancer

# AWS Lambda  
**Serverless compute service.**  
- Run code without managing servers
- Triggered by events (S3 upload, API Gateway, etc.)
- Pay per execution time

# AWS Elastic Beanstalk  
Deploy apps without managing infrastructure.

# Storage Services
 **Amazon S3**  
Object storage service.
- Stores files as objects in buckets
- Highly durable (11 9’s)
- Storage classes:
    - Standard
    - Intelligent-Tiering
    - Glacier (archive)
- Versioning available
- Lifecycle policies

# Amazon EBS  
Block storage for EC2.

# Amazon EFS  
Shared file storage (like network drive).

# Database Services  
**Amazon RDS**  
Managed relational databases.
- MySQL, PostgreSQL, SQL Server, etc.
- Multi-AZ for high availability
- Read replicas for scaling reads

# Amazon DynamoDB  
Fully managed NoSQL database.
- Key-value / document
- Serverless
- Auto scaling
- Very fast performance

# Amazon Aurora
High-performance relational DB (MySQL/PostgreSQL compatible).

# Networking Basics
**Amazon VPC**  
Virtual private cloud (your isolated network).
- Subnets (public/private)
- Route tables
- Internet Gateway
- NAT Gateway
  
**Public Subnet**  
Has route to Internet Gateway.  
**Private Subnet**  
No direct internet access.  

# Elastic Load Balancing  
Distributes traffic across multiple EC2 instances.  
Types:  
- Application Load Balancer (Layer 7)
- Network Load Balancer (Layer 4)

# Amazon CloudFront
Content Delivery Network (CDN).

# Security & IAM
AWS Identity and Access Management  
Manages users and permissions.  
- Users
- Groups
- Roles
- Policies (JSON documents)
**Key Concepts:**  
- Least privilege
- MFA (Multi-Factor Authentication)
- Root user (avoid using it)

## AWS Shield  
DDoS protection.

## AWS WAF  
Web Application Firewall.

# Monitoring & Management
**Amazon CloudWatch**  
Monitoring service.
- Metrics
- Logs
- Alarms

# AWS CloudTrail
Logs API calls (who did what).

# AWS CloudFormation
Infrastructure as Code (IaC).

# High Availability & Scaling
**High Availability**  
- Multi-AZ deployment
- Load balancer
- Auto Scaling
**Scalability**  
- Vertical scaling = Bigger instance
- Horizontal scaling = More instances

# Shared Responsibility Model  
AWS is responsible for:  
- Hardware
- Infrastructure
- Physical security  
You are responsible for:  
- Data
- IAM permissions
- OS updates (on EC2)
- Security configurations

# Important Differences to Remember
Service	Type	Used For  
EC2	Compute	Virtual servers  
Lambda	Serverless	Event-driven compute  
S3	Object storage	Files, backups  
EBS	Block storage	EC2 disk  
RDS	Relational DB	SQL databases  
DynamoDB	NoSQL	Serverless key-value DB  
VPC	Networking	Private network  
IAM	Security	Access control  

## Common Exam Traps
- S3 is object storage (NOT block storage)
- EBS only attaches to ONE EC2 at a time (usually)
- DynamoDB is NoSQL
- Security Groups are stateful
- NACLs are stateless
- Data transfer OUT costs money
- Lambda has time limits
- Root user should not be used

# Quick Memory Tricks
- EC2 = Computer
- S3 = Storage
- RDS = Relational
- DynamoDB = Dynamic NoSQL
- VPC = Virtual network
- IAM = Identity

———--------------------------

# AWS Services by Type (IaaS vs PaaS vs SaaS)
## IaaS (Infrastructure as a Service)
You manage: OS, runtime, apps, data AWS manages: hardware, networking, virtualization  
|Service|Type|
|-------|-------|
|Amazon EC2|IaaS|  
|Amazon EBS|IaaS|  
|Amazon EFS|IaaS| 
|Amazon VPC|IaaS|
|Elastic Load Balancing|IaaS|  
|Amazon Glacier|IaaS|    

Think: Raw infrastructure

## PaaS (Platform as a Service)
You manage: application & data AWS manages: OS, runtime, scaling, patching
|Service|Type|
|-------|-------|
|AWS Elastic Beanstalk|	PaaS|
|AWS Lambda	|PaaS|
|Amazon RDS	|PaaS|
|Amazon Aurora|	PaaS|
|Amazon Redshift	|PaaS|
|Amazon DynamoDB	|PaaS|
|Amazon S3	|PaaS (Managed storage service)|

Think: Managed platform

## SaaS (Software as a Service)
Fully managed application.
Examples (not core AWS infrastructure services):
- Gmail
- Salesforce
- Microsoft 365
AWS mainly provides IaaS + PaaS.

# Study Sheet
## Cloud Computing
**Typical Benefits**  
- Pay-as-you-go pricing
- Scalability
- High availability
- Global reach
- No upfront hardware cost
- Fault tolerance
  
**Typical Services**  
- Compute (EC2, Lambda)
- Storage (S3, EBS)
- Databases (RDS, DynamoDB)
- Networking (VPC)

**IaaS vs PaaS vs SaaS**  
|Model|	You Manage	|AWS Manages|
|-----|-------------|-----------|
|IaaS|	OS, apps|	Hardware|
|PaaS|	Apps only	|OS + infrastructure|
|SaaS	|Nothing|	Everything|  

## Identity & Access Management
**AWS Identity and Access Management** 
Controls permissions.  
Core Components:  
- Users
- Groups
- Roles
- Policies (JSON permissions)  
Remember:  
- Least privilege principle
- MFA recommended
- Root user = avoid using
  
**AWS Accounts**
- One account = one billing unit
- Root user created first

# AWS Organizations
- Manage multiple accounts
- Use OUs (Organizational Units)
- Apply Service Control Policies (SCPs)

# Cloud Networking
**Regions & AZs**
- Region = geographic area
- AZ = isolated data center within region
- High availability = multiple AZs
**Edge Locations**  
Used by:  
- Amazon CloudFront (CDN)

## VPC
**Amazon VPC**  
Components:  
- Subnets (public/private)
- Route tables
- Internet Gateway
- NAT Gateway
- VPC Endpoints

## Security
**Security Groups**  
- Stateful
- Instance level
- Allow rules only
**NACLs (Network ACLs)**  
- Stateless
- Subnet level
- Allow & Deny rules

## Gateways
- Internet Gateway → Public internet access
- NAT Gateway → Private subnet → Internet (outbound only)
- VPC Endpoint → Private AWS service access

## Compute
**Amazon EC2**  
EC2 Configuration:  
- AMI (OS template)
- Instance type (CPU/RAM)
- EBS storage
- Security group
- Key pair
- IAM role

**AWS Lambda**   
- Event-driven
- No server management
- Pay per execution

**AWS Elastic Beanstalk**  
- Upload code
- AWS handles scaling

## Storage & Data
**Storage**  
|Service|	Type|	Use|
|--------|----|-----|
|EBS|	Block	|EC2 disk|
|EFS	|File|	Shared file system|
|S3	|Object|	Files, backups|
|Glacier	|Archive|	Long-term storage|  
  
**Databases**
|Service|	Type|	Use|
|--------|----|-----|
|RDS	|Relational|	SQL databases|
|Aurora|	Relational	|High-performance SQL|
|DynamoDB|	NoSQL	|Key-value|
|Redshift	|Data warehouse	|Analytics|  
  
## Very Important Exam Concepts
- Security Groups = Stateful
- NACL = Stateless
- EC2 = IaaS
- Lambda = PaaS
- RDS = PaaS
- S3 = Object storage
- EBS = Block storage
- EFS = File storage
- Multi-AZ = High availability
* Read Replica = Read scaling
* NAT Gateway = Private subnet internet access
