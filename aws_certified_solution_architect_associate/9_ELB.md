# Elastic Load Balacing
ELB automatically distributes incoming application traffic across multiple targts, such as Amazon EC2 instances. This can be done across multiple AZs.
There are 3 different types of load balancer:
- Application Load Balancer: Best for balancing of HTTP and HTTPS traffic. They operate at layer 7 and are application-aware. Intelligent Load Balancer
- Network load Balancer: Operating at the connection level at layer 4. They handle millions of requests per second while maintaining ultra low latency. Performance Load Balancer.
- Classic load Balancer: Legacy Load Balancer for classic/test/dev. 

The status of the instances that are healthy at the time of the health check is InService otherwise the status is OutOfService. The load balancer performs health checks on all registered instances. It then routes requests only to the healthy instances. The routing resumes to instances when it has been restored to the healthy state.
