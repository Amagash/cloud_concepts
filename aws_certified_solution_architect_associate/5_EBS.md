# Elastic Block Storage (EBS) and Elastic File System (EFS)
## SSD Volumes
Highly available and scalable storage volumes you can attach to an EC2 instance:
-  gp2: General purpose SSD.
   -  suitable for boot disks and general applications
   -  up tp 16 000 IOPS per volume
   -  up to 99.9% durability
-  gp3: General purpose SSD.
   -  suitable for high performance applications
   -  Predictable 3 000 IOPS baseline performance and 125 MB/s regardless of the volume size
   -  up to 99.9% durability
-  io1: provisioned IOPS SSD.
   -  Suitable for OLTP and latency-sensitive applications
   -  50 IOPS/GB
   -  Up to 64 000 IOPS per volume
   -  High performance and most expensive.
   -  up to 99.9% durability
-  io2: provisioned IOPS SSD.
   -  Suitable for OLTP and latency-sensitive applications
   -  500 IOPS/GB
   -  Up to 64 000 IOPS per volume
   -  Latest generation provisioned IOPS volume
   -  99.9% durability


## HDD Volumes
- st1: Throughput optimized HDD
  - Suitable for big data, data warehouses, ETL
  - Max throughput is 500 MB/s per volume
  - Cannot be a boot volume
  - up to 99.9% durability
- sc1: Cold HDD
  - Less frequently accessed data
  - Max throughput of 250 MB/s per volume
  - Cannot be a boot volume
  - Lowest cost
  - up to 99.9% durability


## Volumes and Snapshots
- Volumes exist on EBS, whereas snapshots exist on S3
- Snapshots are point-in-time photographs of volumes and are incremental in nature
- The first snapshot will take some time to create. For consistent snapshots, stop the instance and detach the volume.
- You can share snapshots between AWS accounts as well as between regions, but fist you need to copy that snapshot to target region
- You can resize EBS volumes on the fly as well as changing the volume types

## AMIs: EBS vs Instance store
AMI = a blueprint for an EC2 instance
- Instance store volumes are sometimes called ephemeral storage
- You can reboot both EBS and instance store volumes you will not lose you data.
- Instance store volumes cannot be stopped. If the underlying hosts fails, you will lose your data
- By default, both root volumes will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volume
- EBS-backed instances can be stopped. You will not loose the data on this instance if it is stopped.

## Protecting EBS volumes with encryption
- Data at rest is encrypted inside the volume
- All the data in flight moving between the instance and the volume is encrypted
- All snapshots are encrypted
- All volumes created from the snapshots are encrypted

To encrypt volumes:
1. Create a snapshot of the unencrypted root device volume.
2. Create a copy of the snapshot and select the encrypt option.
3. Create an AMI from the encrypted snapshot.
4. Use that AMI to launch new encrypted instances. 

## What you need to know about EC2 Hibernation
- EC2 Hibernation preserves the in-memoru RAM on persistent storage (EBS)
- Much faster to boot up because you do not need to reload the operating system.
- Instance RAM must be less than 150 GB
- Instance families include C3, C4, C5, M3, M4, M5, R3, R4 and R5
- Available for Windows, Amazon Linux 2 AMI and Ubuntu.
- Instances can't be hibernated for more than 60 days
- Available for on-demand instances and reserved instances.

## EFS Overview
- Supports the network file system version 4 (NFSv4) protocol
- Can support thousands of concurrent NFS connections
- Only pay for the storage you use (no pre-provisioning required)
- Data is stored across multiple AZs within a region
- Can scale up to petabytes
- Read-after-write consistency

If you have a scenario-based question around highly scalable shared storage using NFS, think EFS. 

## FSx Overview
Choose between EFS, FSx for Windows, or FSx for Lustre:
1. EFS: when you need distributed, highly resilient storage for linux instances and linus-based applications
2. Amazon FSx for Windows: When you need centralized storage for Windows-based applications, such as Sharepoint, Microsoft SQL Server, Workspaces, IIS WebServer, or any other native Microsoft application
3. Amazon FSx for Lustre: When you need high-speed, high-capacity distributed storage, This will be for applications that do high performance computing (HPC), financial modeling, etc. Remember that FSx for Lustre can store data directly on S3.

## Storage options
- S3: Used for serverless object storage
- Glacier: Used for archiving objects
- EFS: Network File System (NFS) for Linux instances. Centralized storage solution across multiple AZs.
- FSx for Lustre: File storage for high performance computing Linux file systems
- EBS Volumes: Persistent storage for EC2 instances.
- Instance Store: Ephemeral storage for EC2 instances
- FSx for Windows: File storage for Windows instances. Centralized storage solution across multiple AZs.
- Knowing the different use cases for storage will gain you valuable points in the exam.

## AWS Backup
- Consolidation: Use AWS Backup to back up AWS services, such as EC2, EBS, EFS, Amazon FSx for Lustre, Amazon FSx for Windows File Server, and AWS Storage Gateway.
- Organizations: You can use AWS Organizations in conjunction with AWS Backup to backup your different AWS services across multiple AWS account. 
- Benefits: Backup gives you centralized control, letting you automate your backups and define lifecycle policies for your data. You get better compliance, as you can enforce your backup policies, ensure your backups are encrypted, and audit them once complete.