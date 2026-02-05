# Storage

- Amazon EBS provides block-level storage volumes for use with Amazon EC2 instances.
- Amazon EBS volumes are off-instance storage that persists independently from the life of an instance.
- They are analogous to virtual disks in the cloud. Amazon EBS provides three volume types: General Purpose SSD, Provisioned IOPS SSD, and magnetic.
- The three volume types differ in performance characteristics and cost, so you can choose the right storage performance and price for the needs of your applications.
- Additional benefits include replication in the same Availability Zone, easy and transparent encryption, elastic volumes, and backup by using snapshots.


## Amazon S3

- Create buckets
- upload any number of objects to the bucket

- outside requests costs money, internal data transfer is free
- If you don't store anything you don't pay

- You can access buckets through URL, and conrtol securtiy

## Elastic File System (EFS)
- attached to the router, any device in your network can access

- this is good for if you need a lot of data transfer
- its shared storage

- it can handle any amount of data dynamically (hence elastic)
- Supports Network File System

- Implementation:
1. Create your Amazon EC2 resources and launch your Amazon EC2 instance.
2. Create your Amazon EFS file system.
3. Create your mount targets in the appropriate subnets.
4. Connect your Amazon EC2 instances to the mount targets.
5. Verify the resources and protection of your AWS account.

- Mount target: To access your file system, you must create mount targets in your VPC. Each mount target has the following properties:
- The mount target ID
- The subnet ID for the subnet where it was created
- The file system ID for the file system where it was created
- An IP address where the file system can be mounted
- The mount target state

## Amazon S3 Glacier
- after a certain amount of time, it's archived. You can configure it so that the archvies are deleted after a while
- For archiving basically

- Glacier is like 'built' on top of S3, a sub-category if you will
- There are lifecycle polices, that basically are the rules that sets the time frame for data to be moved from S3 bucket, to infeuqtemly used data, to archived data (glacier), to deleted data

- You'd like your data to be encrypted
- You can use IAM to control access to the data for extra security

- 
 
