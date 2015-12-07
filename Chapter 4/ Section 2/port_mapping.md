# Port Mapping

Port mapping allows a mapping between the host ports with the containers inner port. The port mapping is configured either by –p or –P options in the run command.

####-p example 
These run options allows the user to map a port container port to a host port

```$ sudo docker run -p 1234:80 imagename```
####-P example 
These run options allows the user to map all ports exposed by container to ports in the host

```$ sudo docker run -P imagename```

####Finding mapped port
Finding the mapped port could be found by the command **ps** but as a better way is the port command for more information visit [the port guide](https://docs.docker.com/reference/commandline/port/)

####Usage
```docker port CONTAINER_Name [PRIVATE_PORT[/PROTO]]```
####Example
```$sudo docker port  test_server ```
    
    8080/tcp -> 0.0.0.0:1234
    
```$sudo docker port  test_server 1234```
    
    0.0.0.0:1234
    
```$sudo docker port  test_server 1234/tcp```
    
    0.0.0.0:1234
