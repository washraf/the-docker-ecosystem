# Container Control Commands

1. Create
2. Start
3. Stop
4. Restart
5. Execute
6. 

##Copy data [From|To] container
It copies data from and to running containers. 

For More visit the [Copy documentation](https://docs.docker.com/engine/reference/commandline/cp/)
###**Usage**
```$ docker cp [OPTIONS] CONTAINER:PATH LOCALPATH|-```

```$ docker cp [OPTIONS] LOCALPATH|- CONTAINER:PATH```

###**Example**
Copy Data from Container to host

```$ sudo docker cp testcopy:/root/file.txt .```


Copy Data from host to container

```$ sudo docker cp host.txt testcopy:/root/host.txt```


##Inspect
This command is used to check for the current configuration of a container from network to drivers and name. It prints the information in the form of JSON File

####**Usage**
```$ docker inspect [OPTIONS] CONTAINER|IMAGE [CONTAINER|IMAGE...]```
####**Example**
```$ sudo docker inspect Your_Ubuntu_Container```

##Deleting a container
This command is used to delete any container either by name or ID. Put Make sure that the container is stopped before you remove it.
####**Usage**
$ docker rm [OPTIONS] CONTAINER [CONTAINER...]
####**Example**
$ sudo docker rm Your_Ubuntu_Container

