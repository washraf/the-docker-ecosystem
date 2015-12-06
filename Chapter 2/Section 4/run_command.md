# Run Command
Creating containers is the sole purpose of all these infrastructure.

Using this command will initiate the following workflow:

1. 
It will check for the container locally
1. 
Fetch the container from the Docker Hub Repository
1. 
Run the container

Usage
$ docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
Although the Image Builder has a default value for each of the following one can override them.
[Options]
The run options control the image’s runtime behavior in a container. These settings affect:
 	detached or foreground running
 	container identification and name
 	network settings and host name
 	runtime constraints on CPU and memory
 	privileges and LXC configuration

IMAGE[:TAG|@DIGEST]
Using an image based on a specific version based on tag or custom made identifier (Digest)

[COMMAND]
Specifies commands to run at the start of the container

[ARG…]
Other arguments which include adding users and setting environment variable and mounting devices.


For more information visit the [command line page](https://docs.docker.com/reference/commandline/run/)