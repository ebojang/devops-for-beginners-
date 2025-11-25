 
Understanding CIDR (Classless Inter-Domain Routing)
CIDR (Classless Inter-Domain Routing) is a method for allocating and identifying IP address ranges more efficiently than the old class-based system. A CIDR notation consists of an IP address followed by a slash and a number.
The smaller the number after the slash, the **larger the range** of IPs covered. CIDR is widely used in networking, especially for configuring VPCs and security groups in cloud platforms like AWS.


Private IP ADDRESSES
**private networks**, which are used within homes, organizations, or internal systems — and are **not routable on the public internet**.
The main **private IP ranges** are:
- `10.0.0.0` to `10.255.255.255`
- `172.16.0.0` to `172.31.255.255`
- `192.168.0.0` to `192.168.255.255`
Note:
Additionally, `127.0.0.1` is reserved as the **loopback address** used for testing network configurations locally.
It does not need an external network connection. 

PUBLIC IP ADDRESSESS
**public IP addresses**  are **accessible over the internet** and must be globally unique.


VIRTUAL PRIVATE CLOUD (VPC)
**VPC (Virtual Private Cloud)** in AWS is your own **isolated private network** within the AWS cloud.
You can create multiple VPCs in each AWS region (default limit: **5 per region**, but this can be increased).

Each VPC has an **IP range** defined using **CIDR notation**:
- **Smallest range:** `/28` → 16 IP addresses
- **Largest range:** `/16` → 65,536 IP addresses


Understanding Subnets in a VPC (IPv4)
A **subnet** is a smaller network inside your **VPC (Virtual Private Cloud)**. It allows you to divide your VPC into multiple sections.

Subnets can be:
- **Public:** Have internet access (through an Internet Gateway).
- **Private:** No direct internet access.

AWS reserves 5 IP addresses in every subnet — these cannot be used by your instances. For example, in `10.0.0.0/24`:

- `.0` – Network address
- `.1` – AWS VPC router
- `.2` – Amazon DNS server
- `.3` – Reserved for future use
- `.255` – Broadcast address (not supported, but reserved)

**NETWORKING FUNDAMENTAL CONCEPT STATEFUL AND STATELSS:**

**STATEFUL** -  a stateful firewall or system remembers the state of the network connections. 
this means if you allow traffic in one direction (say inbound), the return traffic is automatically allowed -  even if you did not explicitly define a rule for it.
Example, 
You allow inbound traffic on port 80 (HTTP).When the instance replies to that traffic, the **outbound response** is automatically allowed.

**STATELESS** - A **stateless** firewall or system does **not remember** any connection state.  
Each packet is evaluated **independently**, based only on your defined rules.
Example, 
If you allow **inbound HTTP (port 80)** traffic, You must also explicitly allow **outbound HTTP response traffic** — otherwise, the return traffic will be blocked.

INTERNET GATEWAY (IGW)
An **Internet Gateway (IGW)** is a component in AWS that enables resources within a **VPC (Virtual Private Cloud)**—such as EC2 instances or other IP-based services—to communicate with the **internet**.  
It acts as the gateway for both inbound and outbound traffic between your VPC and the outside world.

IGW is :
- **Horizontally scalable**, meaning it can handle increasing traffic loads without manual scaling.
- **Highly available and redundant**, ensuring no single point of failure.


BASTION HOST

- A **Bastion Host** is an EC2 instance that sits in a **public subnet**. 
- A **bastion host** acts as a **secure gateway** to reach private instances safely.
- It **does** have internet access — so you can SSH (connect) into it.
- Once connected to the bastion, you can then **SSH into the private instances** inside the private subnet.

HOW BASTION HOST WORKS 

- **Bastion Host** → in **public subnet** (reachable from the internet).
- **Private Instances** → in **private subnet** (no direct internet access).
- **Admin** → connects to **Bastion Host** → then connects to **Private Instance**.


What is a NAT Gateway?
A **NAT Gateway** is an **AWS-managed service** that allows **instances in private subnets** to **access the internet** (for updates, patches, APIs, etc.) **without allowing inbound internet traffic** to reach them.

It keeps **private instances secure** — they can reach the internet **outbound only**, not the other way around.
* **AZ-specific:** each NAT Gateway is tied to one Availability Zone (AZ).
    - For **redundancy**, you must deploy one per AZ.*
* **Requires an Internet Gateway** to route traffic to the internet.*
* **Cannot serve instances in the same subnet** — private instances must be in a **different subnet**.


**NAT INSTANCE** is more controlled by customer, it's flexible and potentially low cost. However, it required manual management. 


==**NETWORK ACCESS CONTROL LIST (NACL)**==
A **Network Access Control List (NACL)** is a **stateless, subnet-level firewall** in AWS that controls **inbound and outbound traffic** using **allow and deny rules**. Each subnet is associated with one NACL — either the default one or a custom NACL you create.

NOTE:
NACL operates at subnet level, affecting all resources in that subnet
stateless- unlike security groups, NACLs don't automatically allow return traffic - both inbound and outbound rules must be defined. 
* Rules are numbered (1-32,766) - lower numbers have high priority
* by default a new custom NACL denies all traffic until rules are added

==Importance of NACL==
Ideal for **blocking IP ranges or traffic types** across entire subnets, providing an **extra layer of network security** beyond Security Groups.

**Security Groups (SGs)**
Security group operates at the instance level (attached o ec2 instances).
Security groups are stateful, meaning if an inbound request is allowed, the corresponding outbound response is automatically allowed. 

**Traffic flow:**

