# Vertical scaling
Increase performance of EC2
# Horizontal scaling
Increase the number of EC2

# Ask yourself
- What do we scale? Launch templates
- Where do we scale? Auto-scaling groups
- When do we scale? Step Scaling

# Launch Templates and configurations
This answers the "What do we scale?"
The launch template specifies all of the needed settings that go into building out an EC2 instance. It is a collection of settings that you can configure so you don't have to walk through the EC2 wizard over and over.

- Templates: 
  - more than just autoscaling
  - supports versioning
  - more granilarity
  - AWS recommended

- Configurations:
  - only for autoscaling
  - immutable
  - limited configuration options
  - don't use them

# Auto scaling groups
Important for high availability applications
- Scale out aggressively
- Scale in conservatively
- Provisioning should be as fast as possible. Bake those AMIs to minimize it
- Cost: use reserved instances to cover the minimum count of EC2 instances and use spot instance to scale with if the use case allows so.
- CloudWatch is your num 1 tool

# 4 ways to scale relational Databases
- Vertical scaling: resizing the DB 
- Scaling storage: you can go up but you can't go back down. (Aurora is doing it automatically)
- Read replicas: create read-only copies and spread out the workload.
- Aurora serverless: we can offload scaling to AWS

# Scale non relational Databases
## DynamoDB
- Scaling is simplified as AWS does the heavy lifting for you.
- Provisioned: most cost effective when workload is generally predictable
- On-demand: less cost effective but useful when workload is sporadic

# Exam tips
- Read-heavy workload => Read Replicas
- Careful with storage => RDS storage only scales up unless you are using Amazon Aurora
- Vertical scaling
- Multi AZ always on
- Whenever possible use Aurora
- Predictable workloads => Provisionned DynamoDB
- Sporadic workloads => On demand dynamoDB
- Auto scaling is only for EC2. No other service can be scaled using auto scaling.
- Favor solutions that are predictive rather than reactive
- Reduce Build times by putting everything in an AMI rather than using user data.
- Spread out your auto scaling groups over multiple AZs.
- ELBs are essentials. Make sure to pick a solution that has an ELB with health checks.