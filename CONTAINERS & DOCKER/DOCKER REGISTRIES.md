
## 🗂 What is a Docker Registry?
- A **Docker Registry** is like an online library for Docker images (Central storage and distribution hub for docker images).
- It stores, manages, and distributes your images.
- Without a registry, your images only exist locally.
-

What is the difference between ECR and dockerhub?
## Types of Registries
1. **Public Registries**
    - Example: **Docker Hub**
    - Anyone can access or share images (public repository).  
    - Great for open-source use (e.g., pulling a MySQL image).   
2. **Private Registries**
    - Example: **AWS Elastic Container Registry (ECR)**
    - ECR is private repository in nature. 
    - Access is restricted hence ECR is secured.
    - Used for sensitive or proprietary applications or good integration with other AWS services .
    - You control who can see or use your images. organisations can integrate their IAM users with the private ECR repository.



**Why Registries are Important in DevOps**
- **Streamlined Deployment** – Push once, then deploy the same image across dev, test, and production. faster and reliable to rollout new features and updates.
- **Team Collaboration** – Everyone works with the same images from a central source.
- **Consistency** – Eliminates the "works on my machine" problem by ensuring the same image runs everywhere.

## The Typical Workflow
1. **Build** – Create an image locally using a Dockerfile.
2. **Test** – Run it as a container to check it works.
3. **Push** – Upload the image to a registry (e.g., AWS ECR).
4. **Pull** – Download the image from the registry for deployment.
5. **Automate** – CI/CD pipelines can pull images automatically for smooth deployments.#

📦 Essential Commands
- **Push an image** → `docker push <registry>/<image>`
- **Pull an image** → `docker pull <registry>/<image>`
- **Login to a registry** → `docker login <registry>`
## 🐳 What is Docker Hub?
- Docker Hub is the most popular **Docker registry** (like an App Store for Docker images).
- It allows you to **store, share, and access** Docker images.
- Useful for beginners since it’s public, easy to use, and integrates directly with Docker.
    
---

## 👍 Why Developers Use Docker Hub

1. **Accessibility** – anyone can quickly pull ready-made images (e.g. Python, MySQL).
2. **Large collection** – official, secure, and regularly updated images from trusted sources.
3. **Free tier** – you can host public repositories, perfect for open-source projects.


**🛠 Steps to Use Docker Hub**
1. login from the command line or vscode: docker login (enter username & password)
2. Create a Repository-  On Docker Hub, click **Create Repository**.
- Name it (e.g. `flask-mysql`) and set it as **public** or **private**.
1. Build and tag your image -  **docker build -t <dockerhub username>/<repository name>: tag** (this could be a version number) . (. use the current directory)
 example : docker build -t ebrimabojang/flask-mysql:V1 .

 Push the Image to Docker Hub
 2. docker push <username>/<repository>:<tag>
 example: docker push ebrimabojang/flask-mysql:V1 
 
 Pull the Image (Download it Anywhere)
 docker pull ebrimabojang/flask-mysql:v1
this downloads it to your local host 

**Learn how to upload (push) your Docker image to Amazon ECR (Elastic Container Registry)**, which is a private container image storage service by **AWS (Amazon Web Services).**


Create a Repository in Amazon ECR
## Pushing Docker Images to **Amazon ECR (Elastic Container Registry)**

### Why use ECR instead of Docker Hub?

- **Private & Secure**: Stores images inside your AWS account (not public like Docker Hub by default).
    
- **Better Integration**: Works seamlessly with AWS services (ECS, EKS, Lambda, etc.).
    
- **Managed Service**: AWS handles scaling, availability, and access controls.


- In the AWS Console, search for **ECR**.  
- Click on **Elastic Container Registry**.    
- Click ==Create Repository==, name it (e.g. `flask-mysql`), and leave other settings as default. ✅ _Why?_: This is the “bucket” where we’ll store our Docker images in AWS. 
 Once created, click the repository and select **“View Push Commands”** – this gives you all the necessary terminal commands for pushing your image.

### 4. **Authenticate with ECR**

- Copy the login command from AWS.
- Paste it into your terminal.
- This **logs Docker into your ECR repository**, not AWS as a whole.
    

 5. **Build Your Docker Image**
- Run the `docker build` command using your Dockerfile.  
    Example:
    `docker build -t flask-mysql .`
    ✅ _Why?_: You need a Docker image locally before you can upload it.

 6.Tag the Docker Image

- You must tag the image with your **ECR repository URL**.  
    Example:
    
    `docker tag flask-mysql:latest [your-ecr-url]/flask-mysql:latest`
    - - ✅ _Why?_: ECR requires the image to have its full registry path in the tag.

 7. Push the Image to ECR

- Now, use the `docker push` command:
    
    `docker push [your-ecr-url]/flask-mysql:latest`
    
✅ _Why?_: This uploads your image to AWS, making it available anywhere in your cloud environment.

### 8. **Check It on AWS**

- Go back to AWS Console → ECR → Your repository.
    
- Refresh, and you’ll see the uploaded image listed.
    

---

## 📥 Pulling the Image from ECR

If you want to use this image later (on another machine or locally), just run:

`docker pull [your-ecr-url]/flask-mysql:latest`

---

## 🚀 Run the Container

Use the following to run the container:

`docker run -p 5002:5002 [your-ecr-url]/flask-mysql:latest`