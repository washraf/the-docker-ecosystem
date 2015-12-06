# Docker Login

Register or log in to a docker registry.

###Usage

```docker login [OPTIONS] [SERVER]```

**[options]**

-e, --email=""       Email

-p, --password=""    Password

-u, --username=""    Username

**[server]**

Docker registry server, if no server is specified ("https://index.docker.io/v1/) is the default.

###Example
```$ sudo docker login```

```Username: XXXXX```

```Password: ```

```Email: XXX@XXX.com```

####**WARNING:** login credentials saved in /root/.docker/config.json
Login Succeeded

Also check the [logout command]( https://docs.docker.com/reference/commandline/logout/)