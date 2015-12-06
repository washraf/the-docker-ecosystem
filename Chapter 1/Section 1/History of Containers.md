# History Of Containers

#### One of most basic laws of science is the Law of the Conservation of Energy “Energy cannot be created or destroyed; it can only be changed from one form to another”.

#### Also, Darwin states that “It is not the strongest of the species that survives, nor the most intelligent that survives. It is the one that is most adaptable to change”.

From those two golden rules we can figure three things about any technology, tool or concept:

1. 
Technologies evolve the techniques for software development in the 90's are far different from the ones used now.
Tools that doesn't adapt to new techniques, requirements will soon be replace by another by a more change adaptable ones even if it's very smart, powerful or cheap.

1. 
Ideas doesn't come out from the vacume most concepts are incrementally created.
1. 
A technology like containers or a tool like docker didn’t invent the wheel; as, Controlling users, resource and tasks is the ultimate role for any Operating system.

The following shows the historical time-line of the changes that lead to what we have now.
 
* 
####1979 :
    During development of Unix Version 7, A chroot on Unix operating systems is an operation that changes the apparent root directory for the current running process and its children. For us now its very standard for a root user to have its own root directories as well as each user.
* 
####2000 :	
    FreeBSD 4.0 was released with a new command, called jail, which was designed to allow shared-environment hosting providers to easily and securely create a separation between their processes and those of their individual customers. Also, allowed isolated resource sharing between processes. FreeBSD jail expanded chroot’s capabilities, but restricted everything a process could do with the underlying system and processes in other jails. And It had problems with shared devices and resources.
* 
####2004 :
    Sun released an early build of Solaris 10, which included Solaris Containers, and later evolved into Solaris Zones. This was the first major commercial implementation of container technology and is still used today to support many commercial container implementations.
* 
####2005
    Open VZ set a complete vision but it was hyper visor like implementation with no speed improvements it was based on chroot and rlimit but it had a complete visions.
    The main problem with openVZ with that they changed the linux kernel it self which by time drifted more and more from the standard releases.
* 
####2006 :
    Engineers at Google (primarily Paul Menage and Rohit Seth) started the work on this feature under the name "process containers". That was later named to control groups. And it’s now a part from the Linux kernel 2.6.24 release January 2008.
    This feature is the most important linux feature that motivited the existance of containers and its explaned in depth a little further in the road.
* 
####2007 :
HP released Secure Resource Partitions for HPUX, later renamed to HP-UX Containers;
* 
####2008 :
LXC (Linux Containers) as the first Cgroups based frame work to support containers. LXC provided a middle ware component that allowed the idea of containers to exist.
* 
####2013 :
    Docker was realeased and doin’t expect to explan docker in a couple of words but docker is a framework to create, monitor and maintain containers that was built on LXC but shifted recently to lib container.
* 
####2013 :
lmctfy (Let Me contain that for you) was release by Google to compete with Docker. [The Project Git Repository](https://github.com/google/lmctfy)
* 
####2014 :
    Google Announces that it has used containers as a concept since * 
2006 and released its open source project [kubernetes](http://kubernetes.io/) that allows container clustering. 

* 
####2015 :
[OPEN CONTAINER INITIATIVE](https://www.opencontainers.org/) annoced that the Docker lib containers is standardized as the base for a Linux kernel feature.
