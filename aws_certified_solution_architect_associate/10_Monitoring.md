# CloudWatch Overview
CloudWatch is a monitoring and observability platform. It allows:
- System metrics: Metrics about the services you use
- Application Metrics: get information from inside your EC2
- Alarms: alarm when something goes wrong

It is agent based, meaning is must be installed and configured. It's not automatic.

## Metrics
- Default: provided out of the box (i.e CPU utilization, network throughput)
- Custom: provided using CloudWatch agent installed on the host (i.e EC2 memory utilisation, EBS storage capacity)

## CloudWatch logs
Allow to monitor, store and access log files. 
- Log event: This is a data point. It contains a timestamp and the data. 
- Log Stream: A collection of those events from the same source.
- Log Group: A collection of log streams. 

### Log features: 
- Filter patterns: You can look for specific terms in your logs (i.e 400 errors in your web server logs).
- CloudWatch Logs Insights: Allows you to query all your logs using a SQL-like interactive solution.
- Alarms: You can create alerts on identified patterns/trends.

## Monitoring with Amazon Managed Service for Prometheus and Amazon Managed Grafana
### Amazon Managed Grafana
Fully managed AWS service allowing secure data viz for instantly **querying**, **correlating** and **vizualizing** your operational metrics, logs and traces from different sources.

- Grafana made easy: It makes it easy to deploy and operate Grafana on AWS. 
- Logical Separation: Workspaces allow for separation of data viz.
- AWS Managed: AWS handles scaling, setup and maintenance of all workspaces.
- Secure: Built-in security features help you meet corporate governance and compliance requirements.
- Pricing: based per active user in a workspace.
- Data Sources: Integrate it with several sources including:
  - Amazon CloudWatch
  - Amazon Managed Service for Prometheus
  - Amazon Opensearch service
  - Amazon Timestream
  - AWS X-ray

Use cases:
- Container Metric Viz
- IoT
- Troubleshooting
### Amazon Managed Service for Prometheus
**Serverless**, **Prometheus-compatible service** used for **securely monitoring container** metrics at scale. 
- Open Source Prometheus
- Automatic scale
- Designed for high availability
- Choose your kubernetes
- PromQL
- Data retention: 150 days.

## Exam tips
Ask yourself:
- What is the best tool to monitor with? 
- Is that metrics available by default? 
- Where can I find the logs? 
- Do I need to adjust my alarm threshold?

What to know:
- Alarms => CloudWatch
- Be careful not everything should go through CloudWatch.
- Know your intervals.
- Logs => CloudWatch Logs
- SQL? Think CloudWatch Logs insights
- Real time =>  Kinesis
- Visualization of metrics => Grafana
- Monitoring container metrics at scale => Amazon Managed Service for Prometheus
- 