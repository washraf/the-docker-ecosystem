# Docker Diff

List the changed files and directories in a **container’s filesystem** from the base image. 

####Usage
$ sudo docker diff container

###Example
Assume There are 3 events that are listed in the diff:

* 
A - Add
* 
D - Delete
* 
C - Change

```$ docker diff determined_bose```

* 
C /root
* 
A /root/xyz
* 
A /root/.bash_history
* 
A /root/abc
* 
A /root/lmn

For more information visit the [official diff page](https://docs.docker.com/reference/commandline/diff/)
