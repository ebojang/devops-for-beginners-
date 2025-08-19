**Containerising a Python Flask App with Docker**

1. **Create a Dockerfile** in your project folder (capital “D”, no extension example **touch Dockerfile**).
    Dockerfile is a text file that contains a series of instructions on how to build a container image
2. **Dockerfile contents:**
    - `FROM python:3.8-slim` → Base image with minimal Python.
    - `WORKDIR /app` → Set working directory inside container.
    - `COPY . .` → Copy all files from current folder to container.
    - `RUN pip install flask` → Install Flask in container.
    - `EXPOSE 5002` → Make port 5002 available externally.
    - `CMD ["python", "app.py"]` → Command to start the app.
        
3. **Build the  Docker image**
    - Run: `docker build -t hello-flask .
    - `-t hello-flask` → Tag (name) the image.
    - `.` → Use current directory for Dockerfile.
        
4. **Result** → A portable container image that can run your Python app anywhere.

WORKFLOW 

1) Create a dockerfile (your recipe)
2) create an image ( docker image -t (name of your image  example bojang))- snapshot of your application at any given point of time 
3) Then run it as a container 

### **2. Running the container**

- Command example:
    `docker run -d -p 5002:5002 hello-flask 
    - `-d` → detached mode (runs in background).
    - `-p host:container` → maps your machine’s port to the container’s port.
    - `--name` → gives the container a friendly name.
    - **hello-flask** = the image name.
        

---

### **3. Checking the container**

- `docker ps` → shows running containers, including:
    - Container ID
    - Image
    - Ports in use   
- Test in browser: visit `http://localhost:5002`
### **4. Stopping the container*
- `docker stop <container_id>` → stops it.
- `docker ps` after stopping → confirms nothing is running.


**Introduction to Docker Compose:**

Docker compose is a tool that allows you to define and manage multiple container applications.
t’s a tool that:

- Lets you define all your containers in a single **YAML file** (called a _Docker Compose file_).
- Makes it easy to start, stop, and manage everything with simple commands.   
- ==Automatically creates a network so containers can communicate without extra setup.== 

The **YAML file** is like a blueprint. It specifies:
- The services (containers) your app needs.
- Images, ports, and how the containers link together.
With just one command – **`docker-compose up`** – you can launch the entire environment in seconds.

**This makes Docker Compose ideal for building and running multi-container applications, such as the Flask and MySQL apps we’ve worked on earlier.**

IMPORTANCE OF DOCKER COMPOSE IN DEVOPS 
* makes development and testing easier 
* ensures consistency across different environments
* enhances teamwork. makes it easy to share codes and configurations



CREATE a docker compose yml file 
Create a file named `docker-compose.yml`:
touch docker-compose.yml

Docker-compose.yml content :
```
version: '3.8'

services:
  web:
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - mydb

  mydb:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: my-secret-pw
```

**Breaking it down:**
- `web` → Our Flask app.
    - `build: .` → Build from the Dockerfile in the current directory.
    - `ports` → Maps port 5000 on your computer to port 5000 inside the container.
    - `depends_on` → Ensures the database (`mydb`) starts before the web app.
        
- `mydb` → Our MySQL database.
    
    - `image: mysql:5.7` → Uses an official MySQL version 5.7 image from Docker Hub.
    - `environment` → Sets up the root password.

## ▶️ Running the application

- **Start everything**
    
    `docker-compose up` **-d**
    - Reads the YAML file.    
    - Builds the `web` image.
    - Starts both `web` and `db`. 
     Creates a default network so they can talk to each other.
**TO VIEW DOCKERCOMPOSE LOGS:**
docker-compose logs 
 
 **TO STOP APPLICATION:**
 docker-compose down
 this stops the containers from running