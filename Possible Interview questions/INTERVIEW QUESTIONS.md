11) what is load balancing and why it is important?
	**Answer:** Load balancing distributes incoming network traffic across multiple servers to ensure no single server is overloaded. It helps improve application availability, reliability, and performance.
	
12) **How does an AWS Elastic Load Balancer (ELB) maintain high availability?**  
**Answer:** ELB constantly checks the health of registered EC2 instances. If an instance fails, ELB automatically routes traffic to healthy instances, keeping the application running smoothly.

13) **What is the difference between a load balancer and a reverse proxy?**  
**Answer:** Both sit between users and servers, but a load balancer mainly distributes traffic evenly, while a reverse proxy can also perform advanced functions like caching, SSL termination, and content-based routing.

4) **How does AWS Application Load Balancer (ALB) handle routing for microservices?**  
**Answer:** ALB can route requests based on URL paths or host headers, directing traffic to specific target groups—ideal for microservice architectures where different services handle different parts of an application. They operate on Layer7 

5) **How does a load balancer determine whether to send traffic to an instance?**  
**Answer:** The load balancer continuously performs health checks (e.g., HTTP requests to a defined port and path). Only instances returning healthy responses (e.g., 200 OK) are eligible to receive traffic.

6) **What happens when an EC2 instance behind an ELB becomes unhealthy?**  
**Answer:** The ELB’s health checks detect the issue and stop routing traffic to that instance, redistributing requests to healthy ones automatically until the failed instance recovers.

7) How are services behind load balancer accessed in AWS?
in AWS services behind a load balancer are accessed using it's DNA name and not the ip address. the reason is because elastic load balancers are designed to be highly available and scalable, so there underlying ip addresses can be changed. The DNS name always resolves to the current set of ips for the load balancer.
8) **What is a target group in an Application Load Balancer, and why is it important?**  
**A:** A target group is a collection of resources (like EC2 instances, ECS tasks, or Lambda functions) that receive traffic from the Application Load Balancer. It’s important because it allows the ALB to route requests efficiently and perform health checks on each resource, ensuring traffic is only sent to healthy targets.

9) What is the main purpose of an SSL/TLS certificate?  
 The main purpose is to **encrypt data in transit** between a client (like a web browser) and a server, ensuring that no one can intercept or read the transmitted information.

10) **What parameters can you configure in an Auto Scaling Group, and why are they important?**   You can configure **minimum**, **desired**, and **maximum** instance counts.
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

26) What does “serverless” mean in AWS?
In AWS, “serverless” means you don’t need to manage or provision servers yourself. AWS runs your code or services automatically, scaling as needed. You just write your code—like in AWS Lambda—and AWS handles everything behind the scenes.

27) **Q1:** How does the number after the slash (the subnet mask) affect the range of IPs in CIDR notation?
The number after the slash specifies how many bits are fixed in the network portion of the address. A **smaller number** (like `/8`) means more bits are available for hosts, resulting in a **larger IP range**, while a **larger number** (like `/30`) means fewer host bits and thus a **smaller range**

28) **What does VPC stand for and what is it used for in AWS?**  
**A1:** VPC stands for _Virtual Private Cloud_. It’s used to create an isolated private network within AWS where you can launch and manage AWS resources securely.

29) **Why should your VPC CIDR range not overlap with other networks?**  
**A1:** Overlapping CIDR ranges cause routing conflicts, preventing proper communication between networks (like between your corporate network and AWS VPCs).

30) **Why does AWS reserve specific IP addresses in every subnet?**  
**A1:** They’re used for internal networking — such as routing (`.1`), DNS services (`.2`), amazon vpc router

31) **What is an Internet Gateway (IGW) in AWS?**
An Internet Gateway is a VPC component that allows resources like EC2 instances to send and receive traffic from the internet. It acts as a bridge between your VPC and the public internet

32) **If you create and attach an Internet Gateway to a VPC, do instances automatically get internet access?**
No. In addition to attaching an IGW, you must update the subnet’s route table to direct outbound traffic (`0.0.0.0/0`) to the IGW. Without the correct route, traffic will not reach the internet.

33) **What are two key characteristics of an Internet Gateway, and how many can be attached to a VPC**?
- An IGW is **horizontally scalable** and **highly available**, with no single point of failure.
- Only **one Internet Gateway can be attached to a VPC** at a time, forming a dedicated connection between that VPC and the internet.

32) why do we need a bastion host?
Because private instances are **not directly reachable from the internet** for security reasons.  
A bastion host allows administrators to **safely manage** those instances without exposing them publicly.

