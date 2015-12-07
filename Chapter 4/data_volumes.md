# Data Volumes

Docker file system is in memory files systems (i.e. files are deleted with the container itself) to mitigate such problems docker has two methods for managing a data in containers Data volumes and Data Volume Containers.

Another important thing Data volumes that they allow you to specify a file outside the UNION file system which is faster.

**Usecases for Data Volumes :**
 1. The need for faster R/W than Union file system.
 2. Sharing Data between Container and Host.
 3. Data Persistence.

For More Information check the datavolumes [user guide]( https://docs.docker.com/userguide/dockervolumes/)

###Mount a host directory as a data volume
This could be achieved by the –v option in the run command. This allows you both to create a directory or to map an already existing one to a container.
####Example
```root@localhost# docker run --name Name -v /Shared:/SharedData -i –t ubutnu /bin/bash```

This command will create a container with a shared folder with the host **/WalidShared** Folder and will be mounted as **/SharedData** in the container and if the folder didn’t exist in the host it will be automatically created.

The other options is giving a name to the container, opening its command shell with bash shell.

```root@localhost# docker inspect Name```

    …
    "Mounts": [
            {
                "Source": Shared",
                "Destination": "/SharedData",
                "Mode": "",
                "RW": true
            }
        ]
    …
```root@d2040412b5bf:/# ls```

    …
    SharedData
    …

If any thing is written in the **SharedData** Volume it will be written in the **/WalidShared** volume
###Creating a Data Volume
This is done using the VOLUME command is the Docker file. And its saved in this option limits to creating mounted volumes.

###Container Data Volumes
This method uses a container as a shared data volume and called data only container.

```Docker run –v /var_volume1 –-name datavolume postgres```

```Docker run –volumes-from datavolume –-name client 1 postgres```

```Docker run –volumes-from datavolume –-name client 2 postgres```

this will create two postgres containers that shares the same data volume container

>Remember to use the same base image
 
