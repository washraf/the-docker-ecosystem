# Docker Create

The docker create command creates container that allows setting configuration you can set in run command the only difference that the created container is never started and in order to start a container run the start command.

For more the docker create check out the [official documentation](https://docs.docker.com/engine/reference/commandline/create/). 
##**Usage**
```$ sudo docker create [OPTIONS] IMAGE [COMMAND] [ARG...]```
##**Example**
```$ docker create -t -i fedora bash```

6d8af538ec541dd581ebc2a24153a28329acb5268abe5ef868c1f1a261221752

```$ docker start -a -i 6d8af538ec5```

bash-4.2#


