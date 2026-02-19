# Step 1: ALWAYS Think in 5 Layers
When you see an architecture question, mentally break it into:

Front-end / Content delivery

Compute layer

Database layer

Storage

Security & Monitoring

Never start randomly. Follow this order.

# Step 2: Identify Keywords in the Question

For BookHub, the exam gave you hints:

"Scale during holiday traffic spikes" → Auto Scaling

"Protect user account and payment data" → IAM + private subnets + encryption

"Delivered globally with low latency" → CloudFront

"High availability required" → Multi-AZ

"Cost-efficient during low traffic" → Auto Scaling or Lambda

"Monitoring and alerts" → CloudWatch

The exam is practically telling you what to use.

# Step 3: Start With Networking (Most Students Forget This)

Strong answers mention:

VPC

Public subnet

Private subnet

Multi-AZ

Example opening sentence structure:

BookHub will be deployed inside an Amazon VPC spanning multiple Availability Zones for high availability.

That one sentence already shows maturity.

# Step 4: Build It Tier by Tier

Now I’ll walk you through building it logically.

### 1. Content Delivery (eBooks + Static Assets)

Ask yourself:
What is an eBook file?

It’s an object file.

So → S3

But users are global → we add:

→ CloudFront

Why?

Low latency

Caches content

Reduces load on S3

Improves scalability

That alone earns points.

### 2. Compute Layer

We need:

User login

Book browsing

Payments

Reviews

Options:

EC2 + Auto Scaling

Elastic Beanstalk

Lambda (serverless)

Since traffic spikes during holidays, a great answer is:

→ EC2 in Auto Scaling Group
→ Behind an Elastic Load Balancer
→ Across Multiple AZs

Why?

Handles spikes

High availability

Cost control during low traffic

### 3. Database Layer

We need:

User accounts

Purchases

Payment records

Reviews

That is structured relational data.

→ RDS (MySQL/Postgres/Aurora)

Security best practice:

Place RDS in private subnet

Enable Multi-AZ

Automated backups

That’s high-level exam language.

### 4. Security

Mention:

IAM roles (least privilege)

Security Groups

RDS in private subnet

Encryption (S3 SSE, RDS encryption)

MFA for admins

These phrases score very high.

### 5. Monitoring

Mention:

CloudWatch (metrics + alarms)

CloudTrail (audit logs)

That gets you near 9–10 level.

Step 5: Justify Every Service

This is what moves you from 7/10 to 10/10.

Don’t just say:

We use EC2.

Say:

EC2 instances in an Auto Scaling Group allow the application to scale automatically during holiday traffic spikes, ensuring performance while controlling costs during low usage periods.

That is justification.

## Structure You Should Use on the Test

Use this template structure:

Introduction (VPC + Multi-AZ)

Content Delivery (S3 + CloudFront)

Compute (EC2 + ELB + Auto Scaling)

Database (RDS in private subnet)

Security (IAM, encryption)

Monitoring (CloudWatch)

Conclusion sentence tying to scalability + cost + security


# Examples
## PhotoShare  
PhotoShare is a social web application that allows users to upload, view, and
share photos. Users can comment on photos, follow other users, and receive
notifications when friends post new content.

Excellent (9-10):  
User-uploaded photos are store on Amazon S3, highly scalable object storage with
virtually unlimited capacity. S3 Intelligent-Tiering automatically moves less-
frequently accessed photos to lower-cost storage classes, optimizing cost without
sacrificing performance. Amazon CloudFront is used as a content delivery network
(CDN), reducing latency and offloading traffic from the original S3 buckets. The
backend runs on Amazon EC2 instances deployed across multiple Availability
Zones in a public VPC subnet and placed behind an Elastic Load Balancer
(ELB) to distribute incoming traffic evenly, ensuring high availability and resilience
to instance failures. Auto Scaling automatically adjusts the number of EC2
instances based on traffic patterns, allowing the app to handle traffic spikes while
controlling costs during low-traffic periods. User and session data can be stored in a
private subnet in Amazon RDS, a managed relational database with automated
backups. IAM is used to enforce least-privilege access, securing both administrative
users and backend services, while S3 bucket policies and RDS security groups
ensure that data is protected and only accessible to authorized services. Amazon
SNS enables push notifications to alert users when friends post new photos or
comments. Amazon CloudWatch monitors EC2 performance metrics, tracks
database health, and sets alarms that trigger scaling actions.

## TrafficWatch  
A municipality wants to monitor traffic conditions using live camera data and
manual reports. The application should allow operators to view camera feeds
(already available via external sources), record incident data, and generate
daily summaries.
  
