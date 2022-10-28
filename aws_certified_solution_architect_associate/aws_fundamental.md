# AWS Fundamentals
## The Building Blocks of AWS: Availability Zones and Regions

### AWS Global Infrastructure
24 Regions, 77 Availability Zones (AZ) and 215 edge locations.
### Availability zones
An **AZ** is one or more Data Centers.
### Data Centers
A data center is a building filled with servers in halls.
### Regions
A **Region** is a geographical area (i.e US East (Northern Virginia)) with 2 or more AZ within 100km from each other.
### Edge Locations
An Edge Location is an endpoint for AWS that is used for caching content. 

---

## Who owns what in the cloud?
### The shared responsibility model

If you can do it yourself in the AWS Management Console, chances are that the customer is responsible (i.e security groups, IAM users, patching EC2 OS, patching databases running on EC2, etc.)

If not, AWS is likely reponsible (i.e management of data centers, securioty cameras, cabling, patching RDS OS, etc.)

Encryption is a shared responsibility

---

## Compute, Storage, Databases, and Networking
### Compute
The way we process information:
- EC2
- Lambda
- Elastic Beanstalk

### Storage
A safe place to leave information:
- S3
- EBS: Elastic Block Store
- EFS
- FSx
- Storage Gateway

### Database
Reliable way to store and retrieve information:
- RDS
- DynamoDB
- Redshift

### Networking
Way to our compute, storage and databases to communicate:
- VPCs
- Direct Connect
- Route 53
- API Gateway
- AWS Global Accelerator
---
## What is the well-architected framework?

---
## AWS Fundamentals exam tips
