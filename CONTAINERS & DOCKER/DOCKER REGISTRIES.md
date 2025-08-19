
## 🗂 What is a Docker Registry?
- A **Docker Registry** is like an online library for Docker images (Central storage and distribution hub for docker images).
- It stores, manages, and distributes your images.
- Without a registry, your images only exist locally.

## Types of Registries
1. **Public Registries**
    - Example: **Docker Hub**
    - Anyone can access or share images.  
    - Great for open-source use (e.g., pulling a MySQL image).   
2. **Private Registries**
    - Example: **AWS Elastic Container Registry (ECR)**
    - Access is restricted.
    - Used for sensitive or proprietary applications.
    - You control who can see or use your images.

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
1. Build and tag your image -  docker build -t <dockerhub username>/<repository name>: tag (this could be a version number) . (. use the current directory)
 example : docker build -t ebrimabojang/flask-mysql:V1 .

 Push the Image to Docker Hub
 1. docker push <username>/<repository>:<tag>
 example: docker push ebrimabojang/flask-mysql:V1 
 
 Pull the Image (Download it Anywhere)
 docker pull ebrimabojang/flask-mysql:v1
this downloads it to your local host 


