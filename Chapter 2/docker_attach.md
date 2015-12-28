# Docker Attach

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
