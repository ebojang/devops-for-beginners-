
**CONTAINERS & DOCKER**

Containers are lightweight portable units for running applications. They bundle
applications and all its dependencies ensuring it runs consistently across different
environments.
Containers will run the code, runtime, binaries and libraries
Container sits above the docker engine. Which sits in line with the host operating
system.

**Docker engine**- provides the environment to build, run and manage containers.
Above the docker engine, you have the docker containers.
Containers share docker engine but manages its code and all its dependencies
independently.
Containers do not interfere with each other and can be moved from one environment
to another. (They are isolated from each other).
They are resource efficient compared to virtual machines.
They are easy to start-up.

**DOCKER**
Docker is an open platform for developing, shipping and running applications in
containers.

**Docker components**
**Docker engine-** core service that runs and manages containers. It’s a portable
lightweight application runtime and packaging tool.
**Docker Hub:** is a cloud service for sharing applications and automating workflows. Is
a repository where you can find and share container images.

**IMAGES &CONTAINERS

Images are templates for creating containers.
Images are immutable (meaning they don’t change once created) only way to
change them is by recreating the image.
Immutability ensures the application runs consistently no matter where it is deployed.
Containers are running instances of images.
**Docker file**- is a file used to build docker images. Contains a series of instructions
that docker uses to assemble an image.


| container                                                                                                    | Virtual machines                                                                                             |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| lightweight and share the host operating system.                                                             | allows multiple operating system to run on a physical machine                                                |
| containers run on the docker engine which sits on top of the host operating system.                          | Hypervisor in VM is responsible for creating and allocating resources like cpu, memory and storage to the VM |
| containers are isolated from each other at the process level but share the underlying host operating system. | each virtual machine has to bootup a full guest operating system. this is time consuming                     |
| Easy to startup                                                                                              |                                                                                                              |
| only uses what's necessary for the application                                                               | consume more resources                                                                                       |
|                                                                                                              | strong isolation - each vm has it's own operating system                                                     |
| Highly portable and can be run in a different environment.                                                   | less portable due to size and dependencies on specific hypervisor                                            |

DOCKER DESKTOP APP and how docker works 
After installation, run 
docker --version
also run 
docker run Hello-world
It first looks for hello world image from your local laptop. 
if nothing found, it then pulls the image from docker hub.
Docker then created the container from the pulled image and creates it.

==VIEW ALL RUNNING CONATIANERS?==
RUN
**docker ps** -  this shows all running containers 
**docker ps** -a - shows all running containers alongside the stopped ones.


DOCKER FILE 
Docker file is a series of instructions on how to create a docker image.
Each instruction in a dockerfile creates a layer in the image.

==BASIC STRUCTURE OF A DOCERFILE== 

1)  **FROM** :  specifies the base image to use for the docker image. base image serves as the foundation for your application. example base image can be a python image, node image 
2) **Run** -  executes commands in the container. This instruction is used to install packages, update dependencies etc. 
3) **copy** - copies files from the host machine into the container. copy command takes two parameters, the  source and destination this is how application code are transferred and used for container configuration.
4) **WORKDIR** -  sets the working directory. this ensures that the command runs in the correct directory within the container.
5) **cmd** - specifies the command to run when the container starts.
CMD is the final instruction that defines the behaviour of the container once it's up and running