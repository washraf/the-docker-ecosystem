# Container Control Commands

## Docker Start, Stop and Restart
These three commands are used to change the state of a container from running to stopped or restart it.

**Stop:** When a user issues this command, the Docker engine sends SIGTERM (-15) to the main process, which is running inside the container.

The **SIGTERM** signal requests the process to terminate itself gracefully. Most of the processes would handle this signal and facilitate a graceful exit. However, if this process fails to do so, then the Docker engine will wait for a grace period. Even after the grace period, if the process has not been terminated, then the Docker engine will forcefully terminate the process. The forceful termination is achieved by sending **SIGKILL** (-9).

The **SIGKILL** signal cannot be caught or ignored, and so it will result in an abrupt termination of the process without a proper clean-up.

###**Usage**
```$ docker stop | start| restart [OPTIONS] CONTAINER [CONTAINER...]``` 

    [Options]
    -t, --time=10      Seconds to wait for stop before killing it
    
    [Container]	
    Control the container either by Name or ID

###**Example**
```$ sudo docker start Your_Ubuntu_Container```

## Exec Command

Run a command in a running container

####**Usage**:

```docker exec [OPTIONS] CONTAINER COMMAND [ARG...]```

    -d, --detach=false         Detached mode: run command in the background
    -i, --interactive=false    Keep STDIN open even if not attached
    -t, --tty=false            Allocate a pseudo-TTY
    -u, --user=                Username or UID (format: <name|uid>[:<group|gid>])
    
####**Example:**
```$ docker exec -d ubuntu_bash touch /tmp/execWorks```

This will create a new file /tmp/execWorks inside the running container ubuntu_bash, in the background.

```$ docker exec -it ubuntu_bash bash```

This will create a new Bash session in the container ubuntu_bash.

## Attach Command

This commands brings a container to the foreground. The container must be running to be attached.

###**Usage**
```$ docker attach [OPTIONS] CONTAINER```
###**Example**
```$ sudo docker attach Your_Ubuntu_Container```

For more Information visit the [commandline page](https://docs.docker.com/reference/commandline/attach/)

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

