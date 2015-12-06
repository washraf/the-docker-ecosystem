# Containers implementations

Although this document is focused on **docker** we must clarify that there are different containers implementations.

####LXC (Linux Containers)
This is the father of all kinds of containers and it represents an operating-system-level virtualization environment for running multiple isolated Linux systems (containers) on a single Linux machine.
You can get more information [Click Here](http://en.wikipedia.org/wiki/LXC)

####OpenVZ
This is an OS-level virtualization technology based on the Linux kernel and the operating system. OpenVZ allows a physical server to run multiple isolated operating system instances, called containers, virtual private servers (VPSs), or virtual environments (VEs).

####Lmctfy
This was by Google to compete with docker but it was not a success.

####The FreeBSD jail
This is a mechanism that implements an OS-level virtualization, which lets the administrators partition a FreeBSD-based computer system into several independent mini-systems called jails.
The AIX Workload partitions (WPARs)
These are the software implementations of the OS-level virtualization technology, which provide application environment isolation and resource control.

####Solaris Containers (including Solaris Zones)
This is an implementation of the OS-level virtualization technology for the x86 and SPARC systems. A Solaris Container is a combination of the system resource controls and boundary separation provided by zones. Zones act as completely isolated virtual servers within a single operating system instance.