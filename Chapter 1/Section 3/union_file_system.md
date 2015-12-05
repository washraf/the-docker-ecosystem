# Union File System

Union file system represents file system by grouping directories and files in branches.
A Docker image is made up of filesystems layered over each other (i.e. Branches that is stacked on top of each other) and grouped togeather. At the base is a boot filesystem, bootfs, which resembles the typical Linux/Unix boot filesystem. A Docker user will probably never interact with the boot filesystem.

![](http://collabnix.com/wp-content/uploads/2015/03/dockerImage.png)
Indeed, when a container has booted, it is moved into memory, and the boot filesystem is unmounted to free up the RAM used by the initrd disk image.
So far this looks pretty much like a typical Linux virtualization stack. 
Indeed, Docker next layers a root filesystem, rootfs, on top of the boot filesystem. This rootfs can be one or more operating systems (e.g., a Debian or Ubuntu filesystem).

Docker calls each of these filesystems images. Images can be layered on top of one another. The image below is called the parent image and you can traverse each layer until you reach the bottom of the image stack where the final image is called the base image. Finally, when a container is launched from an image, Docker mounts a read-write filesystem on top of any layers below. This is where whatever processes we want our Docker container to run will execute. 
When Docker first starts a container, the initial read-write layer is empty. As changes occur, they are applied to this layer; for example, if you want to change a file, then that file will be copied from the read-only layer below into the read-write layer. The read-only version of the file will still exist but is now hidden underneath the copy.

![](http://devopscube.com/wp-content/uploads/2015/02/docker-filesystems-busyboxrw.png)