1. **Inbound:**
    - Traffic first passes through the **NACL inbound rules**.
    - If allowed, it reaches the **Security Group inbound rules** of the instance.
    - If both permit it, the traffic is accepted.
        
2. **Outbound:**
    - When an instance sends traffic out, it first goes through **Security Group outbound rules**.    
    - Then it passes through **NACL outbound rules** before leaving the subnet.


VPC PEERING 

VPC peering allows two virtual private clouds (VPCs) to communicate with each other privately over AWS internal network without sending traffic over the public internet.
When two VPCs are peered, resources (like EC2 instances, databases, etc.) in one VPC can communicate with resources in the other as though they were part of the same network.

NOTE
* The IP address ranges (CIDRs) of both VPCs must be **unique** — overlapping IP ranges will prevent peering.*
* Non-transitive — must connect every pair that needs communication.
* **Route Table Updates Required:**  
After creating a peering connection, you must manually update **route tables** in each VPC’s subnets so traffic knows where to go.

VPC ENDPOINTS
VPC endpoints - privately connect your Virtual Private Cloud (VPC) to AWS services without sending traffic over the public internet

Importance:
VPC endpoints is secured as no need for public ips or NAT gateways.
low latency 


Types of VPC Endpoints 
* Interface Endpoint -  uses private link , creates an Llastic Network Interface (ENI) in your subnet.
* Gateway Endpoint - works only for S3 and Dynamo DB - this adds a route in your vpc route table pointing to the service.


Egress-only Internet Gateway
An egress-only internet gateway (EOIG) is an AWS networking component designed specifically for ipv6 traffic. 
it's similar to Internet Gateway but only allows outbound traffic from your vpc to the internet for ipv6 addresses
It blocks inbound traffic initiated from the internet, making it a security measure for IPv6-enabled resources.
NOTE:
For IPv6, NAT isn’t applicable because IPv6 addresses are globally unique and routable.


How Egress-only internet gateway flows traffic:
Instances in private subnets with IPv6 addresses send outbound requests.
EOIG forwards these requests to the internet.
Any inbound traffic that wasn’t initiated by the instance is blocked.


IPV4 AND IPV6 ROUTING IN VPC 

VPC supports dual-stack networking , meaning you can use IPV4, IPV6 or both.

IPV4 ROUTING IN VPC
* VPCs typically use private IPv4 CIDR blocks (e.g., 10.0.0.0/16)
* Each subnet in the VPC is associated with a route table which define where traffic goes based on destination CIDR.
* fir internal traffic: Routes point to local (the vpc itself)
* for internet access, add a route 0.0.0.0/0 pointing to an **internal Gateway.
* for private subnets needing outbound ipv4 internet access, traffic goes through a NAT Gateway**
* For inter-VPC communication, routes point to VPC Peering or Transit Gateway.

IPV6 ROUTING
* IPV6 routes are seperate but in the same route table. 
* add a route to ::/0 pointing to an Internet Gateway (IGW)
* IPv6 is globally routable, so NAT is not used. Instead, security relies on Security Groups and Network ACLs.
* for outbound only ipv6 traffic use Egress-Only Internet Gateway (EOIGW)

QUESTION
What Happens When Two Resources Access Internet Simultaneously
Both resources send traffic to the NAT Gateway.
The NAT Gateway performs Network Address Translation:

It maps each private IP and port combination to the public Elastic IP with a unique port.
This is called Port Address Translation (PAT).

So, even though the public-facing IP is the same (the EIP), the NAT Gateway keeps track of sessions internally using port numbers.


DOMAIN REGISTRAR AND DOMAIN SERVICE 

A **domain registrar** is where you purchase and maintain legal ownership of your domain name. A registrar is an organization authorized to sell and manage ownership of domain names. - It ensures that the domain is listed under your name in the global domain registry. EG Godaddy, cloudflare etc 

DNS Service (DNS Hosting Provider) - is where you manage DNS records (A, CNAME, MX, etc.) that direct internet traffic for your domain.

Think: **Registrar = ownership**, **DNS host = traffic direction**.

The registrar is who you _buy_ your domain from and who keeps track of your ownership.  
The DNS service is where you set the records that tell browsers “where to go” when someone types your domain.

AMAZON CLOUDFRONT 
Amazon **CloudFront** is AWS’s global **Content Delivery Network (CDN)**. Its main job is to make your applications load faster and work more efficiently for users all around the world.

How Cloudfront works?
Instead of every user request traveling all the way to your **origin server** (like an S3 bucket, an EC2 instance, or a load balancer), CloudFront stores **cached copies of your content** at **edge locations**.  
These are data centers placed strategically around the world.

Benefits of cloudfront 
- Speed up content delivery
- Reduce load on your servers
- Improve the user experience
- Add powerful layers of security


Cloudfront origins:
In CloudFront, an **origin** is the place where **CloudFront fetches** your content before delivering it to users through its global edge network. Think of the origin as the “source” of your files or data.

==2 main types of origins cloudfront supports:==
1) S3 Bucket origins:Amazon S3 is one of the most popular origins for CloudFront—especially for **static content** like:
- Images, videos, CSS/JS filrs, downloads, static websites
-**Security: OAC (Origin Access Control)** - - Your S3 bucket **cannot be accessed directly** from the internet
- Only CloudFront is allowed to read or write objects
- This prevents bypassing CloudFront security and caching
**CloudFront as Ingress** - can also be set up to **upload files to S3**.

1) Custom Origins (HTTP-based Backends)
A Custom Origin is any server that responds over **HTTP or HTTPS**, such as:
ALB, EC2, On premises server and any http backend 