Excellent (9-10):  
Daily incident reports, summaries, and historical traffic data are stored in Amazon
S3, durable, scalable, and cost-efficient object storage. S3 versioning can track
changes to reports, and S3 lifecycle policies can automatically transition older
reports to lower-cost storage classes such as Glacier, reducing storage costs without
losing data. The backend runs on Amazon EC2 instances deployed across multiple
Availability Zones (AZs) in a public VPC subnet to ensure high availability and
fault tolerance. An Elastic Load Balancer (ELB) distributes incoming traffic while
Auto Scaling automatically adjusts the number of EC2 instances in response to
traffic spikes or failures, maintaining both performance and cost efficiency.
Structured data, including incident details, camera metadata, operator logs, and
user activity, is stored in Amazon RDS, a managed relational database with
automated backups, multi-AZ replication for failover, and the ability to scale
storage and compute resources as traffic and data volume grow. RDS security
groups and IAM roles ensure that only authorized backend services and operators
can access the database, and RDS resides in a private subnet that can only be
accessed by the EC2 instances with an appropriate IAM role. Operator and
administrative access is managed through IAM, enforcing least-privilege policies.
AWS CloudTrail can also be enabled to log all administrative and API actions for
auditing purposes. Amazon CloudWatch monitors EC2 instance performance, RDS
health, and application logs, while alarms notify administrators of any unusual
behavior or failures.

## EduLearn  
EduLearn hosts recorded lectures and quiz materials for thousands of
learners. It should stream video efficiently, track user progress, and ensure
high availability during exam seasons.
  
Excellent (9-10):  
EduLearn can be deployed on AWS Elastic Beanstalk (EB), which abstracts the
underlying infrastructure by automatically provisioning EC2 instances, configuring
Elastic Load Balancing (ELB), and enabling Auto Scaling. This approach allows
the platform to handle peak traffic, such as during exam seasons, without requiring
manual server management, while providing a simpler deployment workflow
compared to managing EC2 instances directly. Lecture videos and quiz materials are
stored in Amazon S3, providing durable, highly available, and cost-efficient object
storage. Amazon CloudFront distributes content globally with low latency,
offloading demand from the S3 origin. For cost optimization, S3 Intelligent-Tiering
or lifecycle policies could be applied to move less-accessed content to lower-cost
storage tiers. User progress and quiz results are stored in Amazon DynamoDB, a
fully managed NoSQL database that offers high scalability and low-latency access.
DynamoDB is suitable for this use case because learner progress and quiz
completion data are often accessed frequently and require flexible, high-throughput
storage. This is preferred over RDS in this scenario because the data access
patterns involve rapid, frequent reads/writes rather than complex relational queries.
IAM roles enforce secure access for administrators, operators, and backend
services, ensuring that each user or service has only the permissions necessary.
Amazon CloudWatch collects performance metrics, logs, and errors from both the
EB environment and DynamoDB, enabling proactive monitoring and alerting

## FinTrack
FinTrack helps small businesses track expenses, upload receipts, and
generate monthly reports. It must protect sensitive financial data, support
multiple roles, and generate reports on demand.
  
Excellent (9-10):  
FinTrack can be a fully serverless application, leveraging AWS Lambda to
handle all backend logic. Lambda provides automatic scaling to handle varying user
demand without requiring manual infrastructure management, ensuring cost
efficiency by charging only for compute used. Amazon API Gateway exposes
secure endpoints with request validation, throttling, and authorization mechanisms.
User authentication and session management can be done using AWS Cognito.
Financial data, user accounts, and role information, being structured, are stored in
Amazon RDS, a managed relational database with automatic backups and
multi-AZ replication. Uploaded receipts are saved as files in Amazon S3 with
server-side encryption (SSE) and versioning enabled to ensure durability,
confidentiality, recoverability. S3 lifecycle policies can automatically transition
older receipts to lower-cost storage tiers such as Glacier, optimizing cost without
sacrificing accessibility. IAM enforces role-based access control, ensuring that
administrators and backend functions have only the permissions necessary to
perform their tasks. Sensitive data access and operations can be logged using AWS
CloudTrail for auditing and compliance purposes. Amazon CloudWatch collects
logs from Lambda executions, monitors performance, and sets alarms for errors or
latency spikes. For notifications, Amazon SNS can alert administrators or users
when critical issues occur. On-demand monthly or ad hoc reports are generated by
invoking Lambda functions that query RDS for financial data and retrieve related
receipts from S3. The resulting reports can be saved back to S3 for secure storage
and downloaded by authorized users
