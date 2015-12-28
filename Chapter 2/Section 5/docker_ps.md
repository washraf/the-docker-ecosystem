# Docker PS

Shows the current running containers on the system

###Usage

```$ docker ps [OPTIONS]```

[OPTIONS]

-a all containers

-filter [] filtering container based on any parameter
###Example
```$ sudo docker ps -a```

    CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS                          PORTS               NAMES

    2e4bea848301        hello-world         "/hello"            About a minute ago   Exited (0) About a minute ago                       sharp_jang

For more information visit the [offical docker documentation]( https://docs.docker.com/reference/commandline/ps/)

A very good discussion on the PS Command on [stackoverflow](http://stackoverflow.com/questions/34417255/where-does-docker-ps-command-look-for-current-containers)