33)  **Where is a Bastion Host usually placed in a VPC?**  
It’s placed in a **public subnet** of the VPC so it can be accessed from the internet.  
The private instances it connects to are located in a **private subnet**.

34) How do Bastion Host and Private Instance Security Groups work together?
- The **Bastion Host’s security group** allows **SSH (port 22)** only from trusted IPs.
- The **Private Instance’s security group** allows **SSH** only from the **Bastion Host’s private IP** or its **security group ID**.  
    This ensures that only connections coming from the bastion can reach the private servers.

34) What is the main purpose of a NAT Gateway or NAT Instance in AWS?
Both allow instances in private subnets to connect to the internet for updates or downloads, while preventing inbound connections from the internet.

35) **How does the availability of a NAT Gateway compare to a NAT Instance?**
NAT Gateways are highly available within an Availability Zone, while NAT Instances need manual failover configuration to achieve similar redundancy.


36) **Why might you choose a NAT Instance over a NAT Gateway?**
You might choose a NAT Instance if you need more control over configuration, want to use it as a bastion host, or prefer a potentially cheaper but manually managed solution.

37) **Explain the scalability and performance differences between a NAT Gateway and a NAT Instance?**
A NAT Gateway automatically scales up to 100 Gbps to handle large amounts of traffic, while a NAT Instance’s throughput is limited by its EC2 instance type. Scaling a NAT Instance requires manually upgrading or adding instances.

38) **How do security management practices differ between NAT Gateway and NAT Instance setups?**
NAT Instances can be associated with security groups for fine-grained control, while NAT Gateways rely on AWS-managed security and routing rules—simpler but less customizable.

39) **What is a Network Access Control List (NACL) in AWS?**
NACL is a subnet-level firewall that controls inbound and outbound traffic using allow and deny rules.

40)  **How is a NACL different from a Security Group?**
NACLs are **stateless** (you must define both inbound and outbound rules), while Security Groups are **stateful** (return traffic is automatically allowed).

41) **In what scenario would you use a NACL instead of or in addition to a Security Group?**
You’d use a NACL when you want to **block or allow specific IP addresses or ranges** at the **subnet level**, affecting multiple instances at once — such as blocking malicious IPs across an entire network segment.


42) **What happens if a NACL does not have an outbound rule allowing traffic?**
The traffic will be **blocked**, even if the Security Group allows it, because NACLs are **stateless** and require explicit outbound rules.


43) **Explain how traffic flows when an external client connects to an EC2 instance?**
Inbound traffic first passes through the **NACL inbound rules** for the subnet. If allowed, it reaches the **Security Group inbound rules** for the instance. If both permit the traffic, it’s delivered. The return traffic follows the reverse path — and since SGs are stateful, their response is allowed automatically, but the NACL outbound rules must also allow it.

44) **Why might an EC2 instance fail to access the internet even though its Security Group allows outbound traffic?**
Because the **NACL outbound rules** may not allow the traffic. Since NACLs are stateless, they require explicit outbound permissions even if inbound rules exist.

45) **Why might an organization use VPC Peering between departments?**
To allow secure, internal communication between departmental VPCs (like Sales and Marketing) without exposing data to the public internet.

46) **If communication between two peered VPCs isn’t working, what are the two most likely configuration issues?**
Either the **route tables** haven’t been updated properly, or the VPCs have **overlapping CIDR ranges** preventing the peering connection.


47) What Happens When Two Resources Access Internet Simultaneously
Both resources send traffic to the NAT Gateway.
The NAT Gateway performs Network Address Translation:
It maps each private IP and port combination to the public Elastic IP with a unique port.
This is called Port Address Translation (PAT).
So, even though the public-facing IP is the same (the EIP), the NAT Gateway keeps track of sessions internally using port numbers.

48) What Happens When Two Resources Access Internet Simultaneously
Both resources send traffic to the NAT Gateway.
The NAT Gateway performs Network Address Translation:
It maps each private IP and port combination to the public Elastic IP with a unique port.
This is called Port Address Translation (PAT).
So, even though the public-facing IP is the same (the EIP), the NAT Gateway keeps track of sessions internally using port numbers.

49) What components do you need for your resources in the vpc to get access to the internet?
50) what is  the difference between stateful firewalls and stateless firewalls? stateful firewall essentially is just a security group and a stateless firewall is a NACL, Network Access Control List, NACL.

51) how do you work independently with less or no supervision?
52) read ticket first, understanding ticket> identify unknown > documentation > 
53) What does a successful engineer look like on this team after 6 months?
54) What’s your approach to knowledge sharing across the team?
i'm someone who loves running demos etcc...

55) What’s one thing the team wishes they improved last year, culturally or technically?
