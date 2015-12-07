# Docker Links

Docker has a **linking** system that allows you to link multiple containers together and send connection information from one to another. When containers are linked, information about a source container can be sent to a recipient container. This allows the recipient to see selected data describing aspects of the source container.
To establish links, Docker relies on the names of your containers. Links allow containers to discover each other and securely transfer information about one container to another container. When you set up a link, you create a conduit between a source container and a recipient container. The Source can access the linked container in a secured setup, is that the linked containers can communicate using secured tunnels without exposing the ports used for the setup, to the external world.

For more Information visit the [docker links guide](https://docs.docker.com/userguide/dockerlinks/)

####Usage
```--link <name or id>: alias```

If the alias is omitted the name will be set to be the same name as the container name but note that both the name and the alias should be unique to the host.
####How Linking Works
When two containers are linked together, the Docker engine automatically exports a few environment variables to the recipient container. These environment variables have a well-defined naming convention, where the variables are always prefixed with capitalized form of the alias name.

For example if a container is linked to a MySQL image with alias SQLDB there are three rules to naming environment variables in the target container:
* 
If the source container has an environment variable called Name an environment variable name SQLDB_NAME will be created
* 
Environment variables that are set using the –e option in the run command or the ENV command in the docker file are named <alias>_ENV_EVNAME e.g. SQLDB_ENV_PASSWORD=123456
* 
Port values that are set using the –p option in the run command or the EXPOSE command the docker file are named <alias>_PORT_PROTOCOL_PORTNO_ADDR e.g. SQLDB_PORT_80_TCP_PORT=336 or SQLDB_PORT_80_TCP=tcp://172.17.0.4:80

###DEMO
Create two container and link them together and check for the /etc/hosts file and all the environment variables.

```$sudo docker run --name source -it -e w="Walid" -p 80:80 ubuntu /bin/bash```

This will open an ubuntu container in interactive tty mode and set an enviroment variable called W with Walid as a value also expose the port 80 and map it to the host’s port 80.

**And in another console:**

```$sudo docker run --name target --link source:src -it ubuntu /bin/bash```

    root@ 765ad6da2b4e:/ cat etc/hosts
    …
    172.17.0.4	src 87de493a5d62 source
    172.17.0.4	source
    172.17.0.4	source.bridge
    172.17.0.5	target
    172.17.0.5	target.bridge
    …
    root@ 765ad6da2b4e:/ env
    …
    SRC_NAME=/target/src
    SRC_ENV_w=Walid
    SRC_PORT_80_TCP_PORT=80
    SRC_PORT_80_TCP_ADDR=172.17.0.4
    SRC_PORT_80_TCP=tcp://172.17.0.4:80
    SRC_PORT=tcp://172.17.0.4:80
    …