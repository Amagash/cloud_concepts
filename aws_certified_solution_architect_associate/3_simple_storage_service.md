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

You can use S3 to host static websites, such as .html sites.
- Bucket policies: Make entire buckets public using bucket policies.
- Static Content: Use S3 to host static content only (not dynamic).
- Automatic Scaling: S3 scales automatically with demand.

---
## Versioning Objects in S3
### Advantages of versioning
- All versions: you can store all versions of an object
- Backup: Can be great backup tool
- Cannot be disabled: once enabled, it cannot be disabled, only suspended
- lifecycle rules: can be integrated with lifecycle rules
- Supports MFA
---
## S3 Storage classes
### S3 stantard
- Built for availability: 99.95 - 99.99% service availability
- Designed for 99.999999999 (11 decimal places) durability for data stored in S3
- Data stored redundantly across multiple decices in at least 3 AZs
- Designes for frequent access
- Suitable for most workloads (websites, content distribution, mobile and gaming, and big data analytics)
### S3 Standard-Infrequent Access (S3 Standard-IA)
- Rapid access: used for data that is accessed less frequently but requires rapid access when needed. 
- Pay to access the data: low per-GB storage price and a per-GB retrieval fee
- Use case: Great for long term storage, backups, and as a data store for disaster recovery files
### S3 One Zone-Infrequent Access
Like Standard-IA but data is stored redundantly within a single AZ. This cost 20% less and is great for long-lived, infrequently accessed, non critical data.
### S3 Intelligent-Tiering
Automatically moves data to the most cost-effective tier based on how frequently you access each object.
### 3 Glacier Options
Use for archiving data:
- Glacier Instant Retrieval: long-term data archiving with instant retrieval
- Glacier flexible retrieval: can be minutes up to 12h to retrieve.
- Glacier Deep Archive: cheapest solution but takes from 12 hours to 48 hours to retrieve.
### Performance across S3
### Storage Costs
### Exam Tips
|Storage|Availability and durability|AZ(s)|Use Case|
|---|---|---|---|
|S3 Standard|99.99% Availability 11 9's Durability|>=3|Suitable for most workloads (e.g., websites, content distribution, mobile and gaming applications, and big data analytics)|
|S3 Standard IA|99.9% Availability 11 9's Durability|>=3|Long-term, infrequently accessed critical data (e.g., backups, data store for disaster receovery files, etc.)|
|S3 One Zone Infrequent Access|99.5% Availability 11 9's Durability|1|Long term, infrequently accessed, non-critical data|
|S3 Intelligent Tiering|99.9% Availability 11 9's Durability|>=3|Unknown or unpredictable access pattern|
|S3 Glacier instant retrieval|99.99% Availability 11 9's Durability|>=3|Provides long term data archiving with instant retrieval time for your data|
|S3 Glacier flexible retrieval|99.99% Availability 11 9's Durability|>=3|Ideal storage class for archive data that does not require immediate access but needs the flexibility to retrieve large sets of data at no cost, such as backup or disaster recovery use cases. Can be minutes up to 12 hours|
|S3 Glacier Deep Archive|99.99% Availability 11 9's Durability|>=3|Cheapest storage class and designed for customer that retain data sets for 7-10 years or longer to meet customer needs and regulatory compliance requirements. The standard retrieval is 12h and the bulk retrieval time is 48 hours.|




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