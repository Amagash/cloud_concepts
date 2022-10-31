# Simple Storage Service (S3)
## S3 Overview
### What is S3
- Object storage: S3 provides secure, durable, highly scalable static object storage (photos, videos, code, documents and text files)
- Scalable: Allows to store and retrieve any amount of data from anywhere at very low cost
- Simple: Easy to use with a simple web service interface

Manages data as objects rather dans in file systems or data blocks. It cannot be used to run OS or database.

### S3 Basics
- Unlimited storage
- Up to 5 TB per object
- Store files in buckets (i.e folders)

### S3 Buckets
- Universal Namespace (has to be globally unique)
- Example S3 URLs: 
  - https://bucket-name.s3.Region.amazonaws.com/key-game
  - https://acloudguru.s3.Region.amazonaws.com/Gypsy.jpg
- Uploading files: if the upload is successful, you receive a HTTP200 code
### Key-Value Store
- Key: name of the object (e.g Gypsy.jpg)
- Value: The data itself, which is made up of a sequence of bytes.
- Version ID: important for storing multiple versions of the same object
- Metadata: Data about the data you are storing
### Availability and Durability
S3 is a safe place to store your files:
- Built for availability: 99.95 - 99.99% service availability
- Designed for 99.999999999 (9 decimal places) durability for data stored in S3

S3 standard:
- Data stored redundantly across multiple decices in at least 3 AZs
- Designes for frequent access
- Suitable for most workloads (websites, content distribution, mobile and gaming, and big data analytics)
### Characteristics
- Tiered Storage: S3 offers a range of storage classes designed for different use cases
- Lifecycle Management: define rules to automatically transitions objects to cheaper storage tier or delete objects that are no longer required after a set period of time.
- Versioning: all versions of an object are stored and can be retrieved, including deleted objects.
### Securing your Data
- Server-side encryption: set default encryption on a bucket to encrypt al new objects
- Access Control Lists (ACLs): Define which AWS accounts of groups are granted access and the type of access. You can attach S3 ACLs to individual objects within a bucket.
- Bucket Policies: S3 bucket policies specify what actions are allowed or denied
---
## Securing your Bucket with S3 Block public access
### Object ACLs VS. Bucket policies
Object ACLs work on an individual object level whereas Bucket Policies work on an entire bucket level. 
### Exam tips
- Buckets are private by default. To make it public you have to allow public access on both the bucket and its objects
- Object ACLs: You can make individual objects public using object ACLs
- Bucket Policies: You can make entire buckets public using bucket policies
- HTTP status code: When you upload an object to S3 successfully, you will receive an HTTP 200 code?
---
## Hosting a Static Website Using S3
---
## Versioning Objects in S3
---
## S3 Storage classes
---
## Lifecycle Management with S3
---
## S3 Object lock and glacier vault lock
---
## Encrypting S3 objects
---
## Optimizing S3 performance
---
## Backing up data with S3 replication
---
## SE Exam Tips