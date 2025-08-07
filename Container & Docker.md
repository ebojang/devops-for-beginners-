
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
Docker engine- core service that runs and manages containers. It’s a portable
lightweight application runtime and packaging tool.
Docker Hub: is a cloud service for sharing applications and automating workflows. Is
a repository where you can find and share container images.

**IMAGES &CONTAINERS

Images are templates for creating containers.
Images are immutable (meaning they don’t change once created) only way to
change them is by recreating the image.
Immutability ensures the application runs consistently no matter where it is deployed.
Containers are running instances of images.
Docker file- is a file used to build docker images. Contains a series of instructions
that docker uses to assemble an image.

