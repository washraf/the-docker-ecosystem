# Docker File Instructions
Creating a docker file is the most used way to create a docker image.
In this section we are going to explore the ways to create a docker image file.

For More information visit [the docker builder](https://docs.docker.com/reference/builder/).

###From:

This instructions sets the base image for the new Image. This is considered the most important instruction in the Dockerfile. This instruction must be the first one to be written and it treats the image as the docker run do. If the images are found locally it’s used and if not it will be pulled from the assigned registry and finally if the image is not found it will raise a build error.
####Usage
 	FROM <image>
 	FROM <image>:<tag>
 	FROM <image>@<digest>

###Maintainer:
Who is the Image creator
####Usage
    MAINTAINER <Name>
###WORKDIR:
Sets the start directory for the container where the run and the CMD instructions are executed.
####Usage
    WORKDIR /path/to/workdir
###RUN:
The RUN instruction will execute any commands in a new layer on top of the current image and commit the results. The resulting committed image will be used for the next step in the Dockerfile.
####Usage	
 	RUN <command> (the command is run in a shell - /bin/sh -c - shell form)
 	RUN ["executable", "param1", "param2"] (exec form)

###CMD:
The CMD Command is used as a default entry point to container. And if more than one is added the last one only will take effect
####Usage
 	CMD ["executable","param1","param2"] (exec form, this is the preferred form)
 	CMD ["param1","param2"] (as default parameters to ENTRYPOINT)
 	CMD command param1 param2 (shell form)

###COPY:
Copies files from the host file system to the image file system. 
####Usage
 	COPY <src>... <dest>
 	COPY ["<src>",... "<dest>"] (this form is required for paths containing whitespace)
###ADD:
The add file is similar to the copy but can handle both tar files and remote URLs
####Usage
 	ADD <src>... <dest>
 	ADD ["<src>",... "<dest>"] (this form is required for paths containing whitespace)
###ENV:
Sets some environment variables for the container
####Usage
 	ENV <key> <value> only one perline 
 	ENV <key>=<value> ... allows multiple per line
###USER:
Sets the user that will be running in the container and the default is the root.
####Usage
```USER <UID>|<UName>```

###EXPOSE:
This allows the container ports to be accessed from the global ports. Note that Port mapping has to be specified directly at creation time using the –p or –P commands
####Usage
    EXPOSE <port> [<port>...]

###ENTRYPOINT:
The ENTRYPOINT instruction will help in crafting an image for running an application (entry point) during the complete life cycle of the container, which would have been spun out of the image. When the entry point application is terminated, the container would also be terminated along with the application and vice versa.
The ENTRYPOINT instruction cannot be overridden in the run command.
####Usage
 ```ENTRYPOINT ["executable", "param1", "param2"] (the preferred exec form)```
 
 ```ENTRYPOINT command param1 param2 (shell form)```

###Vloume:
The VOLUME instruction creates a mount point with the specified name and marks it as holding externally mounted volumes from native host or other containers. 
####Usage
```VOLUME ["/data"]```

It is generally considered a bad idea to run commands like apt-get -y update or yum -y update in your application Dockerfiles because it can significantly increase the time it takes for all of your builds to finish. Instead, consider basing your application image on another image that already has these updates applied to it.
