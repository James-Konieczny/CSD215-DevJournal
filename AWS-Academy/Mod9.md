# Cloud Architecture
- Cloud architectes determine business goals

## AWS Well-Architected Framework
- Cloud architects:
  - Engage with deecision marker to identify the business goal and the capabilities that need improvement
  - Ensure alignement between technolology deliverables of a solution and the business goals
  - Work with delivery teams that are implementing the solution to ensure that the technology features are appropriate
- Having well-architected systems gratly increases the likelylihood of business success

**What is the AWS Well-Architected Framework?
- A guide for designing in frastructures that are
  - Secure
  - High-performing
  - Resilient
  - efficient
- A consistent approach to evaluting and implementing clooud architectures
- a way to provide best practices that were developed through lessons learned by reviewing customer architectures

### 6 Pillars Of The Well-Architected Framework
- operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability

- Each pillar includes a set of design principles and best practice areas. Each best practice area aligns to questions a reviewer should ask when designing an architecture. The questions for each pillar are part of the Well-Architected Framework Appendix.

## AnyCompany background
- sells 3D-printed cityscapes
- AnyCompanyCorporation has three main departments:
  - Fly and Snap –image acquisition, preprocessing, and storage
  - Show and Sell –promoting, selling, and working with customers
  - Make and Ship –manufacturing of products and delivery

## Operational Excellence Pillar
- deliever business value
- Focus: Run and monitor systems to deliver business value, and to continually improve supporting processes and procedures
- Key Topics: automating changes, responding to events, defining standards to amanage daily operations

- perform operations as code
- make frequent, small, reversible changes
- refine operations procedures frequently
- anticipate failure
- learn from all operational events and failures

  **Operational execellence questions**
  <img width="1168" height="657" alt="Screenshot 2026-02-17 101802" src="https://github.com/user-attachments/assets/18e34281-f6f4-48d0-b8c5-81b6d80cdd90" />
- The foundational questions for operational excellence fall under three best practice areas: organization, prepare, operate, and evolve.
- Operations teams must understand business and customer needs so they can effectively and efficiently support business outcomes.
- Operations teams create and use procedures to respond to operational events and validate the effectiveness of procedures to support business needs.
- Operations teams collect metrics that are used to measure the achievement of desired business outcomes.
- As business context, business priorities, and customer needs, change over time, it’s important to design operations that evolve in response to change and to incorporate lessons learned through their performance

## Security Pillar
- Focus: Protect information, systems and assets while delivering business value through risk assessments and mitigation strategies
- Key Topics: Protecting confidentiality and integrity of data
- Identifying and amnaging who can do what
- protecting systems
- establishing controls to detect security events

- Implement a strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events

**Security questions**
<img width="1167" height="660" alt="Screenshot 2026-02-17 102559" src="https://github.com/user-attachments/assets/8203f10d-2f5a-4ea1-a3eb-7014b8bf82fc" />

## Reliability Pillar
- Focus: Ensure a workload performs its intended function correctlu and consistentlu ehrn it's expected to
- Key Topics: Deigning distributed systems, recovery planning handling change
- Automatically recover from failure
- Test recovery procedures
- Scale horizontally to increase aggregate workload availability
- Stop guessing capacity
- Manage change in automation

**Reliability questions**
<img width="1168" height="657" alt="Screenshot 2026-02-17 102936" src="https://github.com/user-attachments/assets/2eeceb05-0a7d-45f8-925f-4cc9db5ae30b" />

## Performance Efficiency Pillar
- Focus: Use IT and computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve
- Key topics: selecting the right resource types and sizes based on workload requirements. monitoring performance. Making informed decisions to maintain efficiency as business needs evolve
- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy

**Performance efficiency questions**
<img width="1167" height="657" alt="Screenshot 2026-02-17 103514" src="https://github.com/user-attachments/assets/4b4a68f5-3b9b-474b-9672-4420c7f994a0" />

## Cost Optimization Pillar
- Focus: Avoid unnecessary costs
- Key topics: understanding and controlling where money is being spent. Selecting the most appropriate and right number of rescource types. analyzing spend over time. scaling to meeting business needs without overspending
- Implement Cloud Financial Management
- Adopt a consumption model
- Measure overall efficiency
- Stop spending money on undifferentiated heavy lifting
- Analyze and attribute expenditure

