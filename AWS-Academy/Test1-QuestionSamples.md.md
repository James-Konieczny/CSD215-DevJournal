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
