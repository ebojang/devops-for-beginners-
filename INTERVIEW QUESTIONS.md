1) what is load balancing and why it is important?
	**Answer:** Load balancing distributes incoming network traffic across multiple servers to ensure no single server is overloaded. It helps improve application availability, reliability, and performance.
2) **How does an AWS Elastic Load Balancer (ELB) maintain high availability?**  
**Answer:** ELB constantly checks the health of registered EC2 instances. If an instance fails, ELB automatically routes traffic to healthy instances, keeping the application running smoothly.
3) **What is the difference between a load balancer and a reverse proxy?**  
**Answer:** Both sit between users and servers, but a load balancer mainly distributes traffic evenly, while a reverse proxy can also perform advanced functions like caching, SSL termination, and content-based routing.
4) **How does AWS Application Load Balancer (ALB) handle routing for microservices?**  
**Answer:** ALB can route requests based on URL paths or host headers, directing traffic to specific target groups—ideal for microservice architectures where different services handle different parts of an application. They operate on Layer7 
5) **How does a load balancer determine whether to send traffic to an instance?**  
**Answer:** The load balancer continuously performs health checks (e.g., HTTP requests to a defined port and path). Only instances returning healthy responses (e.g., 200 OK) are eligible to receive traffic.
6) **What happens when an EC2 instance behind an ELB becomes unhealthy?**  
**Answer:** The ELB’s health checks detect the issue and stop routing traffic to that instance, redistributing requests to healthy ones automatically until the failed instance recovers.