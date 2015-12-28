# Docker Images Commands

###Docker Save and Load Images
Docker has two commands the save and load commands that allows you to have a portable version of a docker image.

For more check the save and load pages in the documentation.
####Usage
    $ docker save [OPTIONS] IMAGE [IMAGE...]
    [options]
    -o, --output=""    Write to a file, instead of STDOUT
    $ docker load [OPTIONS]
    [options]
    -i, --input=""     Read from a tar archive file, instead of STDIN. The tarball may be compressed with gzip, bzip, or xz
####Example
    $ docker save -o ubuntu.tar ubuntu:lucid ubuntu:saucy
    $ docker load --input fedora.tar


###Docker Images

Shows the currently available images.
Images are saved in /var/lib/docker/containers directory.

For More Information visit the [Images command page](https://docs.docker.com/reference/commandline/images/).

####Usage
```$ Docker images [OPTIONS] [REPOSITORY]```
####Example
```$ sudo docker images```

    REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
    hello-world         latest              af340544ed62        8 weeks ago         960 B


---


###Docker Pull
Docker pull commands gets an images from the Docker Registry either local or the global one.

This command is called if the run commands can’t find the stated image.

For More information visit the [pull command page](https://docs.docker.com/reference/commandline/pull/)
####usage
```$docker pull [OPTIONS] NAME[:TAG] | [REGISTRY_HOST[:REGISTRY_PORT]/]NAME[:TAG]```

**[options]**
  
    -a, --all-tags=false          Download all tagged images in the repository
    --disable-content-trust=true Skip image verification
####Example
```$ docker pull debian```

will pull the debian:latest image and its intermediate layers

###Docker Search
Docker search commands search on the docker images repositories to find images
For More information visit the [search command page](https://docs.docker.com/reference/commandline/search/)

####Usage
```$docker search [OPTIONS] TERM```

**[options]**
    
    --automated=false    Only show automated builds
    --no-trunc=false     Don't truncate output
    -s, --stars=0        Only displays with at least x stars