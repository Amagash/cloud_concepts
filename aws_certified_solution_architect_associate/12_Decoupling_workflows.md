# Overview
Always want loose coupling (have load balancers) instead of tight coupling (i.e one EC2 instance talking directly to another EC2 instance without a Load balancer). 
# Simple Queue Service (SQS)
SQS is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. It's like a ELB but with a buffer.
## Poll-Based Messaging
A producer of a message (i.e you send a letter to your friend) sends it via the SQS (i.e like the post office) and the receiver receives the message whenever it's ready (i.e your friends goes to the mailbox and get the letter)
## Important settings
- Delivery delay: default is 0 and can be set up to 15 minutes
- Message size: Up to 256 KB text in any format
- Encryption: by default messages are encrypted in transit but you can add at-rest.
- Message retention: Default is 4 days and can be set between 1 minute and 14 days. After 14 days, the messages are purged.
- Long VS Short: always look for long polling.
- Queue depth: this can be a trigger for autoscaling if the queue hits a set treshold.
- Visibility timeout: allows to lock a message for 30 seconds.

## Dead-Letter Queues (DLQ)
Messages that fail to be treated are redirected to a DLQ instead of staying in the SQS for 14 days and get purged. Always set an alarm with CloudWatch to monitor the queue depth of the DLQ. Be careful, DLQs are fundamentally no different than SQSs, they're just used differently but they are the same. So they have the same retention window but it allows to treat failed messages without blocking the principal SQS.

## SQS message ordering
### Standard SQS
- Best-effort ordering
- Duplicate messages
- Nearly unlimited transactions per second
### FIFO SQS
- Guaranteed ordering
- No message duplication
- 300 messages per second

# Simple Notification Service (SNS)
SNS is a fully managed massaging service for both application-to-application (A2A) and application-to-person (A2P) communication (i.e send emails or text messages to users).
# API Gateway
API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

# Exam tips
- Never tightly couple, always loosely couple
- Message ordering => SQS FIFO
- Duplication problem => SQS FIFO
- Performance => Standard SQS
- Cost effective => Standard SQS