**Cost optimization quesetions**
<img width="1164" height="653" alt="Screenshot 2026-02-17 104237" src="https://github.com/user-attachments/assets/86eab558-9520-461a-a515-0568fb22866a" />

## The AWS Well-Architected Tool
- Helps you review the state of your workloads and compares them to the latest AWS architecturral best practices
- Gives you access toknowledge and best practices used by AWS architects, whenever you need it
- Delivers an action plan with step-by-step guidance on how to build better workloadds for the cloud
- Provides a consistent process for you to review and measure you cloud architectures

# Reliability and availbility
- Reliability is a measure of your system’s ability to provide functionality when desired by the user.
- Because "everything fails, all the time," you should think of reliability in statistical terms.
- Reliability is the probability that an entire system will function as intended for a specified period.
- Note that a system includes all system components, such as hardware, firmware, and software.
- Failure of system components impacts the availability of the system.
- To understand reliability, it is helpful to consider the familiar example of a car. The car is the system.
- Each of the car’s components (for example, cooling, ignition, and brakes) must work together in order for the car to work properly.
- If you try to start the car and the ignition fails, you cannot drive anywhere—the car is not available.
- If the ignition fails repeatedly, your car is not considered reliable.
- A common way to measure reliability is to use statistical measurements, such as Mean Time Between Failures (MTBF).
-  MTBF is the total time in service over the number of failures.

-  A measure of your system’s ability to provide functionality when desired by the user.
-  Systemincludes all system components: hardware, firmware, and software.
-  Probabilitythat your entire system will function as intended for a specified period.
-  Mean time between failures (MTBF) = total time in service/number of failures
-----------------
- As you just learned, failure of system components impacts the availability of the system.
- Formally, availabilityis the percentage of time that a system is operating normally or correctly performing the operations expected of it (or normal operation time over total time).
- Availability is reduced anytime the application isn’t operating normally, including both scheduled and unscheduled interruptions.
- Availability is also defined as the percentage of uptime (that is, length of time that a system is online between failures) over a period of time (commonly 1 year).
- A common shorthand when referring to availability is number of 9s.
- For example, five 9s means 99.999percentavailability.
- A highly availablesystem is one that can withstand some measure of degradation while still remaining available.
- In a highly available system, downtime is minimized as much as possible and minimal human intervention is required.
- A highly available system can be viewed as a set of system-wide, shared resources that cooperate to guarantee essential services.
-  High availability combines software with open-standard hardware to minimize downtime by quickly restoring essential services when a system, component, or application fails.
-  Services are restored rapidly, often in less than 1 minute.
<img width="1167" height="656" alt="Screenshot 2026-02-17 105355" src="https://github.com/user-attachments/assets/461e5dbc-8207-45c8-9ef8-39f63b86ebcf" />
<img width="1147" height="593" alt="Screenshot 2026-02-17 105437" src="https://github.com/user-attachments/assets/49047d63-a1ec-40e5-be9a-8adbea8c5fff" />

# AWS Trusted Advisor
- Online tool that provides real-time guidance to help you provision your resources following AWS best practices.
- Looks at your entire AWS environment and gives you real-time recommendations in five categories.
- AWS Trusted Advisor looks at your entire AWS environment and gives you recommendations in five categories:
  - Cost Optimization–AWS Trusted Advisor looks at your resource use and makes recommendations to help you optimize cost by eliminating unused and idle resources, or by making commitments to reserved capacity.
  - Performance–Improve the performance of your service by checking your service limits, ensuring you take advantage of provisioned throughput, and monitoring for overutilized instances.
  - Security–Improve the security of your application by closing gaps, enabling various AWS security features, and examining your permissions.
  - Fault Tolerance–Increase the availability and redundancy of your AWS application by taking advantage of automaticscaling, health checks, Multi-AZ deployments, and backup capabilities.
  - Service Limits–AWS Trusted Advisor checks for service usage that is more than 80percentof the service limit. Values are based on a snapshot, so your current usage might differ. Limit and usage data can take up to 24 hours to reflect any changes.
- For a detailed description of the information that AWS Trusted Advisor provides, see AWS Trusted Advisor Best Practice Checks at https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor-check-reference.html.

# Summary
In summary, in this module you learned how to:
- Describe the AWS Well-Architected Framework, including the six pillars
- Identify the design principles of the AWS Well-Architected Framework
- Explain the importance of reliability and high availability
- Identify how AWS Trusted Advisor helps customers
- Interpret AWS Trusted Advisor recommendations
