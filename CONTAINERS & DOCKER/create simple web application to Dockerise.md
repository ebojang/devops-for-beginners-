	8765e34r56890-876543q212first check python version
python3 --version 
install flask 
==Flask is a simple and lightweight framework for creating web applications in python.== 
run 
~ pip3 install flask or pip install flask 
create a new directory under your repository, cd into it and create an application example app.py 
touch app.py
application code 

1) first we import the flask ( from flask import Flask) - this helps in creating a new flask application instance.
2) set a route (@app.route('/') - **We define a route for the root URL which is forward slash**('/')
3) when someone visits the url (==@app.route('/')== the hello_world function is called (def hello_world(). which in return gives back ""i am a king!"
4) application is then run by using app.run
5) variable is used here to run application on our local host which is 0.0.0.0 and using port 5000. this allows us to look at local host 5000 for this application.

```python
from flask import Flask



app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'I am a king!'

if  __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)
```
once template or python file above is saved, run:
❯ python3 app.py
 * Serving Flask app 'app'
 * Debug mode: off
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5002
 * Running on http://172.20.162.206:5002
The above shows the service Flask app is running on the local host 127.0.0.1:5002

press ctrl c to stop the above link and refresh edge browser to confirm app stopped running


**Containerise the above web application:**

1) first write a dockerfile in your hello_flask directory:  touch Dockerfile 
2) then write content of docker file: FROM follow this with the image we are going to use (python), use official python image followed by version.  
FROM python:3.8-slim
3) next, set WORKDIR -  any commands that's run after this will be running in this directory
WORKDIR /app
4) COPY - this is used to copy all of the files from our current directory , which is the app.py to our working directory /app
COPY .  /app
5) Run command to install flask in our container. run 
RUN pip install flask or use sudo apt install pipx
pipx install flask (same way we installed flask on our local device )
 RUN sudo apt intsall pipx
 pipx install flask
 6) EXPOSE - this is used to exposed port 5000 . we are making this port available so that we can access the container from a local host. This makes the application accessible from outside the container 
 EXPOSE 5000
 7) CMD - this tells the docker to run our python application followed by the app that we are trying to run which is app.py
 CMD ["python", "app.py"]

==**DOCKERFILE clean code or version**==
FROM python:3.8-slim
WORKDIR  /app
Copy . /app or COPY . .
RUN pip install flask
EXPOSE 5000
CMD ["python", "app.py"]


Once your dockerfile has been created, next step is to build Docker image. 
go to your terminal on command line  and type 
~ docker build -t hello- flask .
docker build command (initiates the build process) -t hello-flask (-t flag tags the image with a name. in this case we are naming the image hello-flask) followed by . (the . represents current directory and ask the docker to look into the current directory to look for the docker file there. if the direcotory is somewhere else. use ./hello-slask )

docker build -t hello- flask .

MAKE OUR IMAGE LIGHTER: MULTISTAGE BUILDS 

## 🛠 What are Multi-Stage Builds?

- Multi-stage builds = using **multiple `FROM` statements** in your Dockerfile.
- **Stage 1 (Build Stage):** Install heavy dependencies and build the app.
- **Stage 2 (Runtime Stage):** Copy only the app + necessary files into a **slim runtime image**.
- Result → final image is **much smaller** since it doesn’t carry unnecessary build tools.
  
  
#stage 1 : Build stage

FROM python:3.8-slim as build
WORKDIR /app
RUN apt-get update && apt-get install -y \
    gcc \

    python3-dev \

    libmariadb-dev \

    pkg-config

COPY . /app  
RUN pip install flask Mysqlclient

# #Stage 2: Production stage

FROM python:3.8-slim
WORKDIR /app
COPY --from=Build /app /app/
EXPOSE 5000
CMD ["python", "app.py"]