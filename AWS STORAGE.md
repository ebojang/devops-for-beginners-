
EBS VOLUME - virtual storage device that lives in your cloud and connect to your instance.
Amazon EBS volume is a durable. block -level storage device that you can attach to your instance.
EBS volume can be used as  primary storage for data that requires frequent updates such as system drive for your data.
EBS allows your instances to persist data, even after instance termination.
EBS are bound to a specific availability zone.

AMAZON MACHINE IMAGE (AMI)

Amazon machine image - is a pre-configured template that contains all the information needed to launch an EC2 instance. 
AMI are bult for specific region {and can be copied across region).
faster boot time when launching instance.
multiple instances can be launched with the same configuration, saving time and ensuring consistency.

AMAZON EFS - ELASTIC FILE SYSTEM 
Elastic file system (EFS) - is a managed Network File System (NFS) that can be mounted on many EC2 instances.
* EFS with EC2 instances in multi Availability Zone
* Highly available, scalable
* EFS are expensive 

SCALABILITY AND HIGH AVAILABILITY 

Vertical scalability means increasing the size of the instance.
* vertical scalability is very common for non distributed systems such as database

Horizontal scalability means increasing the number of instances /systems for your application to handle more load.
* very common in web applications and modern cloud applications 
* an Auto scaling group (ASG) and load balancer is used in horizontal scaling to evenly distribute workload
High Availability 
* High availability means running your application or system in at least 2 data centers (availability zone)
* the goal of high availability is to survive data center loss *

LOAD BALANCING
 Load balances are servers that forward traffic evenly to multiple servers (example EC2 instances downstream).
 * elastic load balancer sits between users and the ec2 instances. it checks which ec2 instances are healthy and direct traffic to the ones that can handle. 

Elastic Load Balancers (ELB)
Elastic load balancer is a managed load balancer by AWS:
AWS takes care of upgrades, maintenance, high availability etc 

Reverse Proxy Server -  sits between client devices and backend servers. acting as an intermediary for requests from client. when a client sends in a request for a resource, such as web page or an application, the reverse proxy receives the request on behalf of the backend servers. it then forwards the request to appropriate backend server based on predefined rules or configuration.
 * reverse proxy enhance security y serving as a barrier between the internet and backend servers. it filters out malicious traffic such as hacking attempts.*

HEALTH CHECKS IN LOAD BALANCER
