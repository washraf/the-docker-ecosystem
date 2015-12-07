# Process NameSpaces

The process namespace allows a translation between a two versions of a process id which is ideal for containers allowing a process two have an id that is used inside the container and another one outside it.
###Validating Name Spaces translation
In the following set of experiments we are going to show how it’s done.

**Step 1:** Create A normal contianer
Create an Ubuntu container in an interactive mode

```# docker run –it ubuntu /bin/bash```

    root@1b51c60ecc24:/#

**Step 2:** Find about the current containers

```# docker ps```
    
    CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS              PORTS               NAMES
    1b51c60ecc24        ubuntu              "/bin/bash"         About a minute ago   Up About a minute                       high_carson

**Step 3:** Find process information about the created container

```# docker inspect --format "{{ .State.Pid }}" 1b51c60ecc24```

$$40085$$

**Step 4:** Test this process on the host itself

```# ps -fp 40085```

    UID        PID  PPID  C STIME TTY          TIME CMD
    root     40085 18860  0 14:06 pts/3    00:00:00 /bin/bash
```# cat  /proc/40085/environ```

    PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin^@HOSTNAME=1b51c60ecc24^@TERM=xterm^@HOME=/root^@

**Step 5:** A view inside the container itself
```root@1b51c60ecc24:/# ps -ef```

    UID        PID  PPID  C STIME TTY          TIME CMD
    root         1     0  0 12:06 ?        00:00:00 /bin/bash
    root        15     1  0 12:19 ?        00:00:00 ps -e

##How this works
In the Linux world, every system has just one root process with the **PID 1 and PPID 0**, which is the root of the complete process tree of that system. The Docker framework cleverly leverages the Linux PID namespace to spin a completely new process tree; thus, the processes running inside a container have no access to the parent process of the Docker host. However, the Docker host has a complete view of the child PID namespace spun by the Docker engine.

The PID namespace provides consistent, virtual resource names in place of host-dependent resource names. Such PIDs within a container are trivially assigned in a unique manner in the same way that traditional operating systems assign names, but such names are localized to the container. Since the namespace is private to a given container, there are no resource naming conflicts for processes in different containers.

As a result, processes are created inside of a container and spend their entire lifetimes in the context of that container; they are not allowed to leave one container and join another.

Docker uses some sort of **translation hash table** between the process ids in the container and how its viewed by the host.
