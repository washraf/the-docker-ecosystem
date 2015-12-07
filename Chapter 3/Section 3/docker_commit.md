# Docker Commit

This command will enable you to update the image you’re using by installing the required tools and packages and save it to be used by other users.
The commit command enable you to save a container to an image to be reusable.

###Usage:
    docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
    [options]
      -a, --author=""     Author (e.g., "John Hannibal Smith <hannibal@a-team.com>")
      -c, --change=[]     Apply specified Dockerfile instructions while committing the image
      -m, --message=""    Commit message
      -p, --pause=true    Pause container during commit

###Demo
The Demo will start by using an Ubuntu image and install Nginx webserver on it and save it locally and on my own docker hub registry.

**Step 1:** Run the container and open it from base image

```$ sudo docker run -i -t ubuntu /bin/bash``` 


**Step 2:** Install required packages and tools

```/# apt-get install nginx```

**Step 3:** Exit the container

```/# exit```

Step 4: Find the edited container ID
$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                        PORTS               NAMES
238c9baddb08        Ubuntu              "/bin/bash"         3 days ago          Up 59 minutes                                     walid

Step 5: Commit the image
$ sudo docker commit -m="A new nginx image" --author="washraf" 238c9baddb08 washraf/nginx 
91064f90fa2c120fb7b10ec7354ab0ed5cdb36b942b2b6df65975f5cdc2403cc


Step 6: Check the image
$sudo docker images

REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
walid/nginx         latest              91064f90fa2c        32 seconds ago      206.5 MB
ubuntu              latest              91e54dfb1179        6 weeks ago         188.3 MB
hello-world         latest              af340544ed62        8 weeks ago         960 B 

Step 7: inspect the image
$sudo docker inspect walid/nginx
… The comment will appear as configured

Step 8: Run the container from the new Image
$ sudo docker run walid/nginx
$ sudo docker run -i -t  walid/nginx /bin/bash