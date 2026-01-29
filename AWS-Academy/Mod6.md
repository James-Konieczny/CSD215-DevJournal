# Mod 6
## Compute Services
- EC2 (infrastures as a service)
- elastic beanstalk and lambda (platform as a service)

| Services | Key Concepts | Characteristics | Ease of Use |
|----------|--------------|-----------------|-------------|
| Amazon EC2 | Infrasture as a service (IaaS). Instance-based. Virtual machines. | Provision virtual machines that you can manage as you choose. | A familiar concept to many IT professionals. |
| AWS Lambda | Serverless computing. Function-based. Low-cost. | Write and deploy code that runs on a schedule or that can be triggered by events. Use when possible (artchitect for the cloud) | A relatively new concepts for IT staff members, but easy to use after you learn how. |
| Amazon ECS, Amazon EKS, AWS Fargate, Amazon ECR | Container-based computing. Instance-based. | Spin up and run jobs more quickly. | AWS Fargate reduces administrative overhead, but you can use options that give you more control. |
| AWS Elastic Beanstalk | Platform as a service (PaaS). For web applications. | Focus on your code (building your application). Can easily tie into other services; database, domain name system (DNS), etc. | Fast and esay to get started. |

- You can create your own AMI, by launching an instance that is unmodified, then you modifiy it with what operating system and software you'd like.
- Create an AMI (create image) of your instance, and then you can create new instances with the AMI

**EC2 instance type**
<img width="1165" height="654" alt="image" src="https://github.com/user-attachments/assets/4056fc72-df9d-4f43-9c74-a1da74379617" />
<img width="1167" height="656" alt="image" src="https://github.com/user-attachments/assets/10181639-c2e8-4896-8564-400db2390d23" />

----------------
- Cloud Watch to monitor EC2 instances
