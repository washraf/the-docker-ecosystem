# CPU Control

Controlling CPU is core management utility of containers. 
####Options to control the CPU of a container:

**-c, --cpu-shares=0**	

CPU shares (relative weight)

**--cpu-period=0**

Limit the CPU CFS (Completely Fair Scheduler) period

**--cpu-quota=0**

Limit the CPU CFS (Completely Fair Scheduler) quota

**--cpuset-cpus=""**

CPUs in which to allow execution (0-3, 0,1)

####CPU share constraint:
By default, all containers get the same proportion of CPU cycles. This proportion can be modified by changing the container’s CPU share weighting relative to the weighting of all other running containers. To modify the proportion from the default of **1024**, use the **-c** or **--cpu-shares** flag to set the weighting to 2 or higher.

The proportion will only apply when CPU-intensive processes are running. When tasks in one container are idle, other containers can use the left-over CPU time. The actual amount of CPU time will vary depending on the number of containers running on the system.

####CPU Period Contraint and Quota

The default CPU CFS (Completely Fair Scheduler) period is 100ms. We can use --cpu-period to set the period of CPUs to limit the container’s CPU usage. And usually **--cpu-period** should work with -**-cpu-quota**.

The --cpu-quota flag limits the container’s CPU usage. The default 0 value allows the container to take 100% of a CPU resource (1 CPU). The CFS (Completely Fair Scheduler) handles resource allocation for executing processes and is default Linux Scheduler used by the kernel. Set this value to 50000 to limit the container to 50% of a CPU resource. For multiple CPUs, adjust the **--cpu-quota** as necessary
For more about scheduling check the [Linux Scheduling documentation](https://www.kernel.org/doc/Documentation/scheduler/sched-bwc.txt)

####CPU Set (CPU pinning)
It is also possible to pin a container to one or more CPU cores. This means that work for this container will only be scheduled on the cores that have been assigned to this container.

####Examples:

1- CPU Period Control: this means the container can get 50% CPU worth of run-time every 50ms.

```$ docker run -ti --cpu-period=50000 --cpu-quota=25000 ubuntu:14.04 /bin/bash```

2- Run and Ubuntu container in interactive tty mode where it can be executed on cpu1and cpu3.

```$ docker run -ti --cpuset-cpus="1,3" ubuntu:14.04 /bin/bash```

3 - Run and Ubuntu container in interactive tty mode where it can be executed on cpu0, cpu1 and cpu2.

```$ docker run -ti --cpuset-cpus="0-2" ubuntu:14.04 /bin/bash```
