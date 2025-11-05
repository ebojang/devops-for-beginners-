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

7) **What is a target group in an Application Load Balancer, and why is it important?**  
**A:** A target group is a collection of resources (like EC2 instances, ECS tasks, or Lambda functions) that receive traffic from the Application Load Balancer. It’s important because it allows the ALB to route requests efficiently and perform health checks on each resource, ensuring traffic is only sent to healthy targets.

8) What is the main purpose of an SSL/TLS certificate?  
 The main purpose is to **encrypt data in transit** between a client (like a web browser) and a server, ensuring that no one can intercept or read the transmitted information.

9) **What parameters can you configure in an Auto Scaling Group, and why are they important?**   You can configure **minimum**, **desired**, and **maximum** instance counts.
- _Minimum_ ensures baseline availability.
- _Desired_ defines the target number of instances.
- _Maximum_ prevents excessive scaling and cost overruns.  
These settings help balance performance and cost effectively.

9) **What is a Docker image, and how is it different from a container?**   
A Docker image is a read-only blueprint that defines everything an application needs to run. A container is a running instance of that image—essentially the live, executable version.

10) Explain how Docker ensures application consistency across environments?
Docker packages the entire application environment—including code, dependencies, and runtime—inside containers, ensuring the same setup in development, testing, and production.

11) **Describe the Docker lifecycle from image to running container.**  
First, a Docker image is built (from a Dockerfile). When executed, Docker creates a container from that image. The container runs as an isolated instance of the application until it’s stopped or removed.

12)  How can you run Docker containers on AWS?
You can run Docker containers on AWS using services like **Amazon ECS (Elastic Container Service)**, **Amazon EKS (Elastic Kubernetes Service)**, or **AWS Fargate** for serverless container execution.

13) **What is Amazon ECS?**  
**Answer:**  
Amazon ECS is a fully managed container orchestration service that allows you to deploy, manage, and scale Docker containers on AWS easily without having to install or operate your own container management system.

14) What is Amazon ECS used for?
Amazon ECS (Elastic Container Service) is used to run and manage Docker containers on AWS. It handles deploying, scaling, and maintaining containerized applications.

15) What does the ECS agent do in the EC2 launch type?
The ECS agent runs on each EC2 instance and connects it to the ECS cluster. It reports the instance’s status and helps ECS manage and run containers on that instance.

16) **When would you choose the EC2 launch type instead of Fargate?**    
You’d choose EC2 when you need full control of the infrastructure—for example, using custom AMIs, tuning instance types for performance, or meeting strict compliance requirements. It’s also useful when cost optimization or specialized workloads require instance-level configuration.

17) **How does Fargate simplify container scaling compared to EC2?**  
With EC2, scaling requires adding or removing EC2 instances manually or via auto-scaling groups. In Fargate, you only increase or decrease the number of container tasks, and AWS automatically handles provisioning and scaling behind the scenes.

18) **3. What are ECS task definitions, and why are they important in Fargate?**   
A task definition is a blueprint that defines how a container should run, including CPU, memory, networking, and image details. In Fargate, task definitions are essential because they tell AWS exactly what resources to allocate for your containers since there are no EC2 instances to manage manually.


19) Why does the ECS Agent need permissions?
    To perform tasks like sending logs, pulling container images, and accessing secrets securely.


20)  Why is it important to use IAM roles in ECS?
To ensure secure and controlled access to AWS services, following the principle of least privilege.

21) How do you assign an ECS Task Role to a container?
A: By specifying the IAM role in the ECS task definition under the taskRoleArn field.

22) How does using separate ECS Task Roles improve security?
A: It allows each container to have only the permissions it needs, reducing the risk of unauthorized access or misuse of AWS resources.

23) : What happens if the EC2 Instance Profile lacks necessary permissions?
A: The ECS Agent may fail to perform tasks like sending logs or pulling images, leading to container launch failures or monitoring issues.

24) What is ECS Service Auto Scaling?
    It’s a feature that automatically adjusts the number of ECS tasks based on metrics like CPU usage or traffic, helping maintain performance and reduce costs.

25) What is target tracking in ECS auto scaling?
Target tracking keeps a specific metric, like CPU utilization, at a desired level by automatically scaling tasks up or down











	
