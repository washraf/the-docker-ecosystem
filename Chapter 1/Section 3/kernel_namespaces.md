# Kernel Namespaces

A kernel namespace wraps a global system resource in an abstraction that makes it appear to the processes within the namespace that they have their own isolated instance of the global resource.

Changes to the global resource are visible to other processes that are members of the namespace, but are invisible to other processes. 

####There are 6 Name Spaces:
* 
**PID** namespace provides isolation for the allocation of process identifiers (PIDs), lists of processes and their details. While the new namespace is isolated from other siblings, processes in its "parent" namespace still see all processes in child namespaces—albeit with different PID numbers.
* 
**Network** namespace isolates the network interface controllers (physical or virtual), iptables firewall rules, routing tables etc. Network namespaces can be connected with each other using the "veth" virtual Ethernet device.
* 
**"UTS" **namespace allows changing the hostname.
* 
**Mount** namespace allows creating a different file system layout, or making certain mount points read-only.
* 
**IPC** namespace isolates the System V inter-process communication between namespaces.
* 
**User** namespace isolates the user IDs between namespaces.

Namespaces are created with the "unshare" command or syscall, or as new flags in a "clone" syscall.

For More about name spaces [click here](http://man7.org/linux/man-pages/man7/namespaces.7.html)