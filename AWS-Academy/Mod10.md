# Automatic Scaling and Monitoring
- For when traffic is high, you want more stuff, but if traffic is low, you dom't want overkill

## Elastic Load Balancing
- Like a traffic guard, it redirects traffic to the differnt reaources
- 3 types of load balancers
- Application, Network, Gatway
![alt text](<Screenshot 2026-02-10 102041.png>)

### How Elastic Load Balancing Works
- A load balancer accepts incoming traffic from clients and routes requests to its registered targets (such as EC2 instances) in one or more Availability Zones. 
- You configure your load balancer to accept incoming traffic by specifying one or more listeners. 
- A listener is a process that checks for connection requests. 
- It is configured with a protocol and port number for connections from clients to the load balancer. 
- Similarly, it is configured with a protocol and port number for connections from the load balancer to the targets. 
- You can also configure your load balancer to perform health checks, which are used to monitor the health of the registered targets so that the load balancer only sends requests to the healthy instances. 
- When the load balancer detects an unhealthy target, it stops routing traffic to that target. 
- It then resumes routing traffic to that target when it detects that the target is healthy again.
------
- load balancing is distrubting the load 

-cloudWatch - set up alarms, events, response you can configure to watch for things and do something
- clioudtrail - is a history log, anything that something does, is logged

- Mointoring can help: save maoney, let you know what you are acutally using 

### CloudWatch
- monitors AWS resources and applications 
- collects and tracks standard and custom metrics
- and set up alarms, notifcations 
- Events, defining rules that does something to an AWS envirnoment/tool despending on an alarm/alert

SNS - Simple Notification Service

Some actions include:
- Auto scaling
- EC2 action
- system manager action

### EC2 Auto Scaling
- reduces unused capacity, and over used capacity
- scaling provides a supply and demand solution
- helps you maintain application availability
- automatically add or remove EC2 instances
- detects impaired EC2 instances and replaces
- scaling options, manual, scheduled, dynamic or on-demand, and predictive
------
- lets you create an auto scaling group that is a collection of EC2 instances and is used to auto scaling and management
- scale out is adding EC2 instances, scale in is removing EC2 instances
![alt text](<Screenshot 2026-02-10 104934.png>)
---------
- AUTO SCALING: anothing service that monitors application and sutomatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost
- provides a simple, powerful user interface that enables you to build scaling plans for resources including: Amazon EC2 instances and Spot Fleets, Amazon Elastic Container Service (Amazon ECS) Tasks, Amazon DynamoDB tables and indexes, Amazon Aurora Replicas