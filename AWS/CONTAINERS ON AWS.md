What is Docker?
**Docker** is a platform that allows developers to **build, ship, and run applications anywhere**, by packaging the app with all its dependencies into a **container**.

Docker image-  are templates for creating containers.
A **container** is a **lightweight, portable unit** that includes the application code, libraries, runtime, and dependencies—ensuring consistency across environments.

Docker containers can run on **any system that has Docker installed**, including local machines or cloud platforms like AWS.

- **Docker Engine (Container Runtime)** is installed on a host system (like an EC2 instance or local server).
- Instead of installing applications directly on the OS, Docker allows each application to run inside its **own container**.

Each **container** is isolated — it has its own processes, memory, and file system — but all containers **share the same host OS kernel** and system resources like CPU, memory, and networking.

A Dockerfile defines your app’s setup, you build it into an image, run it as a container, and can share it through registries. Docker simplifies development and deployment by ensuring your app always runs in the same environment everywhere.

- **Dockerfile** – The starting point for any Docker project. It acts as a _recipe_ for building a Docker image, containing instructions like:
    
    - `FROM`: specifies the base image (e.g., Ubuntu 18.04).
    - `COPY`: copies files from your computer into the container.
    - `RUN`: executes commands during the build (e.g., installing dependencies).
    - `CMD`: defines the command to run when the container starts (e.g., launching a Python script).
    - 
- **Build the Image** – Once the Dockerfile is ready, you create an image using `docker build`, giving it a tag or name.
    
- **Run the Container** – You launch a container from the image using `docker run`, which starts your application inside a consistent, isolated environment.
    
- **Push and Pull** – Docker images can be uploaded (_pushed_) to repositories like **Docker Hub** or **Amazon ECR**, and later downloaded (_pulled_) for reuse or sharing.


**Amazon ECS (Elastic Container Service)** is a fully managed container orchestration service that runs and scales Docker containers on AWS.  
When setting up an ECS cluster, you choose a **launch type**, which defines how your containers are deployed and who manages the underlying infrastructure.

### **1. EC2 Launch Type**

- You manage the **EC2 instances (virtual machines)** where containers run.
- Each EC2 instance must have the **ECS agent** installed — this agent registers the instance to the ECS cluster and communicates container status.
- ECS manages container lifecycle (start/stop), but **you handle** instance provisioning, patching, and scaling.
- **Best for:** Users who need control over the underlying servers (e.g., performance tuning, custom AMIs, or compliance).
    

### **2. Fargate Launch Type**
- **Serverless** model — AWS manages all infrastructure.
- You only define **task definitions** (CPU, memory, and networking requirements).
- AWS automatically provisions and scales resources as needed.
- **Best for:** Teams that want to focus on applications, not servers, and need scalability without managing infrastructure.

Amazon ECS Service Auto Scaling dynamically adjusts the number of running ECS tasks based on demand. This helps maintain performance during traffic spikes and reduces costs during low usage.
1) Target Tracking Scaling: Automatically adjusts tasks to maintain a target metric (e.g., CPU at 40%).
2) Step Scaling: Responds to specific thresholds.
3) Scheduled Scaling: Predefined scaling based on predictable traffic patterns.



AMAZON ELASTIC KUBERNETES SERVICE (EKS)
Amazon EKS (Elastic Kubernetes Service) is a fully managed service that allows you to run Kubernetes on AWS without managing the underlying infrastructure. AWS handles the Kubernetes control plane, including updates, patching, and scaling.


EKS vs ECS:
ECS is AWS-native, simpler, and tightly integrated with AWS services.
EKS is Kubernetes-based, making it cloud-agnostic and portable across platforms like GCP and Azure.




