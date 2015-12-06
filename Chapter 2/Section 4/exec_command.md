# Exec Command

Run a command in a running container

####**Usage**:

```docker exec [OPTIONS] CONTAINER COMMAND [ARG...]```

    -d, --detach=false         Detached mode: run command in the background
    -i, --interactive=false    Keep STDIN open even if not attached
    -t, --tty=false            Allocate a pseudo-TTY
    -u, --user=                Username or UID (format: <name|uid>[:<group|gid>])
    
####**Example:**
```$ docker exec -d ubuntu_bash touch /tmp/execWorks```

This will create a new file /tmp/execWorks inside the running container ubuntu_bash, in the background.

```$ docker exec -it ubuntu_bash bash```

This will create a new Bash session in the container ubuntu_bash.
