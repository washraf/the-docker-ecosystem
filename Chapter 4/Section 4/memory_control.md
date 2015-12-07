# Memory Control

Controlling memory is core management utility of containers. 
####Options to control the memory of a container :
**-m, --memory=""**

Memory limit (format: <number>[<unit>], where unit = b, k, m or g)

**--memory-swap=""**

Total memory limit (memory + swap, format: <number>[<unit>], where unit = b, k, m or g)

**--oom-kill-disable**

By default kernel destroys a process which tries to pass its limit or have no more available memory this option allows us to disable this for the kernel.

**--memory-swappiness=0**

By default, a container’s kernel can swap out a percentage of anonymous pages. To set this percentage for a container, specify a --memory-swappiness value between 0 and 100. A value of 0 turns off anonymous page swapping. A value of 100 sets all anonymous pages as swappable.

**--cpuset-mems=""**

Memory nodes (MEMs) in which to allow execution (0-3, 0,1). Only effective on NUMA systems.
Controlling memory resources is done via the combinations of two options (Memory and Memory Swap).

####We have four main ways to set memory usage:

* 
**memory=inf, memory-swap=inf (default)**

    There is no memory limit for the container. The container can use as much memory as needed.

* 
**memory=L<inf, memory-swap=inf**

    (specify memory and set memory-swap as -1) The container is not allowed to use more than L bytes of memory, but can use as much swap as is needed (if the host supports swap memory).

* 
**memory=L<inf, memory-swap=2*L**

    (specify memory without memory-swap) The container is not allowed to use more than L bytes of memory, swap *plus* memory usage is double of that.

* 
**memory=L<inf, memory-swap=S<inf, L<=S**

    (specify both memory and memory-swap) The container is not allowed to use more than L bytes of memory, swap *plus* memory usage is limited by S.

####**Examples**
1- Run an Ubuntu container in interactive tty mode with a 300Mega memory and no limit on memory swap (-1)

```$ sudo docker run -it -m 300M --memory-swap -1 ubuntu:14.04 /bin/bash```

2- Run an Ubuntu container in interactive tty mode with a 300Mega memory and max memory of 1G.

```$ docker run -ti -m 300M --memory-swap 1G ubuntu:14.04 /bin/bash```

3- Run an Ubuntu container in interactive tty mode which restricts the processes in the container to only use memory from memory nodes 1 and 3.

```$ docker run -ti --cpuset-mems="1,3" ubuntu:14.04 /bin/bash```

4- Run an Ubuntu container in interactive tty mode restricting the processes in the container to only use memory from memory nodes 0, 1 and 2.

```$ docker run -ti --cpuset-mems="0-2" ubuntu:14.04 /bin/bash```