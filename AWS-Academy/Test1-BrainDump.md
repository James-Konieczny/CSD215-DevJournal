The 6-Layer Architecture Formula (Use This Every Time)

When you see a design question, think in this order:

Layer	Ask Yourself	Typical AWS Services
🌍 Global Delivery	Do users need low latency worldwide?	S3 + CloudFront
💻 Compute	Where does the application logic run?	EC2, Auto Scaling, ELB, Lambda, Elastic Beanstalk
🗄 Database	Is the data structured or NoSQL?	RDS, Aurora, DynamoDB
📦 Storage	Are we storing files or objects?	S3, EBS, EFS, Glacier
🔐 Security	How do we protect access?	IAM, Security Groups, NACLs, Encryption
📊 Monitoring	How do admins monitor it?	CloudWatch, CloudTrail

If you mention all 6 layers, you’re already near 8/10.

2️⃣ Core Service Cheat Sheet Table
🌍 Global & Networking
Service	What It Does	Use It When
Region	Geographic location	Choose based on users
Availability Zone (AZ)	Isolated data center	For high availability
VPC	Virtual network	Always mention it in design
Public Subnet	Has internet access	Web servers, load balancers
Private Subnet	No direct internet	Databases
CloudFront	CDN	Global content delivery
Internet Gateway	Connects VPC to internet	Public resources
NAT Gateway	Private → internet access	Private EC2 needs updates
VPC Endpoint	Private access to AWS services	Secure S3/DynamoDB access
💻 Compute
Service	Type	Best For
EC2	IaaS	Full control servers
Auto Scaling	Scaling	Handle traffic spikes
Elastic Load Balancer (ELB)	Traffic distribution	High availability
Elastic Beanstalk	PaaS	Easier app deployment
Lambda	Serverless	Event-driven apps, variable traffic
Quick Decision Rule:

Need full control? → EC2

Want easier management? → Elastic Beanstalk

Traffic unpredictable? → Lambda

🗄 Storage
Service	Type	Use Case
S3	Object storage	Files, images, videos, static websites
S3 Intelligent-Tiering	Cost optimization	Variable access patterns
Glacier	Archive storage	Long-term backups
EBS	Block storage	Attached to EC2
EFS	Shared file system	Multiple EC2 instances
Quick Rule:

Files? → S3

EC2 disk? → EBS

Shared file system? → EFS

Archive? → Glacier

🗄 Databases
Service	Type	Best For
RDS	Relational	Structured data, transactions
Aurora	High-performance relational	MySQL/Postgres compatible
DynamoDB	NoSQL	High-scale key-value workloads
Redshift	Data warehouse	Analytics & reporting
Quick Rule:

Accounts, payments, structured records? → RDS

Massive scale, flexible schema? → DynamoDB

Analytics? → Redshift

🔐 Security
Service	What It Does	Key Exam Phrase
IAM	Identity & permissions	Least privilege
IAM Roles	Temporary permissions	EC2/Lambda access S3
Security Groups	Instance firewall	Stateful
NACLs	Subnet firewall	Stateless
MFA	Multi-factor authentication	Root protection
Encryption (SSE)	Data protection	At rest encryption
EXAM TRAPS:

Security Groups = stateful

NACLs = stateless

Root account should NOT be used daily

📊 Monitoring
Service	Use For
CloudWatch	Metrics, logs, alarms
CloudTrail	Audit API calls
SNS	Notifications
3️⃣ The "If You See This, Use This" Table
Question Mentions	You Should Think
Global users	CloudFront
Static website	S3 + CloudFront
Traffic spikes	Auto Scaling
High availability	Multi-AZ
Sensitive database	Private subnet + RDS
Cost optimization	Auto Scaling / Intelligent-Tiering
Monitoring	CloudWatch
Auditing	CloudTrail
Uploading files	S3
Relational data	RDS
Massive scale NoSQL	DynamoDB
4️⃣ High-Scoring Design Keywords

If you use these phrases, graders love it:

"Multi-AZ deployment"

"Least privilege access"

"Private subnet for database"

"Elastic scalability"

"Cost optimization"

"High availability"

"Managed service reduces operational overhead"

"Server-side encryption"

"Auto Scaling adjusts capacity based on demand"

5️⃣ The 10/10 Written Answer Formula

Use this paragraph flow:

Deploy in VPC across multiple AZs

Use ELB + Auto Scaling for compute

Store files in S3

Use CloudFront for global delivery

Store structured data in RDS (private subnet)

Secure with IAM + Security Groups + encryption

Monitor with CloudWatch

Conclude with scalability + security + cost efficiency

That’s literally the pattern used in high-scoring answers like the examples in your rubric 

Test 1 - Sample Written Respons…

.

6️⃣ Final Memory Trick (The “S.C.A.L.E.D.” Method)

When designing:

S – Storage
C – Compute
A – Access control
L – Load balancing
E – Elastic scaling
D – Database

Run through that checklist before finishing your answer.
