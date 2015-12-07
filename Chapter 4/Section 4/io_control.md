# IO Control

####Block IO bandwidth (Blkio) constraint
By default, all containers get the same proportion of block IO bandwidth (blkio). This proportion is 500. To modify this proportion, change the container’s blkio weight relative to the weighting of all other running containers using the **--blkio-weight** flag.
The **--blkio-weight** flag can set the weighting to a value between 10 to 1000.
####Examples
```$ docker run -ti --name c1 --blkio-weight 300 ubuntu:14.04 /bin/bash```

```$ docker run -ti --name c2 --blkio-weight 600 ubuntu:14.04 /bin/bash```

>The blkio weight setting is only available for direct IO. Buffered IO is not currently supported.
