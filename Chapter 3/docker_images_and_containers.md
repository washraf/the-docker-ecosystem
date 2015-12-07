# Docker Images and Containers

###Docker images 

A Docker image is a read-only template. For example, an image could contain an Ubuntu operating system with Apache and your web application installed. Images are used to create Docker containers. Docker provides a simple way to build new images or update existing images, or you can download Docker images that other people have already created. Docker images are the build component of Docker.

###Docker containers

A container is the physically existing collection of processes that uses the OS resources to implement a functionality, a container is always based on an image and to turn an image into a container, the Docker engine takes the image, adds a read-write filesystem on top and initializes various settings including network ports, container name, ID and resource limits. A running container has a currently executing process, but a container can also be stopped (or exited to use Docker's terminology). An exited container is not the same as an image, as it can be restarted and will retain its settings and any filesystem changes.
