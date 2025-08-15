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


