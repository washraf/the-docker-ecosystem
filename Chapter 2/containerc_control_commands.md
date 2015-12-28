# Container Control Commands

1. Create
2. Start
3. Stop
4. Restart
5. Execute
6. 



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

