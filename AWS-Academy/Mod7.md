# Storage


## EBS
- Amazon EBS provides block-level storage volumes for use with Amazon EC2 instances.
- Amazon EBS volumes are off-instance storage that persists independently from the life of an instance.
- They are analogous to virtual disks in the cloud. Amazon EBS provides three volume types: General Purpose SSD, Provisioned IOPS SSD, and magnetic.
- The three volume types differ in performance characteristics and cost, so you can choose the right storage performance and price for the needs of your applications.
- Additional benefits include replication in the same Availability Zone, easy and transparent encryption, elastic volumes, and backup by using snapshots.

Amazon Elastic Block Store (Amazon EBS) offers persistent storage for Amazon EC2 instances. Amazon EBS volumes are network-attached and persist independently from the life of an instance. Amazon EBS volumes are highly available, highly reliable volumes that can be leveraged as an Amazon EC2 instances boot partition or attached to a running Amazon EC2 instance as a standard block device.

When used as a boot partition, Amazon EC2 instances can be stopped and subsequently restarted, enabling you to pay only for the storage resources used while maintaining your instance's state. Amazon EBS volumes offer greatly improved durability over local Amazon EC2 instance stores because Amazon EBS volumes are automatically replicated on the backend (in a single Availability Zone).

For those wanting even more durability, Amazon EBS provides the ability to create point-in-time consistent snapshots of your volumes that are then stored in Amazon Simple Storage Service (Amazon S3) and automatically replicated across multiple Availability Zones. These snapshots can be used as the starting point for new Amazon EBS volumes and can protect your data for long-term durability. You can also easily share these snapshots with co-workers and other AWS developers.

- EBS Documentation: https://aws.amazon.com/ebs/

- Amazon EBS volumes deliver the following features:
- Persistent storage: Volume lifetime is independent of any particular Amazon EC2 instance.
- General purpose: Amazon EBS volumes are raw, unformatted block devices that can be used from any operating system.
- High performance: Amazon EBS volumes are equal to or better than local Amazon EC2 drives.
- High reliability: Amazon EBS volumes have built-in redundancy within an Availability Zone.
- Designed for resiliency: The AFR (Annual Failure Rate) of Amazon EBS is between 0.1% and 1%.
- Variable size: Volume sizes range from 1 GB to 16 TB.
- Easy to use: Amazon EBS volumes can be easily created, attached, backed up, restored, and deleted.

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
 
