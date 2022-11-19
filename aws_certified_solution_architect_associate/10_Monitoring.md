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

