# Docker Vocab

####Docker Image and Container
A Docker image is template or a class that has all the necessary file to create a container. The difference between an image and a container is like the difference between the class and an object. A class is a manuscript of what should be there without any physical existence and this is just what an image is an image contains what should be there without any actual access to any resources (e.g. CPU time, memory and storage). On the other hand a container is the object it has a physical existence on the host with an IP, exposed ports and real Processes.

At the end of a day docker is just a virtualization and process isolation solution. So if you made the image host all application, the domain and data access layers you're just back at square one. Docker implements and provides tools for orchestration that will make your life easier so please an image should be used as single component in your system.

####Docker Engine
The docker command run in daemon mode. This turns a Linux system into a Docker server that can have containers deployed, launched, and torn down via a remote client.

####Docker Client
The docker command used to control most of the Docker workflow and talk to remote Docker servers.

####Docker Hub (Registry)
The Storage component of docker that allows you to save, use and search for images.
