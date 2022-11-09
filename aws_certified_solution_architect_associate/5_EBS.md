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